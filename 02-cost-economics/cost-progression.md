# Cost Progression

`Home › 02-cost-economics › Cost Progression`

## The Four Levels

| Level | Metric | What It Tells You | Typical Maturity |
|---|---|---|---|
| 1 | Cost per token | Raw consumption — no context | Most organizations start here |
| 2 | Cost per request | Consumption per interaction | Common in early production |
| 3 | Cost per task | Consumption per unit of work attempted | Requires task-level tracing |
| 4 | Cost per successful outcome | Consumption per unit of realized value | Target maturity — see [Maturity Model](../08-maturity-model/maturity-levels.md) |

## Why Level 1–2 Metrics Mislead

Consider two customer-service agents. The first consumes 10 million tokens and resolves 100,000 requests. The second also consumes 10 million tokens, but resolves only 20,000, frequently retrying and escalating. From a token or request perspective, they look identical. From a business perspective, they are completely different systems.

Cost per token and cost per request measure *activity*. They say nothing about whether that activity produced anything of value. This is the core reason this repository pairs cost with [value economics](../03-value-economics/value-calculation.md) at every level.

## Moving to Level 4

Reaching cost per successful outcome requires:

1. A precise **outcome definition** — see [03-value-economics/value-progression.md](../03-value-economics/value-progression.md) and [templates/outcome-value-definition-sheet.md](../templates/outcome-value-definition-sheet.md)
2. **Task-level tracing** that links consumption to a specific outcome, not just a request — see [04-measurement-and-observability/tracing-and-attribution.md](../04-measurement-and-observability/tracing-and-attribution.md)
3. Willingness to report the number even when it's unfavorable — Level 4 tracking surfaces expensive workflows that Level 1–2 tracking hides

**Guidance:** Define your Level 4 metric before building the system, not after the first invoice — see [Phase 1](../06-lifecycle/phase-1-define-baseline.md).

---

**Next:** [Total Economic Cost](total-economic-cost.md)
