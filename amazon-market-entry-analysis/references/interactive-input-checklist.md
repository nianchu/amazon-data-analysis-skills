# Interactive input checklist

Use this file as the staged conversation script. Ask one phase at a time.

## Phase 0 — Initial request

Ask the user for:

- Amazon marketplace and country;
- product name or the customer problem it solves;
- 2–3 seed competitor ASINs;
- whether the decision is product selection, competitor analysis, product design, or launch planning;
- current period to analyze, normally the latest 30 days.

Then say what initial search terms Codex will propose.

## Phase 1 — Seed definition and product-sales exports

Codex first inspects the seed ASINs, defines the product boundary, and provides the exact search terms. Ask the user to export one file per term for these comparable scopes:

- current latest 30 days;
- immediately preceding comparable 30 days or previous complete month;
- the same date range or same month one year earlier.

All periods must use the same search-term set. Each file should retain:

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

## Phase 3 — Reverse-ASIN keyword acquisition

Codex selects a stratified ASIN batch list and acquires the reverse-ASIN data through an authorized, already signed-in SellerSprite session when available. Do not make keyword files a default user upload. If direct access is blocked, ask the user for exports containing:

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

If access is blocked, ask for Listing screenshots, manuals, or manufacturer links only when the missing evidence materially changes the analysis. Do not expose a default Listing-upload requirement in the intake form.

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
- volumetric-weight freight rate;
- actual-weight freight rate;
- exchange rate;
- return rate and unsellable-return share if used;
- advertising cost rate or dollar budget;
- withdrawal/payment cost;
- average storage months and launch month;
- duties, insurance, labels, domestic transport, coupons, Vine, and other unit costs.

Calculate `volumetric weight = L×W×H÷divisor`, `volumetric cost = volumetric weight×volumetric rate`, and `weight cost = actual weight×weight rate`; use `MAX(volumetric cost, weight cost)` as final first-leg cost. If both methods use the same rate, the user may enter the same rate twice.

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

## Phase 9 — Compliance and patent research

Codex researches public marketplace, certification, licensing, patent, trademark, and design evidence. Do not expose compliance or patent uploads as default intake fields. Ask only for non-public supplier evidence when it is needed:

- supplier certificates and test reports;
- model numbers covered by each report;
- HDMI/Dolby or other licensing evidence;
- power supply and battery configuration;
- packaging labels and intended Listing claims;
- supplier patent assurances and known competitor patents.

Never interpret missing documents as clearance.

## Phase 10 — Final confirmation

Before delivery, show a compact received/missing list. Ask only about blockers that can change the decision. Produce the report with unavailable modules clearly labeled rather than inventing data.
