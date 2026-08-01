# Input Contract

## Required

- validated formal product pool with ASIN, product form, price band, lifecycle, sales tier, and key feature bundle;
- marketplace and observation date;
- Listing URLs and captured Listing content;
- review-level rows with ASIN, rating, date, review title, review text, and source URL.

## Recommended

- verified-purchase flag, variation, helpful votes, review images/video, seller response;
- review count and rating at extraction time;
- designated market leader, closest substitute, and recent entrant;
- language and country metadata;
- return-reason or customer-service data when available.

## Data-quality gate

Profile duplicates, blanks, language, rating distribution, recency, ASIN coverage, variation coverage, and sampling bias. Mark market-level theme shares `data insufficient` when the sample is too narrow or intentionally negative-review-heavy without weighting.

