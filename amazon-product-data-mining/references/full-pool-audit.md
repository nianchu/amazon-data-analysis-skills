# Full product-pool audit

Run this audit after initial classification and whenever the resulting pool appears too large or too small.

## 1. Reconcile ingestion

For every source export, record filename, query, raw rows, valid ASIN rows, and schema.

Calculate:

- Total source rows.
- Valid-ASIN rows.
- Unique ASINs.
- ASINs appearing in multiple query exports.
- Integrated rows.
- Formal, pending, excluded, and conflict rows.

Require:

`unique ASINs = integrated rows = formal + pending + excluded + conflicts`

Do not drop an ASIN because it appears irrelevant. Retain it in integrated source data with an auditable exclusion reason.

## 2. Audit deduplication

- Use ASIN as the product-pool grain.
- Preserve every matched query and source filename.
- Compare titles and important metrics across duplicate observations.
- Keep one real source observation as canonical.
- Never sum sales or revenue from repeated keyword hits.
- Treat blanks, error codes, and suspicious repeated sentinel values as missing when scoring row completeness.
- Record material title conflicts because an ASIN may have been repurposed or the export may be stale.

## 3. Audit identity row by row

For each unique ASIN, answer:

1. What is the starting input/state?
2. What output or function must remain?
3. What independent output/result is created?
4. What mechanism performs the target job?
5. Does the direction match the product definition?
6. Is it a core product, allowed extension, adjacent product, accessory, or bundle?

Use the positive definition first. Do not build a growing ASIN blacklist.

## 4. Evidence rules

Evidence priority:

1. Interface or connection diagram.
2. Listing bullets and description.
3. A+ content.
4. Manufacturer manual/specification.
5. Manufacturer or authorized product page.
6. Title/downloaded attributes.

Record URL, evidence position, observed statement, evidence level, and verification date/batch.

- Missing evidence → `待深度核验`.
- Explicit proof of every hard gate → `正式合格`.
- Explicit reverse evidence → `已排除`.
- Materially contradictory sources → `证据冲突`.

Never convert “not stated” into “not supported.”

## 5. Contradiction tests

Review all formal rows for:

- Wrong input/output direction.
- Missing retained output or pass-through.
- Missing independent extracted output.
- ARC/eARC-only behavior when standard source input is required.
- Accessories, converters, embedders, extenders, capture devices, or unrelated jobs.

Review all excluded rows for:

- Explicit extraction/de-embedding.
- Required input and retained output.
- Independent output.
- Allowed splitter, switch, matrix, or other extension forms.

Group comparable models and ensure equivalent signal paths receive equivalent statuses.

## 6. Completion standard

Finish only when:

- Counts reconcile.
- Every unique ASIN has one final row.
- Every formal row proves all hard gates.
- Every exclusion has explicit reverse evidence.
- Every unresolved identity remains pending.
- Known positive, extension, and counterexample ASINs pass regression checks.
- The final workbook contains the required worksheets and preserves source lineage.
