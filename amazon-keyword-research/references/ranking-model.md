# Ranking model

## Principles

1. Rank opportunity, not search volume alone.
2. Keep demand, conversion, competition, cost, and relevance as separate visible components.
3. Normalize metrics within the current marketplace and product project.
4. Winsorize or log-transform highly skewed volume and competition fields before min-max scoring.
5. Treat missing values as unknown, not zero.
6. Reduce confidence when evidence comes from few ASINs or a single source.

## Default component model

Use a 0–100 scale:

- Relevance: 25%
- Demand: 20%
- Conversion evidence: 20%
- Competition accessibility: 15%
- Market coverage: 10%
- Bid efficiency: 10%

`Opportunity = 0.25R + 0.20D + 0.20V + 0.15A + 0.10M + 0.10B`

This is a starting model, not a universal truth. Reweight only after documenting the product stage, objective, and available fields.

### Relevance

Combine product-job match, form match, compatibility match, and purchase-intent specificity. Hard-excluded terms receive no opportunity score.

### Demand

Use transformed search or purchase volume and trend. Avoid allowing one head term to dominate solely because of scale.

### Conversion evidence

Prefer first-party orders and conversion rate. Otherwise use source purchase rate, multiple-ASIN rank evidence, or other clearly labelled proxies.

### Competition accessibility

Score higher when ranking difficulty, competing products, title density, click concentration, and dominant-ASIN strength are lower. Keep the original competition metrics visible.

### Market coverage

Score based on the number and weighted share of relevant competitor ASINs associated with the term. Weight evidence from representative competitors more than irrelevant or fringe links.

### Bid efficiency

Compare CPC with economic value. When unit economics are absent, treat CPC as a relative cost signal and lower confidence.

## Confidence grade

- A: multiple independent sources, broad competitor coverage, and no critical missing component.
- B: good multi-ASIN evidence with one non-critical component missing.
- C: limited ASIN/source coverage or reliance on proxy conversion evidence.
- D: sparse or contradictory evidence; keep for observation rather than action.

## Strategy labels

- Core defend/build: high relevance, high demand, strong conversion evidence.
- Exact test: high relevance and acceptable cost with sufficient confidence.
- Long-tail capture: strong relevance/conversion but lower demand.
- Discovery: plausible relevance with weak evidence; use controlled phrase/broad tests.
- Organic first: expensive CPC but strong strategic relevance.
- Advertising first: attainable paid placement while organic evidence is weak.
- Negative candidate: irrelevant or repeatedly costly without conversion.

