# Interactive input checklist

Use this file as the staged conversation script. Ask one phase at a time.

## Phase 0 — Initial request

Ask the user for:

- Amazon marketplace and country;
- product name or the customer problem it solves;
- 1–5 seed ASINs, if known;
- whether the decision is product selection, competitor analysis, product design, or launch planning;
- current period to analyze, normally the latest 30 days.

Then say what initial search terms Codex will propose.

## Phase 1 — Product-sales exports

Codex provides the exact search terms. Ask the user to export one file per term with:

- ASIN and parent/child identifiers when available;
- title, brand, category, price;
- child sales and child revenue;
- rating and review count;
- listing date or listing age;
- seller, fulfillment, rank, New Release flag;
- marketplace, query, period, and export date.

Ask for XLSX/CSV files without manual deletion. Codex merges, validates, and deduplicates them.

## Phase 2 — Product definition confirmation

Codex drafts:

- core job;
- required input/starting state;
- required output/end state;
- indispensable mechanism;
- allowed extension forms;
- adjacent products that must remain separate.

Ask the user only for known positive/negative examples or a boundary decision that materially changes the market. Codex performs Listing verification.

Phase output: formal product pool, product definition/rules, integrated source data.

## Phase 3 — Reverse-ASIN keyword files

Codex gives the user a stratified ASIN batch list. Ask for exports containing:

- keyword;
- natural rank and sponsored rank;
- source ASIN;
- search volume and period;
- purchase volume or conversion rate;
- CPC/bid;
- competing products and advertising competitors;
- SPR, title density, concentration;
- SellerSprite displayed supply-demand ratio;
- marketplace and export date.

Phase output: keyword source data and keyword ranking.

## Phase 4 — Historical trend files

Ask for:

- same-keyword product-sales exports for the selected historical comparison periods;
- core-keyword 24-month monthly history;
- the provider's definitions of search volume, purchase volume, CPC, and supply-demand ratio.

Codex obtains Google Trends when accessible. Historical product files must run through the product-data-mining rules before comparison.

## Phase 5 — Listing parameter mining

The user normally does not need to provide more files. Codex audits formal-pool Listings.

If access is blocked, ask for Listing screenshots, exported HTML/PDF, manuals, connection diagrams, bullets, A+, or manufacturer links.

Phase output: one controlled analytical column per product-specific parameter.

## Phase 6 — Review files

Codex gives the exact ASIN list. Ask the user to export raw review details with:

- ASIN and review ID/link;
- star rating;
- review title and body;
- date;
- variation/model;
- verified-purchase flag;
- helpful votes;
- country/language;
- Vine flag when available.

Prefer all 1–3 star reviews and a representative 4–5 star sample. For market percentages, avoid intentionally oversampling low-star reviews unless weights are documented.

## Phase 7 — Profit inputs

Always ask before calculating; do not silently reuse historical values:

- selling price and currency;
- purchase price and whether it includes tax, packaging, and accessories;
- package length, width, height, and units;
- actual packaged weight;
- volumetric formula and divisor;
- first-leg transport mode and rate;
- exchange rate;
- return rate and unsellable-return share if used;
- advertising cost rate or dollar budget;
- withdrawal/payment cost;
- average storage months and launch month;
- duties, insurance, labels, domestic transport, coupons, Vine, and other unit costs.

Codex queries or asks the user to confirm marketplace referral, FBA fulfillment, inbound placement, and storage fees.

## Phase 8 — User product and launch constraints

Ask for:

- planned product specifications and feature claims;
- product images, manual, packaging, or prototype evidence;
- available launch budget and advertising ceiling;
- first-order quantity and replenishment lead time;
- target margin and maximum acceptable return rate;
- brand status, review resources, and launch timing;
- risk tolerance and required decision date.

## Phase 9 — Compliance and patent inputs

Ask for:

- supplier certificates and test reports;
- model numbers covered by each report;
- HDMI/Dolby or other licensing evidence;
- power supply and battery configuration;
- packaging labels and intended Listing claims;
- supplier patent assurances and known competitor patents.

Never interpret missing documents as clearance.

## Phase 10 — Final confirmation

Before delivery, show a compact received/missing list. Ask only about blockers that can change the decision. Produce the report with unavailable modules clearly labeled rather than inventing data.
