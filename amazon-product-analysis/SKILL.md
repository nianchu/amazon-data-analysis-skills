---
name: amazon-product-analysis
description: Analyze a validated Amazon product pool and its historical sales, Listing parameters, reviews, keyword outputs, cost inputs, and compliance evidence to assess market size, trend, competition, lifecycle, seasonality, price and feature drivers, customer needs, profit, risk, and market-entry opportunity. Use when Codex must turn an already-qualified Amazon product dataset into a reproducible Excel analysis and an evidence-backed go/no-go recommendation for any Amazon marketplace. Do not use this skill to discover or qualify the product pool or to mine raw keywords.
---

# Amazon Product Analysis

Analyze only the product universe accepted by the upstream product-data-mining workflow. Preserve source data, make every calculation reproducible, and separate observed facts, estimates, assumptions, and recommendations.

## Boundaries

- Treat `amazon-product-data-mining` as the owner of product definition, ASIN qualification, deduplication, and Listing parameter extraction.
- Treat `amazon-keyword-research` as the owner of keyword discovery, ranking, conversion, CPC, and placement strategy inputs.
- Never silently add an excluded or unresolved ASIN to market calculations.
- Do not reinterpret missing values as `No`, zero, or unsupported.
- Treat a blank Listing-derived parameter as `Listing未披露`. Do not call it incomplete product-pool data, ask the user to fill it, or infer a value from another ASIN.
- Do not present SellerSprite estimates, sampled reviews, trend indices, or inferred costs as audited facts.
- Do not claim that correlation proves a feature caused sales.

## Workflow

1. Read [references/input-contract.md](references/input-contract.md) and inventory the supplied datasets.
2. Ask the user for missing product-cost and operating inputs listed in the input contract before running profit, CPC-tolerance, or launch-budget calculations. Do not silently assume commercially material values.
3. Run the data-quality gate before analysis. Stop affected modules when required fields or time coverage are inadequate, while continuing modules that remain valid.
4. Create a metric dictionary and freeze denominators, date windows, marketplace, currency, parent/child treatment, and status filters.
5. Read [references/analysis-workflow.md](references/analysis-workflow.md) and execute only supported modules.
6. Read [references/decision-framework.md](references/decision-framework.md) before scoring market-entry opportunity.
7. Read [references/output-contract.md](references/output-contract.md) and create the final workbook.
8. Recalculate key totals independently, inspect formulas and charts, and reconcile all summary values to the formal product pool.
9. Verify the visible worksheet order: decision and analysis sheets first; every calculation base, formal product pool, integrated source, and period source sheet last.

## Required Analysis Principles

- Use child-ASIN rows for market-unit and revenue aggregation unless the input contract explicitly defines another grain.
- Deduplicate only by the declared key. Never combine parent and child estimates without a documented rule.
- Keep time comparisons like-for-like: same marketplace, keyword/product scope, period length, currency, and metric provider.
- Use mutually exclusive lifecycle cohorts for totals; cumulative views may be supplementary.
- Build price bands from the observed distribution first, then add commercially meaningful bands if useful.
- Weight both unit share and revenue share. Report listing count separately so assortment share is not confused with demand share.
- For feature comparisons, disclose sample size and missingness for every group. Suppress or flag unstable groups.
- Require at least 24 monthly observations to make a confident seasonality claim; otherwise label it preliminary.
- Tie every conclusion to a workbook table, formula, source field, or cited external source.
- Import core-keyword search volume and SellerSprite supply-demand ratio from `amazon-keyword-research`; do not independently redefine or silently recalculate them.
- Separate observed competitor evidence from inferred operating tactics. Assign a confidence level and plausible alternative explanation to every inference.

## Decision Output

Conclude with one of:

- `建议切入`
- `有条件切入`
- `暂缓切入`
- `数据不足，无法判断`

State the target segment, recommended specification, price position, operational approach, profit sensitivity, principal risks, missing evidence, and next validation experiment. A numeric score supports the decision but never overrides a critical compliance, patent, margin, or data-quality blocker.

## Quality Gate

Before delivery, confirm:

- formal-pool ASIN count equals the analysis base after documented exclusions;
- units and revenue reconcile between source, calculation sheets, pivots, charts, and executive summary;
- period-over-period calculations use comparable windows;
- lifecycle cohorts are exhaustive and non-overlapping;
- 30/60/180-day new-product windows are explicitly labeled cumulative, and `New Release` counts come only from an actual platform flag rather than product age;
- feature groups do not convert blanks into negative values;
- review percentages state the denominator and sampling method;
- review themes without review-level text are labeled preliminary and never receive invented percentages;
- profit includes all known cost categories and exposes assumptions;
- opportunity conclusions distinguish evidence from inference;
- the workbook retains untouched source sheets and a calculation audit trail.
- all product-pool and source-data sheets appear after every reader-facing analysis sheet.
