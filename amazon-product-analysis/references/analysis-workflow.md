# Analysis Workflow

## 1. Market capacity

Calculate for the selected formal product pool:

- unique child ASINs and active listings;
- estimated units and revenue for the period;
- average selling price: total revenue / total units;
- median price and weighted price;
- unit and revenue distribution across segments.

Label the result as an observed-provider estimate for the captured product universe, not total Amazon GMV.

## 2. Trend

Compare like-for-like periods using:

- units growth;
- revenue growth;
- ASP change;
- active-ASIN change;
- core-keyword search trend and marketplace search-volume trend.

Decompose revenue movement into unit and price/mix effects when supported. Explain universe changes separately.

Import approved core-demand keywords, individual search volumes, periods, CPC, and SellerSprite supply-demand ratio from `amazon-keyword-research`. Treat summed core-keyword search volume as an overlapping demand index, not unique shopper demand. Preserve SellerSprite's supply-demand value and definition without silent recalculation.

## 3. Competition

Calculate link-level and brand-level CR3, CR10, HHI, and the number of brands accounting for 50% and 80% of units/revenue.

Default interpretation from the user workflow:

- link concentration is high when CR3 exceeds 50% or CR10 exceeds 80%;
- brand concentration is high when top-10 brand share exceeds 70%.

Treat these as configurable business rules, and show exact values rather than only labels.

## 4. Lifecycle and new-entry vitality

Create mutually exclusive age cohorts:

- under 6 months;
- 6–12 months;
- 1–3 years;
- 3–5 years;
- over 5 years;
- unknown.

For each cohort, report listing count, active rate where measurable, unit share, revenue share, median units, median review count, price, and feature mix. Compare new-product penetration without confusing age with causality.

For products launched within 180 days, also report:

- sales activation rate and success rate versus the market median;
- 30/60/90/180-day sales or rank trajectory when available;
- review-growth velocity;
- price discount, coupon, and promotion intensity;
- sponsored-placement and organic-position acquisition;
- Amazon New Releases presence, rank, category path, and penetration rate;
- feature bundles and price bands associated with successful entrants;
- evidence of existing-brand or old-listing traffic support.

Use cumulative windows for `≤30`, `≤60`, and `≤180` days and say so in the table note. Calculate activation rate as active new ASINs divided by ASINs in the window. Calculate unit and revenue shares against the complete formal product pool. Count `New Release` only when the source carries an actual New Release flag; age alone is not a proxy.

Use CPC as a competition-cost input rather than double-counting it inside new-product vitality. Compare weighted market CPC with break-even CPC in the competition and profit modules.

## 5. Seasonality

Use monthly units, revenue, search volume, and price where possible. Separate trend and seasonal components, identify repeatable peak/trough months, and report peak-to-average ratio.

Use 24+ months for confident claims. With 12–23 months, label findings preliminary. With less than 12 months, do not infer annual seasonality.

Translate repeatable demand peaks into a provisional procurement calendar using production lead time, ocean/air transit, receiving, and safety-stock assumptions.

## 6. Product and price segmentation

Use price quantiles, feature bundles, channel position, age, review strength, and margin potential to classify products into evidence-supported segments such as entry, mainstream, premium, and clearance.

Do not label a low-price item as clearance solely from price. Require signals such as sustained price decline, old age, weak replenishment, coupons, or declining sales.

## 7. Feature and specification analysis

For each normalized parameter:

- report known/unknown coverage;
- cross-tab listing count, units, revenue, ASP, unit share, and revenue share;
- compare within relevant price and age strata;
- identify bundles rather than evaluating only isolated features;
- flag groups with small samples.

Treat Listing blanks as `Listing未披露`. Report parameter coverage as a transparency measure, but do not turn undisclosed values into a user data-completion task when the product pool and Listing mining are already complete.

Use regression or matched comparisons only when data volume and missingness support them. Describe results as associations.

## 8. Review and unmet-needs analysis

Sample reviews across sales tiers, brands, prices, ratings, recent/older periods, and key feature bundles. Deduplicate repeated text and separate product failure, compatibility, expectation, usability, logistics, and service issues.

For each theme report:

- review count and percentage of analyzed reviews;
- affected ASIN count;
- rating and recency distribution;
- representative paraphrases;
- severity, frequency, fixability, and evidence confidence.

Convert recurring, fixable problems into testable product requirements. Do not copy long review passages.

## 9. Profit and sensitivity

Build unit economics with:

- selling price and discounts;
- product and packaging cost;
- inbound freight, duty, tax, insurance, and prep;
- referral commission and fulfillment/closing fees;
- storage, returns, removal/disposal, exchange loss, and advertising;
- contribution margin before and after advertising.

Show base, optimistic, and conservative scenarios. Calculate break-even CPC and ACoS only when conversion rate and unit margin inputs exist.

## 10. Patent and compliance risk

List marketplace-specific certifications, labeling, restricted-material, radio/electrical, packaging, and documentation requirements. Search relevant patent/trademark/design evidence when authorized.

Separate:

- confirmed requirement or record;
- plausible risk needing specialist review;
- absence of evidence.

Do not give a legal clearance opinion.

## 11. Consumer scenarios and entry strategy

Map user, source device, display, audio equipment, connection path, desired outcome, compatibility constraints, and failure modes. Rank opportunities by demand evidence, unmet need, differentiation feasibility, margin, keyword access, operational difficulty, and risk.

Import keyword conclusions as a modular appendix when provided; do not recompute raw keyword rankings here.

## 12. Three-competitor teardown

Select three role-based competitors rather than simply the top three sellers:

1. market leader;
2. closest product and price-position substitute;
3. successful recent entrant or fastest credible challenger.

Compare specification, use case, positioning, title, images, video, bullets, A+, price, coupon, variation structure, review themes, keyword positions, ads, promotions, and observable launch trajectory.

For potentially manipulative or policy-violating tactics, use an evidence ladder:

- `observed fact`: directly visible listing, review, category, variation, rank, price, or archive evidence;
- `supported inference`: multiple independent signals fit the tactic;
- `weak hypothesis`: one ambiguous signal only;
- `unknown`: evidence is insufficient.

For every supported inference, cite the evidence, date, alternative explanation, confidence, likely competitive effect, and platform-enforcement risk. Never state an inference as fact. Do not provide instructions for fake reviews, deceptive variation merges, rank manipulation, or evading platform controls; translate the competitive insight into compliant alternatives.
