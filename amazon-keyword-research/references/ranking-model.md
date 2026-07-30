# Ranking model

## Principles

1. Rank opportunity, not search volume alone.
2. Keep demand, conversion, competition, cost, relevance, and coverage visible.
3. Normalize within the current marketplace and project.
4. Transform highly skewed volume and competition fields before min-max scoring.
5. Treat missing values as unknown, not zero.
6. Reduce confidence when evidence comes from few formal-pool ASINs or one source.

## Default model

Use a 0-100 scale:

- Relevance: 25%
- Demand: 20%
- Conversion evidence: 20%
- Competition accessibility: 15%
- Market coverage: 10%
- Bid efficiency: 10%

`Opportunity = 0.25R + 0.20D + 0.20V + 0.15A + 0.10M + 0.10B`

Document any change to these weights.

### Relevance

Combine product-job match, product-form match, compatibility match, and purchase-intent specificity. Hard-excluded terms receive no opportunity score.

### Demand

Use transformed search or purchase volume and trend. Prevent one head term from dominating solely because of scale.

### Conversion evidence

Prefer first-party orders and conversion rate. Otherwise use source purchase rate, multi-ASIN rank evidence, or clearly labeled proxies.

### Competition accessibility

Score higher when ranking difficulty, competing products, title density, click concentration, and dominant-ASIN strength are lower.

### Market coverage

Use both covering-ASIN count and weighted formal-pool sales coverage. Weight representative products more than fringe links.

### Bid efficiency

Compare CPC with economic value. Without unit economics, use CPC only as a relative cost signal and reduce confidence.

## Confidence grade

- A: multiple independent sources, broad formal-pool coverage, and no critical missing component.
- B: good multi-ASIN evidence with one non-critical component missing.
- C: limited ASIN/source coverage or proxy conversion evidence.
- D: sparse or contradictory evidence; observation only.

## Strategy labels

- Core defend/build.
- Exact test.
- Long-tail capture.
- Discovery.
- Organic first.
- Advertising first.
- Negative candidate.
