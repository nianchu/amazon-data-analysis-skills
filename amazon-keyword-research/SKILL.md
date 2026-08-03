---
name: amazon-keyword-research
description: Build, clean, classify, score, and rank high-conversion Amazon keywords for any marketplace from a verified formal product pool, reverse-ASIN exports, PPC search-term data, Brand Analytics, and optional historical files. Use when Codex needs to discover natural and sponsored terms, evaluate local-market keyword coverage, rank terms by conversion opportunity and CPC, or recommend organic and advertising priorities. Use amazon-product-data-mining first when the product pool has not been defined and verified.
---

# Amazon Keyword Research

Build an auditable Amazon keyword universe without coupling product identity decisions to keyword scoring.

## Boundaries

- Never store credentials, cookies, API keys, verification codes, or seller identity data.
- Treat each marketplace and product project independently.
- Preserve raw exports; write normalization, classification, and scores to new columns.
- Treat missing metrics as unknown, never as zero.
- Never claim complete keyword coverage solely from seed ASINs or four head competitors.
- Keep product inclusion/exclusion logic in `amazon-product-data-mining`.
- Treat every Amazon marketplace, language, currency, and observation period as an isolated keyword project.

## Upstream dependency

Prefer the `正式产品池` worksheet produced by `amazon-product-data-mining`.

Accept these canonical fields when present:

- ASIN, brand, title, sales, revenue, price, listing age.
- Product form, signal path, core specifications, and verification status.
- Source query and source-file lineage.

If no verified product pool exists:

1. Ask for product sales exports or run `amazon-product-data-mining`.
2. If the user wants to proceed anyway, label the result `探索性词库`.
3. Do not use unverified products to claim market-wide coverage.

Read [references/input-contract.md](references/input-contract.md) before mapping files.
Read [references/marketplace-adaptation.md](references/marketplace-adaptation.md) when working outside the original marketplace or comparing sites.

## Workflow

### 1. Select keyword-source ASINs from the formal pool

Build a stratified ASIN set, not only a top-sales list:

- Head links by sales and revenue.
- Mainstream products by price and feature configuration.
- New challengers with meaningful sales velocity.
- Premium or differentiated products.
- Extension forms such as splitter, switch, or matrix variants.
- Long-tail products contributing distinct use cases or vocabulary.

Record the selection layer and reason for every ASIN. Weight keyword evidence by sales relevance without allowing one dominant link to define the entire vocabulary.

### 2. Export reverse-ASIN keywords efficiently

Batch ASINs when the source tool supports it. Prefer one representative batch per product layer over one export per ASIN.

When an authorized SellerSprite session is already open, operate it directly and export the required batches. Do not ask the user to upload reverse-ASIN files by default. If direct access or export is blocked, give the user the exact ASIN batches, required fields, marketplace, and period, then request only those exports. Never request credentials or authentication secrets.

Collect, where available:

- Natural keywords and ranks.
- Sponsored keywords and ranks.
- Search volume, its period and source definition, purchase volume, conversion rate, CPC, SPR.
- SellerSprite's displayed supply-demand ratio and its displayed supply count or competing-product basis.
- Competing products, title density, click concentration, and trend.

Keep the export period, marketplace, source tool, and filename.

### 3. Normalize and retain lineage

- Preserve every source row in `源数据`.
- Keep original and normalized keyword values.
- Normalize case, whitespace, punctuation, obvious encoding errors, and equivalent singular/plural forms.
- Do not merge semantically different phrases merely because they share tokens.
- Attach source ASIN, product layer, source type, source file, worksheet, and row number.

### 4. Classify relevance and intent

Assign one primary class:

- 核心大词
- 精准产品词
- 功能/规格词
- 接口/兼容词
- 使用场景词
- 问题解决词
- 竞品/品牌词
- 泛流量词
- 无关词

Also assign funnel stage and deployment eligibility: organic, advertising, both, observation, or exclusion.

Use the verified product definition and formal-pool attributes to judge relevance. Do not redefine the product boundary here.

### 5. Aggregate evidence

Aggregate normalized keywords while retaining all source ASINs and files. Calculate when fields exist:

- Covering ASIN count and weighted sales coverage.
- Natural-ranking and sponsored-ranking evidence.
- Search and purchase volume, conversion rate, and trend.
- CPC, competing products, title density, SPR, concentration, and SellerSprite supply-demand ratio.
- First-party PPC clicks, orders, sales, ACOS, and search-term conversion.

Designate the product's `core demand keywords` from verified relevance, purchase intent, multi-ASIN coverage, and conversion evidence. Output each core term's own search volume. Also output a clearly labeled core-term search-volume sum when useful, but state that keyword audiences can overlap and the sum is a demand index rather than deduplicated shopper demand.

Preserve SellerSprite's supply-demand ratio as a source metric. Do not silently recompute or replace it with `search volume / product count`, because SellerSprite's displayed denominator and period may differ. Record the source definition, marketplace, period, and export date. If the field is absent, leave it unknown unless the user explicitly requests a separately labeled calculated proxy.

### 6. Score and rank

Read [references/ranking-model.md](references/ranking-model.md).

Keep visible component scores for relevance, demand, conversion, competition accessibility, market coverage, and bid efficiency. Add a confidence grade. Do not calculate a high-confidence overall score when critical evidence is missing.

Create a separate `高转化优先级` based primarily on observed orders, conversion rate, purchase volume, and multi-ASIN organic/sponsored rank evidence. Do not label a keyword high-conversion from search volume or CPC alone.

### 7. Test vocabulary coverage

Measure:

- Incremental relevant keywords contributed by each ASIN batch.
- Weighted sales coverage of the selected ASINs.
- Coverage across product forms, price bands, features, listing ages, and product layers.
- Stabilization of relevant core terms.

Mark `核心词库基本稳定` only when marginal relevant contribution has flattened under a documented threshold. Otherwise mark `待扩展` and name the missing layer.

### 8. Produce exactly two worksheets

Unless the user requests otherwise:

1. `源数据`
2. `关键词排序`

Follow [references/output-contract.md](references/output-contract.md). Keep formulas or calculation notes visible.

Ensure the ranking worksheet exposes a stable downstream interface for `amazon-product-analysis`: core-demand-keyword flag, search volume, search-volume period, SellerSprite supply-demand ratio, CPC, conversion evidence, relevance, confidence, and calculation notes.

### 9. Recommend deployment

When budget, margin, target ACOS, and product positioning are provided, classify terms into:

- Organic position priorities.
- Exact-match advertising priorities.
- Phrase/broad discovery terms.
- Product-targeting or competitor terms.
- Negative keyword candidates.
- Deferred observation terms.

State CPC period, conversion assumptions, economic constraints, and confidence before recommending bids or budget allocation.

## Quality gate

- Reconcile source rows, normalized keywords, and unique-keyword counts.
- Confirm every keyword traces to source ASINs and files.
- Confirm source ASINs belong to the formal product pool or are explicitly marked exploratory.
- Confirm keyword language, search-volume source, CPC currency, and marketplace all match.
- Confirm search-volume period and SellerSprite supply-demand-ratio definition are retained and not silently inferred.
- Verify excluded terms remain traceable.
- Check formulas, units, currency, percentage scales, and missing-value handling.
- State coverage status, gaps, and the next most valuable ASIN layer or data source.
