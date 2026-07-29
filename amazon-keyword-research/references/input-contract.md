# Input contract

## Project metadata

Record:

- Marketplace and language
- Analysis period and export time
- Currency
- Source tool and export type
- Source filename
- Seed ASIN list
- Selected competitor ASIN list and selection reason
- Product inclusion and exclusion rules

## Keyword row mapping

Map source columns to these canonical fields when available:

| Canonical field | Meaning |
|---|---|
| original_keyword | Exact source keyword |
| normalized_keyword | Cleaned aggregation key |
| source_asin | ASIN producing the observation |
| source_type | Natural, sponsored, reverse-search, PPC, ABA, or other |
| natural_rank | Observed natural rank |
| sponsored_rank | Observed sponsored rank |
| search_volume | Search volume for the stated period |
| purchase_volume | Purchase volume for the stated period |
| conversion_rate | Purchases divided by searches/clicks according to source definition |
| cpc | CPC and currency |
| competing_products | Competing product count |
| title_density | Source-defined title density |
| spr | Source-defined launch/ranking estimate |
| trend | Search trend or period comparison |
| source_file | Exact filename |
| source_row | Original worksheet and row number |

Do not invent unavailable values. Preserve unmapped source columns in `源数据`.

## Product sales data

When used for competitor selection, retain at least:

- ASIN and parent/child relationship if available
- Brand and title
- Price
- Sales and revenue
- Review count and rating
- Listing date or age
- Category
- Source keyword/query

Deduplicate products before calculating market shares, but keep a lineage table or source markers showing every query that returned the ASIN.

