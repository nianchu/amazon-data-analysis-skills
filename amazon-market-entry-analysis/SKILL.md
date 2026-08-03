---
name: amazon-market-entry-analysis
description: Orchestrate an interactive, evidence-backed Amazon market-entry study for any product and marketplace by guiding the user through staged data provision, invoking product-pool mining, keyword research, review insight, market analysis, profit modeling, and compliance gates, then producing a decision-first Excel report. Use when a user says they want to analyze a product, competitor, ASIN, category, or market opportunity but needs Codex to tell them exactly what to provide step by step.
---

# Amazon Market Entry Analysis

Run an interactive project without merging the responsibilities of the four specialist skills.

## Specialist routing

- Use `amazon-product-data-mining` for product definition, ASIN qualification, deduplication, Listing verification, and specification extraction.
- Use `amazon-keyword-research` for reverse-ASIN keyword collection, search volume, CPC, conversion evidence, ranking, and placement strategy.
- Use `amazon-review-insight` for review-level cleaning, themes, scenarios, pain points, and improvements.
- Use `amazon-product-analysis` for market, trend, competition, lifecycle, pricing, features, profit, compliance status, opportunity score, and final workbook.

Never transfer one specialist's decisions into another specialist's boundary silently.

## Interaction rule

Ask only for the current phase's inputs. Do not present the entire request list at once unless the user explicitly asks for it.

At every phase, state:

1. what Codex will do;
2. exactly what the user must provide or export;
3. required fields, marketplace, period, and file format;
4. how Codex will validate the files;
5. what output closes the phase;
6. what the next phase will request.

Do not request passwords, cookies, API keys, verification codes, or full account credentials. The user may log in and export authorized data.

Read [references/interactive-input-checklist.md](references/interactive-input-checklist.md) before starting a new project or deciding what to request next.

## Project workflow

### Phase 0 — Start the project

Ask for marketplace, target product or customer job, seed ASINs if known, intended decision, and desired observation period. Create a project manifest and keep each marketplace isolated.

### Phase 1 — Discover candidate products

Propose several initial search terms. Ask the user for product-sales exports for each term and period. Preserve every source file and query.

### Phase 2 — Define the product and verify the pool

Use `amazon-product-data-mining`. Define the unique functional identity before excluding products. Verify ambiguous ASINs from current Listings, images, bullets, A+, manuals, or manufacturer pages. Produce exactly the formal pool, product definition/rules, and integrated source sheets.

Do not calculate market capacity until this phase passes its quality gate.

### Phase 3 — Build the keyword universe

Choose a stratified ASIN sample from the formal pool. Give the user the exact ASIN batches to reverse. Ask for natural and sponsored terms, ranks, search and purchase volume, conversion evidence, CPC, competition, and SellerSprite supply-demand ratio. Use `amazon-keyword-research` and retain exactly the keyword source and ranking sheets.

### Phase 4 — Add historical demand and sales

Ask for like-for-like historical product-sales exports and 24-month keyword history. Keep marketplace, keyword scope, provider, and period comparable. Obtain Google Trends separately and never add its normalized index to Amazon search volume.

### Phase 5 — Extract Listing parameters

Infer a product-specific schema from purchase-decision variables. Verify every formal-pool ASIN. Leave unmentioned values blank or `Listing未披露`; never infer unsupported values.

### Phase 6 — Analyze reviews

Select review ASINs using sales coverage and stratification. Ask for raw review-level exports, not only AI summaries. Use `amazon-review-insight`. Report review-weighted, ASIN-balanced, sales-weighted, and recent-period views when data permits. Preserve review source rows at the end of the workbook.

### Phase 7 — Model profit

Before calculating, ask the user for price, purchase cost, package dimensions, actual weight, volumetric divisor, first-leg rate, return rate, advertising cost, withdrawal cost, storage horizon, and other costs. Query current marketplace referral, FBA fulfillment, and storage fees when possible. Calculate chargeable weight as the higher of actual and volumetric weight.

### Phase 8 — Match the user's product and operating plan

Ask for the user's product specifications, claims, images/manuals if available, budget, inventory constraints, target margin, launch timing, and risk tolerance. Select three evidence-backed competitors and separate observed facts from inferred tactics.

### Phase 9 — Compliance and patent gate

Inventory supplier certificates, authorization chains, planned claims, power configuration, packaging, and known patents. Treat compliance research and FTO as gates; never state legal clearance without evidence.

### Phase 10 — Deliver the decision report

Read [references/latest-template.md](references/latest-template.md). Use the latest decision-first structure, keep calculation and source sheets last, preserve all raw data, and state evidence limitations visibly.

## State and resumption

Maintain a compact project manifest containing:

- marketplace and observation date;
- product definition version;
- received files and missing files;
- formal/pending/excluded ASIN counts;
- keyword and review coverage;
- user-supplied profit inputs;
- completed phases and next requested action;
- latest workbook path and version.

When a conversation becomes long or the user changes computers, summarize this manifest into a portable Markdown file. Never rely only on chat history for project state.

## Completion gate

Do not call the report final until:

- product identity and pool are verified;
- source and formal counts reconcile;
- current and historical scopes are disclosed;
- keyword metrics retain source periods and definitions;
- review percentages state sample and denominator;
- profit inputs are user-confirmed and platform fees dated;
- compliance blockers are explicit;
- executive conclusions trace to visible evidence;
- every source/product-pool sheet appears after reader-facing analysis sheets.
