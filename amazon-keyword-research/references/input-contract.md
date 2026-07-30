# Input contract

## Project metadata

Record:

- Marketplace, language, currency, and analysis period.
- Export time, source tool, export type, and source filename.
- Upstream formal-product-pool filename and version.
- Product definition version.
- Selected keyword-source ASINs, product layer, and selection reason.

## Formal product pool

Prefer these fields:

| Field | Meaning |
|---|---|
| ASIN | Verified product identifier |
| Listing核验状态 | Must be `正式合格` for normal inclusion |
| 产品形态（核验后） | Standard or extension form |
| 信号路径（核验后） | Verified functional path |
| 品牌 | Brand |
| 商品标题 | Listing title |
| 月销量 | Current-period sales |
| 月销售额 | Current-period revenue |
| 价格 | Current price |
| 上架时间/上架天数 | Product age |
| 规格参数列 | Product-specific verified fields |

Do not silently include rows marked excluded, pending, or insufficient evidence.

## Keyword row mapping

Map source columns when available:

| Canonical field | Meaning |
|---|---|
| original_keyword | Exact source keyword |
| normalized_keyword | Cleaned aggregation key |
| source_asin | ASIN producing the observation |
| source_product_layer | Head, mainstream, challenger, premium, extension, or long-tail |
| source_type | Natural, sponsored, reverse-search, PPC, ABA, or other |
| natural_rank | Observed natural rank |
| sponsored_rank | Observed sponsored rank |
| search_volume | Search volume for the stated period |
| purchase_volume | Purchase volume for the stated period |
| conversion_rate | Source-defined conversion rate |
| cpc | CPC and currency |
| competing_products | Competing product count |
| title_density | Source-defined title density |
| spr | Source-defined launch/ranking estimate |
| trend | Search trend or period comparison |
| source_file | Exact filename |
| source_row | Original worksheet and row number |

Preserve unmapped source columns in `源数据`. Never invent unavailable values.
