# The Two Ledgers: Cost and Value

`Home › 01-foundations › The Two Ledgers`

AI FinOps has historically tracked one ledger — cost. A complete methodology tracks two, side by side, at the same granularity, for every workload.

```
Net AI Value = Realized Business Value − Total Economic Cost
```

Neither ledger is meaningful alone. Cost without value looks like waste even when it isn't. Value without cost looks like success even when it's unprofitable.

## The Cost Ledger

Full detail: [02-cost-economics/](../02-cost-economics/)

| Level | Metric | What It Tells You |
|---|---|---|
| 1 | Cost per token | Raw consumption — no context |
| 2 | Cost per request | Consumption per interaction |
| 3 | Cost per task | Consumption per unit of work attempted |
| 4 | Cost per successful outcome | Consumption per unit of realized value |

## The Value Ledger

Full detail: [03-value-economics/](../03-value-economics/)

| Level | Metric | What It Tells You |
|---|---|---|
| 1 | Output produced | Did the system generate a result at all? |
| 2 | Task completed | Was the intended action finished without escalation/failure? |
| 3 | Outcome realized | Did the completed task produce the intended business result? |
| 4 | Value captured | Was the outcome converted into measurable business value? |

## Combined Metrics

```
AI Cost Density  = Total AI Consumption ÷ Successful Business Outcomes
AI Value Density = Realized Business Value ÷ Total Economic Cost
```

Full detail: [04-measurement-and-observability/cost-value-density.md](../04-measurement-and-observability/cost-value-density.md)

A system with high Cost Density but also high Value Density can still be the right investment — expensive, but worth it. A system with low Cost Density but near-zero Value Density is a false economy — cheap, but pointless. **Always read these two numbers together.**

## Where This Model Is Applied

Every phase in the [lifecycle](../06-lifecycle/lifecycle-overview.md) touches both ledgers. Every governance gate in [07-governance](../07-governance/review-gates.md) requires both. The [templates](../templates/) capture both. This is the single model the rest of the repository builds on.

---

**Previous:** [Core Principles](principles.md)
**Next:** [Stakeholder Roles](stakeholder-roles.md)
