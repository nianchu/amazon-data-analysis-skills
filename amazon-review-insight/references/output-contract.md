# Output Contract

## Evidence gate

Before any percentage table, state whether review-level text is available, the number of deduplicated reviews, ASIN coverage, rating mix, date range, and sampling method. If review text is absent, output a preliminary scenario/pain-point evidence table without theme percentages and explicitly state what must be collected for quantification.

Produce these tables:

1. `review_source`: one row per captured review with source metadata and deduplication status.
2. `review_theme_detail`: one row per review-theme pair with taxonomy, sentiment, severity, scenario, and evidence.
3. `theme_summary`: theme, review count, analyzed-review share, affected-ASIN count/share, rating mix, recent share, severity, fixability, confidence, and representative paraphrase.
4. `scenario_pain_map`: user, source, display, audio equipment, connection path, desired outcome, pain point, current workaround, unmet need, and opportunity.
5. `improvement_backlog`: proposed requirement, source themes, priority score, technical validation, commercial value, risk, confidence, and acceptance test.
6. `listing_claim_gap`: Listing claim, supporting positive evidence, contradicting evidence, expectation-gap risk, and recommended copy or product change.

Every percentage must state its denominator and sampling method. Include raw counts beside percentages. Preserve URLs for auditability.
