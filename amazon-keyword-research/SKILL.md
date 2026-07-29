---
name: amazon-keyword-research
description: Build, clean, classify, score, and rank an Amazon product keyword universe from seed ASINs, competitor layers, SellerSprite keyword-reverse-search exports, product-search exports, and optional advertising data. Use when Codex needs to discover natural and sponsored keywords, judge keyword coverage, select additional competitor ASINs, produce a source-data plus keyword-ranking Excel workbook, or recommend organic and advertising keyword priorities for an Amazon marketplace.
---

# Amazon Keyword Research

Create a traceable Amazon keyword universe that can be used independently or passed to a larger market-analysis workflow.

## Operating boundaries

- Keep account credentials, cookies, API keys, verification codes, and seller identity data out of the skill and its outputs.
- Treat every product and marketplace as a separate project. Never reuse a prior project's rows unless the user explicitly supplies them as an input.
- Keep raw exports unchanged. Write cleaned and calculated data to a new workbook.
- State whether the result is a sampled market vocabulary or a near-complete vocabulary. Never claim complete coverage without passing the coverage checks.
- Separate source observations from calculated scores and analyst judgments.

## Required inputs

Accept one or more of:

- Seed ASINs and marketplace.
- Product sales/search-result exports used to construct competitor layers.
- Keyword reverse-search exports for the selected ASINs.
- Optional PPC search-term, campaign, Brand Analytics, or historical keyword exports.

Before processing, record the marketplace, observation period, export time, source tool, currency, and file list. Read [references/input-contract.md](references/input-contract.md) for required field mapping.

## Workflow

### 1. Define the product boundary

Describe the product's core job, required physical form, key compatibility conditions, and exclusions. Use these rules to remove keyword-matched but functionally different products.

If exclusions are uncertain, retain borderline products with `相关性状态=待复核`; do not silently delete them.

### 2. Build competitor layers

When sales data is available, select competitors across all material market layers:

- Head links: highest sales or revenue.
- Mainstream links: representative price, features, and sales.
- New challengers: recently listed products with meaningful sales velocity.
- Premium or differentiated links: high-price or distinctive-feature products.
- Long-tail links: lower-volume products that introduce unique use cases or vocabulary.

Prefer vocabulary coverage over selecting only the highest-selling links. Record the selection reason for every ASIN.

### 3. Ingest and normalize keyword rows

- Preserve every source row in `源数据`.
- Normalize case, surrounding spaces, punctuation variants, singular/plural variants, and obvious encoding artifacts.
- Keep both the original keyword and normalized keyword.
- Do not merge semantically different terms merely because they share tokens.
- Attach source ASIN, source type, marketplace, period, and source filename.

### 4. Classify intent

Classify each normalized keyword into one primary group:

- 核心大词
- 精准产品词
- 功能/规格词
- 接口/兼容词
- 使用场景词
- 问题解决词
- 竞品/品牌词
- 泛流量词
- 无关词

Also label funnel stage, relevance, and whether the term is suitable for organic ranking, advertising, both, observation only, or exclusion.

### 5. Aggregate evidence

Aggregate duplicate normalized keywords while retaining source lineage. Calculate, where fields exist:

- Number and share of source ASINs covering the keyword.
- Natural-ranking and sponsored-ranking evidence.
- Search volume and trend.
- Purchase volume, conversion rate, click concentration, title density, competing products, SPR, and CPC.
- Sales contribution or PPC orders from first-party advertising data.

Never treat missing values as zero. Use explicit missing-data flags.

### 6. Score and rank

Read [references/ranking-model.md](references/ranking-model.md). Produce separate component scores for:

- Relevance.
- Demand.
- Conversion evidence.
- Competition difficulty.
- Bid cost.
- Market coverage.
- Strategic fit.

Keep the component scores visible. Calculate an overall opportunity score only when minimum evidence requirements are met. Add a confidence grade so a high score based on sparse data is not mistaken for a reliable conclusion.

### 7. Test coverage

Evaluate coverage by:

- Incremental unique keywords contributed by each additional ASIN.
- Share of material sales represented by selected competitors.
- Coverage of product forms, prices, features, ages, and market layers.
- Stabilization of core relevant vocabulary after successive ASIN batches.

Mark the vocabulary `待扩展` when important layers are absent or new ASIN batches still contribute substantial relevant core terms. Mark it `核心词库基本稳定` only when the marginal relevant contribution has materially flattened; explain the threshold used.

### 8. Produce the workbook

Default to exactly two worksheets unless the user asks otherwise:

1. `源数据`: source-preserving rows plus normalized fields and lineage.
2. `关键词排序`: one row per normalized keyword with evidence, component scores, overall score, confidence, strategy labels, and calculation notes.

Follow [references/output-contract.md](references/output-contract.md). Put formulas or auditable calculation descriptions in the workbook. Do not hide ranking logic in prose.

### 9. Recommend keyword deployment

When budget and product positioning are supplied, segment keywords into:

- Organic position priorities.
- Exact-match advertising priorities.
- Phrase/broad discovery terms.
- Product-targeting or competitor terms.
- Negative keyword candidates.
- Deferred observation terms.

Do not recommend bids or budget allocation without stating the CPC source period, conversion assumptions, target ACOS, and confidence.

## Quality gate

Before delivery:

- Reconcile source row counts and unique keyword counts.
- Confirm excluded rows remain traceable.
- Check formulas, units, percentages, currencies, and missing-value handling.
- Verify that rankings change for defensible reasons rather than missing data.
- State known gaps, coverage status, and the next most valuable data to add.
- Keep project-specific conclusions outside the reusable skill folder.

