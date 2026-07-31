---
name: amazon-product-data-mining
description: Define any Amazon product by its unique functional identity, merge and deduplicate all product-search or sales exports, audit every unique ASIN, verify ambiguous identities from Listing titles, images, bullets, A+, manuals, and product pages, extract product-specific specifications, and produce a defensible formal product pool plus integrated source-data workbook for any Amazon marketplace. Use before keyword research, market sizing, competitive analysis, or product opportunity analysis whenever Codex must determine which ASINs truly belong to a target market or recheck a pool for false inclusions and exclusions.
---

# Amazon Product Data Mining

Create a verified Amazon product pool before calculating market size or mining competitor keywords.

## Boundaries

- Never store credentials, cookies, API keys, verification codes, or seller identity data.
- Treat every marketplace, product, and observation period as a separate project.
- Preserve raw exports and source lineage.
- Define the product by function and signal path, not by title keywords or category alone.
- Do not place a product in the formal pool until the required functional gates are proven.
- Never treat missing evidence as negative evidence. Use `待深度核验` until a Listing-level check proves inclusion or exclusion.
- Exclude only with explicit reverse evidence, such as the wrong signal direction, missing indispensable output, or a different core job.
- Leave a specification blank when the current ASIN Listing does not explicitly state it.
- Keep keyword discovery and scoring in `amazon-keyword-research`.
- Support every Amazon marketplace; never mix marketplaces, languages, currencies, or observation periods in one product pool.

## Required inputs

Accept marketplace, observation period, several core search terms, product sales/search exports, optional seed ASINs, and optional positive or negative examples.

Record source filename, query term, marketplace, domain, language, period, export time, currency, and row count. Read [references/input-contract.md](references/input-contract.md) and [references/marketplace-adaptation.md](references/marketplace-adaptation.md).

## Workflow

### 1. Merge sales exports

- Preserve all original columns.
- Add source query, source file, and source-row lineage.
- Validate ASIN format.
- Deduplicate by ASIN before sales or revenue calculations.
- Select the most complete row as canonical while retaining every matched query and file.
- Never sum duplicate ASIN sales across search-query exports.
- Reconcile source-row count, valid-ASIN count, duplicate rows beyond first, unique ASIN count, and integrated-table count.
- Detect same-ASIN title conflicts and metric snapshot conflicts across exports.
- Mark placeholder or suspicious sentinel values; do not let them improve completeness scoring.
- Keep one actual source observation as canonical. Never average, sum, or invent conflicting marketplace metrics.

### 2. Define the product before excluding products

Write the core job, target user/scene, required input or starting state, required output or end state, indispensable mechanism/form, allowed extensions, and adjacent products that must remain distinguishable.

Read [references/product-definition-framework.md](references/product-definition-framework.md) and translate the definition into auditable gates.

Load a product-specific case reference only when it matches the current product. The HDMI audio extractor file is an example and must not be reused as a universal schema: [references/hdmi-audio-extractor-definition.md](references/hdmi-audio-extractor-definition.md).

Do not create an exclusion list first. Establish the positive definition, then test every candidate against it.

### 3. Run title-level triage

Use title and downloaded attributes only to prioritize:

- Strong candidate.
- Strong non-target.
- Borderline/needs Listing verification.

Title triage is not final product identity and must never be the only reason for a borderline exclusion. Retain every row in integrated source data.

### 4. Verify product identity

Audit every unique ASIN against the positive gates. For obvious non-targets, record the explicit reverse evidence. For every ambiguous or contradictory ASIN, query the current Listing and capture required input evidence, retained output/pass-through evidence, independent extracted output evidence, extraction/de-embedding evidence, conversion direction, product form, evidence URL, and evidence position.

Use this evidence order:

1. Interface or connection diagram in Listing images.
2. Listing bullets and product description.
3. A+ content.
4. Manufacturer specification sheet or manual.
5. Manufacturer/authorized product page.
6. Title and downloaded attributes only as low-confidence evidence.

Classify as `正式合格`, `已排除`, `待深度核验`, or `证据冲突`.

Use current-ASIN Listing content where accessible. If Amazon is unavailable, use manufacturer or authorized product documentation and record the URL. If only title and downloaded attributes are available, leave the ASIN pending rather than implying full-page verification.

Read [references/full-pool-audit.md](references/full-pool-audit.md) before finalizing a pool or rechecking an allegedly undersized pool.

### 5. Extract product-specific Listing parameters

Infer a new compact parameter schema for every product from repeated Listing attributes, purchase-decision variables, and the product's unique mechanism. Confirm it with the user when practical.

- Keep one analytical column per parameter.
- Use controlled values suitable for pivot tables.
- Allow multi-select values in one cell only where required.
- Do not infer one field from another.
- Do not copy specifications between ASINs.
- Record conflicts rather than choosing the more favorable claim.

Read [references/listing-parameter-contract.md](references/listing-parameter-contract.md). Treat the HDMI field list as one example, not the default for other products.

### 6. Build the formal pool

Include only products satisfying every hard gate. Keep extension forms, such as splitter, switch, or matrix products with the core function, but classify their form separately.

Do not calculate market capacity from pending or excluded rows.

Before finalizing, run a second-pass contradiction audit:

- Formal rows with wrong-direction terms, ARC/eARC-only behavior, or no independent output.
- Excluded rows whose evidence shows all hard gates.
- Products with the same model/form but inconsistent statuses.
- ASINs whose current Listing identity differs from the downloaded title.
- Any unresolved ASIN must remain pending; do not force a complete status distribution.

### 7. Produce exactly three worksheets

Unless the user requests otherwise:

1. `正式产品池`
2. `产品定义与准入规则`
3. `整合源数据`

Follow [references/output-contract.md](references/output-contract.md).

### 8. Hand off downstream

- Pass `正式产品池` ASINs to `amazon-keyword-research`.
- Pass the formal pool and specification columns to market, competition, lifecycle, pricing, and feature analysis.
- Keep excluded rows for contamination audits.

## Quality gate

- Reconcile every source file and query, then raw, valid, duplicate, unique, formal, pending, excluded, and conflict counts.
- Confirm `source unique ASINs = integrated source rows = formal + pending + excluded + conflicts`.
- Confirm no ASIN appears more than once in integrated source data.
- Confirm known counterexamples remain excluded.
- Confirm formal products have evidence for every hard gate.
- Confirm exclusions cite explicit reverse evidence rather than missing keywords.
- Confirm every ambiguous ASIN received Listing-level or manufacturer-level verification.
- Confirm cross-query title and metric conflicts are recorded and the canonical row is an actual source observation.
- Confirm blank specifications mean “not explicitly found,” not “unsupported.”
- Confirm output contains exactly the three contracted worksheets.
- State the evidence level and products requiring deeper verification.
- Confirm the product-specific definition and schema were created for the current product rather than inherited from an earlier project.
- Confirm marketplace, language, currency, and period are consistent across the pool.
