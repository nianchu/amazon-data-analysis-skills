# Decision Framework

## Scored dimensions

Score each dimension from 0 to 5 and retain the evidence behind the score:

| Dimension | Default weight |
|---|---:|
| Contribution-margin potential | 30% |
| Competition accessibility | 30% |
| New-product vitality | 20% |
| Market size and trend | 20% |

Use these user-approved weights. Treat compliance, IP, data quality, and operational feasibility as guardrails or hard blockers rather than score-padding dimensions.

Calculate `weighted points = dimension score / 5 * dimension weight` and sum to 100. Count CPC only inside competition accessibility; use it elsewhere for diagnostics without adding or subtracting score again.

## Confidence

Assign High, Medium, or Low confidence to every dimension using:

- source coverage;
- observation length;
- metric reliability;
- missingness;
- agreement across independent indicators.

Show both weighted opportunity score and confidence. Never replace missing evidence with a neutral score.

## Decision guide

- `建议切入`: strong evidence, acceptable margin, achievable differentiation, and no critical blocker.
- `有条件切入`: opportunity exists, but named tests or constraints must be satisfied.
- `暂缓切入`: weak economics, inaccessible competition, declining demand, or unacceptable risk.
- `数据不足，无法判断`: core evidence is missing or contradictory.

## Hard blockers

Override the numeric score when any critical issue remains:

- formal product pool is unreliable;
- unit economics are negative in the base case with no credible remedy;
- product cannot meet mandatory compliance;
- material patent/IP risk lacks professional clearance;
- demand or seasonality claims rely on inadequate time coverage;
- proposed differentiation is unsupported by customer or market evidence.

## Recommendation format

State:

1. decision and confidence;
2. target customer and scenario;
3. target price and margin range;
4. minimum viable and optional specifications;
5. primary differentiation and proof required;
6. launch and keyword approach from the keyword module;
7. inventory timing;
8. principal risks;
9. next low-cost validation experiment and pass/fail threshold.
