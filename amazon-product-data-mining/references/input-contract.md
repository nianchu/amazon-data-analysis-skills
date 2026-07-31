# Input contract

## Project metadata

Record the target product, marketplace code, Amazon domain, marketplace country, Listing language, analysis period, currency, export tool, export time, source query for each file, seed ASINs, and user-provided examples.

## Minimum product fields

Retain when available:

- ASIN and parent ASIN.
- Brand, title, detail URL, and image URL.
- Category and BSR.
- Sales, revenue, child sales, and child revenue.
- Price, reviews, rating, and listing age.
- Seller and fulfillment fields.
- Downloaded attributes, dimensions, and weight.
- Source query, filename, worksheet, and row.

## Data-quality rules

- Remove rows without a valid ASIN from the product table, but count them in the audit.
- Deduplicate by ASIN before market totals.
- Never add sales values from duplicate query hits.
- Preserve query/file lineage in delimited lineage columns.
- Mark placeholder, malformed, or suspicious values instead of silently accepting them.
- Treat repeated numeric sentinel/error values as missing for completeness scoring until their meaning is verified.
- Compare duplicate-ASIN titles and key metrics across source exports; record conflicts and preserve the selected source observation.
- Never merge ASIN observations from different marketplaces into one formal pool merely because the ASIN is identical.
- Normalize currency only in a separate calculated field; preserve the original marketplace currency.
