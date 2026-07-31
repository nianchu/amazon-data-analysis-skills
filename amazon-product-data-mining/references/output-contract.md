# Output contract

## Worksheet: 正式产品池

Include all canonical source fields, final identity status, verified product form, verified signal path, product-specific specifications, identity evidence, source URLs, evidence level, and verification batch.

Only `正式合格` products belong here.

## Worksheet: 产品定义与准入规则

Include the positive product definition, hard gates, allowed extensions, exclusion boundaries, evidence requirements, and interpretation of blank or conflicting fields.

## Worksheet: 整合源数据

Include every unique ASIN exactly once:

- All canonical source fields.
- Matched-query and file lineage.
- Preliminary classification and final identity status.
- Verified product form and signal path.
- Specification columns.
- Exclusion reason or verification evidence.
- Amazon Listing URL, auxiliary evidence URL, evidence level, and batch.

Use `待深度核验` when the current evidence cannot prove or disprove the product identity. Do not relabel this state as an exclusion.

## Delivery notes

State source files and queries; raw, valid, duplicate, and unique counts; formal, pending, excluded, and conflict counts; title/metric conflicts across duplicate observations; evidence level; known limitations; and recommended next verification.

Require the reconciliation:

`unique ASINs = integrated rows = formal + pending + excluded + conflicts`
