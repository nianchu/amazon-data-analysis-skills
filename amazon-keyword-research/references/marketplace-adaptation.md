# Marketplace adaptation

Build a separate keyword universe for each Amazon marketplace.

## Local-market rules

- Use the marketplace's shopper language and domain.
- Preserve original keyword text; store translations separately.
- Keep local search volume, CPC, competition, conversion, and rank observations isolated.
- Preserve local currency and period definitions.
- Normalize accents, punctuation, grammatical variants, and compound-word forms according to the local language.
- Do not translate a successful US keyword list and treat it as validated European or Japanese demand.

## European marketplaces

Treat UK, Germany, France, Italy, Spain, Netherlands, Sweden, Poland, Belgium, and other sites separately:

- Shopper language and vocabulary differ.
- CPC, competition, VAT display, and category structure differ.
- The same ASIN may have different rank, price, and keyword coverage.

Build each local formal product pool with `amazon-product-data-mining`, then mine local reverse-ASIN and advertising data.

## Cross-market comparison

Only compare after:

- Aligning periods.
- Labeling language and marketplace.
- Converting CPC/currency with a stated rate and date.
- Separating original metrics from normalized comparison fields.
- Keeping local conversion evidence and confidence visible.
