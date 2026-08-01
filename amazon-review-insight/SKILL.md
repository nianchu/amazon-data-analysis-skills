---
name: amazon-review-insight
description: Analyze Amazon product Listings and review-level data to identify customer use scenarios, praised attributes, complaints, compatibility failures, unmet needs, and evidence-backed product improvements. Use when Codex must turn a validated Amazon product pool into structured review-theme tables, scenario-pain-point maps, improvement requirements, or inputs for an Amazon product-entry report. Do not use this skill to qualify the product pool, rank keywords, calculate market size, or provide legal clearance.
---

# Amazon Review Insight

Analyze only products accepted by `amazon-product-data-mining`. Keep Listing claims, review evidence, and analyst inference separate.

## Workflow

1. Read [references/input-contract.md](references/input-contract.md) and inventory the product and review data.
2. Build a stratified ASIN sample across sales tier, price band, brand, product form, lifecycle, and feature bundle. Include all designated core competitors.
3. Capture Listing evidence: title, bullets, A+, images, video, compatibility claims, connection diagrams, warranty, and stated use cases.
4. Capture review-level evidence where authorized: ASIN, rating, date, variation, title, text, verified-purchase flag, helpful votes, and source URL.
5. Normalize and deduplicate reviews. Never treat blank text, repeated syndication, seller responses, or quoted manuals as independent customer evidence.
6. Apply the taxonomy in [references/theme-taxonomy.md](references/theme-taxonomy.md). Allow multiple themes per review but count each review once per theme.
7. Produce the outputs in [references/output-contract.md](references/output-contract.md).
8. Reconcile theme counts to the analyzed-review denominator and label sampling limitations.

## Evidence Rules

- Label direct Listing content `Listing claim`.
- Label a paraphrased customer statement `Review evidence` and retain ASIN, rating, date, and URL.
- Label a cross-source interpretation `Supported inference`; state alternative explanations and confidence.
- Do not quote long review passages. Use short paraphrases.
- Do not infer feature absence from a blank Listing field.
- Do not claim that review frequency equals defect rate or return rate.
- Separate product defects, compatibility constraints, expectation gaps, installation errors, logistics damage, and customer service.
- Suppress percentages when the denominator is too small; show the raw count and low confidence instead.
- When review-level text has not been collected, produce only a clearly labeled preliminary evidence/hypothesis table from available Listing and public evidence. Do not calculate positive/negative theme shares.
- Keep `product sales/Listing dataset complete` separate from `review-level corpus available`; the absence of the latter does not make the formal product pool incomplete.

## Sampling Minimums

- Target at least 20 reviews per core ASIN when available.
- Include recent and older reviews, positive and negative ratings, and relevant variations.
- For market-level percentages, target at least 200 deduplicated reviews across at least 10 ASINs. Below this, label results exploratory.
- Oversample 1–3 star reviews for discovery, but calculate market percentages only with documented weighting or a representative sample.

## Improvement Logic

Convert a theme into a product requirement only when it is recurring, important, technically actionable, and consistent with the product definition. Score:

- frequency: 1–5;
- severity: 1–5;
- fixability: 1–5;
- commercial relevance: 1–5;
- evidence confidence: High, Medium, or Low.

Calculate `improvement priority = frequency × severity × fixability × commercial relevance`. Keep confidence outside the numeric score as a guardrail.

## Boundaries

- Send keyword questions to `amazon-keyword-research`.
- Send product qualification and Listing parameter extraction to `amazon-product-data-mining`.
- Send market sizing, profit, lifecycle, trend, and final opportunity scoring to `amazon-product-analysis`.
- Treat patent and mandatory compliance research as a separate legal/compliance workstream. This skill may surface review evidence of safety or certification concerns but must not give legal clearance.
