# Input Contract

## Core inputs

Require:

1. Formal product pool from `amazon-product-data-mining`, with one declared row grain and qualification status.
2. Current-period sales dataset with ASIN, title, brand, price, estimated units, estimated revenue, first-available date, and marketplace.
3. Listing parameter columns relevant to the defined product.

Use when available:

- one or more comparable historical sales periods;
- monthly product sales history;
- Google Trends export and marketplace search-volume history;
- standardized output from `amazon-keyword-research`;
- review-level data with ASIN, rating, date, variation, text, and verified-purchase flag where available;
- product cost, package dimensions and weight, commission category/rate, fulfillment fee, freight, duty, tax, return and advertising assumptions;
- patent and compliance evidence.

## Grain and keys

Declare:

- whether each sales row is a child ASIN, parent ASIN, or Listing;
- whether variants share sales estimates;
- the unique key for each sheet;
- currency and exchange-rate date;
- observation window and provider.

Do not sum mixed grains. Preserve every original input sheet unchanged and create cleaned copies separately.

## Data-quality checks

Profile:

- row count, unique ASIN count, duplicate keys, blank rates, invalid dates, nonnumeric metrics, negative values, and currency conflicts;
- price × units versus supplied revenue, allowing for provider rounding and estimate methodology;
- extreme values and repeated sentinel/error values;
- overlap and scope differences between periods;
- missingness of every feature used in comparison.

Classify issues as:

- `blocking`: invalid analysis base, mixed grain, irreconcilable totals, or absent core metrics;
- `material`: may change a conclusion and must appear in limitations;
- `minor`: cosmetic or low-impact.

If data is insufficient for a module, mark that module `数据不足` rather than fabricating an answer.

## Required profit-input interview

When profit or launch economics are requested, ask the user for all unavailable items:

- marketplace, target price, currency, and exchange-rate assumption;
- unit product cost, packaging cost, labeling, inspection, and domestic freight;
- packed length, width, height, gross weight, and units per carton;
- first-leg method, volumetric divisor, volumetric-weight rate, actual-weight rate, duty or HS code, customs, insurance, and receiving cost;
- target inventory age and storage duration;
- return rate, recoverable-return share, replacement rate, and disposal loss;
- launch budget, daily ad budget, target ACOS, expected conversion rate, coupon/deal/Vine costs;
- MOQ, tooling, certification, creative, and other amortized launch costs;
- FBA or FBM fulfillment choice and any account-specific fee preview.

Fetch current public Amazon fee schedules when available, but label them estimates. Prefer the user's Seller Central revenue calculator or fee preview for product-specific referral, FBA, storage, inbound, return, and other account-dependent charges.
