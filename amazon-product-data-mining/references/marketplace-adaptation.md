# Marketplace adaptation

Support any Amazon marketplace, including North America, Europe, Japan, Australia, India, the Middle East, and other available sites.

## Isolation rules

Treat each marketplace as a separate analytical dataset:

- Marketplace/domain.
- Listing language.
- Currency and tax display.
- Observation period and timezone.
- Search-query language.
- Category taxonomy.
- Compliance regime.

Do not transfer sales, BSR, price, review counts, keyword volume, CPC, or conversion metrics across marketplaces.

## Localization rules

- Preserve original Listing text and add translated/normalized fields separately.
- Normalize decimal separators, date formats, units, and currencies without overwriting source values.
- Build local-language search queries; include English terms only when shoppers in that marketplace demonstrably use them.
- Rebuild the product pool per marketplace because availability and adjacent-product contamination differ by site.
- Keep EU marketplaces separate by country even when regulations overlap.

## Comparable cross-market analysis

When comparison is requested:

- Align observation periods.
- Convert currencies using a stated rate and date.
- Keep original and converted prices.
- Compare normalized metrics only after reconciling tax inclusion and source definitions.
- Label marketplace-specific compliance, seasonality, and language effects.
