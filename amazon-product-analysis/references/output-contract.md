# Excel Output Contract

## Required workbook sheets

Keep the workbook answer-first and use this reader-facing order. Do not combine these modules into an opaque data dump:

1. `00_先看结论`
2. `01_指标口径`
3. `02_市场容量`
4. `03_销售趋势`
5. `04_需求趋势`
6. `05_产品生命周期`
7. `06_季节性与营销节点`
8. `07_新品切入机会`
9. `08_竞争度分析`
10. `09_关键词需求与转化`
11. `10_产品形态分层`
12. `11_功能参数决策`
13. `12_主要竞品与运营拆解`
14. `13_评论与消费者痛点`
15. `14_利润与敏感性`
16. `15_合规与专利风险`

Place every audit/source sheet after all reader-facing analysis sheets, using a visibly separate suffix range such as:

- `90_计算底表`
- `91_正式产品池_当前期`
- `92_正式产品池_历史期1`
- `93_正式产品池_历史期2`
- `94_整合源数据_当前期`
- `95_源数据_历史期1`
- `96_源数据_历史期2`

Never place a product pool, calculation base, or source sheet between analysis modules. Preserve untouched sources; add more trailing sheets when periods require them.

## Required module content

- Sales trend: comparable-period units, revenue, ASP, coverage, change, conclusion, formula, and confidence.
- Demand trend: individual core keyword history, Google Trends or approved substitute, period completeness, demand interpretation, and overlap caveat.
- Lifecycle: mutually exclusive age cohorts with product, unit, and revenue shares.
- Seasonality and events: at least 24 monthly observations for a confident claim; label Prime Day, Prime Big Deal Days, Black Friday/Cyber Monday, holidays, and the limits of causal attribution.
- New-entry opportunity: cumulative 30/60/180-day product count, activation, units, revenue, unit/revenue share, actual New Release flag count, and a ranked new-product table.
- Review analysis: positive/negative themes, scenarios, pains, evidence scope, improvements, denominator, and confidence. If review-level text is absent, do not invent percentages.
- Compliance/IP: requirement, applicability, current evidence, risk, required document/action, prohibited claim, source URL, owner, and status. Do not present a checklist as legal clearance.

## Presentation rules

- Lead with the decision, confidence, target segment, and critical blockers.
- Use formulas or pivots for calculated tables; avoid manually typed summary totals.
- State period, marketplace, currency, grain, denominator, source, and update date near each key table.
- Use consistent colors for fact, estimate, assumption, risk, and recommendation.
- Keep charts decision-oriented: market trend, concentration, lifecycle mix, price/feature performance, review themes, and profit sensitivity.
- Include unknown/missing categories instead of hiding them.
- Display Listing-derived blanks as `Listing未披露`; do not describe them as an incomplete product pool or infer `不支持`.
- Place detailed calculations behind the summary, not inside it.

## Executive summary

Include:

- market capacity and trend;
- competition and lifecycle;
- seasonality confidence;
- viable segment and target price;
- recommended specification bundle;
- customer pain points and proposed improvements;
- base/conservative/optimistic margin;
- compliance/IP flags;
- go/no-go decision;
- next validation actions.

Every summary number must reconcile to a calculation sheet. Every qualitative claim must identify its evidence source or be marked as an inference.
