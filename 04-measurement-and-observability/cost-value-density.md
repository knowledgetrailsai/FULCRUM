# Cost Density and Value Density

`Home › 04-measurement-and-observability › Cost & Value Density`

## The Formulas

```
AI Cost Density  = Total AI Consumption ÷ Successful Business Outcomes
AI Value Density = Realized Business Value ÷ Total Economic Cost
Net AI Value      = Realized Business Value − Total Economic Cost
```

- **Cost Density** answers: *how much do we spend to produce one unit of outcome?*
- **Value Density** answers: *for every dollar spent, how much value came back?*
- **Net AI Value** answers: *in absolute terms, is this workload worth running?*

## Why Two Densities, Not One

A system with high Cost Density but also high Value Density can be the right investment — expensive, but worth it. A system with low Cost Density but near-zero Value Density is a false economy — cheap, but pointless. Reading Cost Density alone (the historical default) misses this distinction entirely. Always report both together, per workflow.

## Consumption Side (Cost Density denominator's numerator)

Includes: tokens, model calls, tool calls, evaluation calls, retrieval, infrastructure. See [02-cost-economics/total-economic-cost.md](../02-cost-economics/total-economic-cost.md) for the full cost accounting.

## Outcome Side

Successful, verified outcomes per the [Level 3 definition](../03-value-economics/value-progression.md) — not task completions, not outputs.

## Comparing Architectures

This is the primary use case for these metrics: comparing two designs for the same workload.

| Architecture | Cost Density | Value Density | Interpretation |
|---|---|---|---|
| A — premium model, minimal evaluation | Higher | Higher | Expensive but effective — may be the right choice |
| B — cheap model, high retry rate | Lower | Lower | False economy — see [Total Economic Cost trap](../02-cost-economics/total-economic-cost.md#why-this-matters-the-cheapest-model-trap) |
| C — routed: deterministic + small model + escalation | Lowest | Highest | Typically the target design — see [Workload Routing](../05-architecture-and-design/workload-routing.md) |

## Where These Are Tracked

- Projected at [Phase 2 — Architect for Economics](../06-lifecycle/phase-2-architect.md)
- Validated at [Phase 4 — Pilot & Calibrate](../06-lifecycle/phase-4-pilot-calibrate.md)
- Tracked continuously at [Phase 5 — Operate & Attribute](../06-lifecycle/phase-5-operate-attribute.md)
- Used to rank workloads at [Phase 6 — Optimize & Scale](../06-lifecycle/phase-6-optimize-scale.md)

Dashboard field specification: [templates/cost-value-dashboard-spec.md](../templates/cost-value-dashboard-spec.md)

---

**Next:** [Tracing and Attribution](tracing-and-attribution.md)
