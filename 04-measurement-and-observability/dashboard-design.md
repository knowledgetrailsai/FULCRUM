# Dashboard Design

`Home › 04-measurement-and-observability › Dashboard Design`

## Design Principle

A dashboard showing only aggregate spend answers "how much did we spend," the wrong question. A dashboard built for AI FinOps must answer "which workflow, which step, and was it worth it" at a glance.

## Recommended Layout

**Level 1 — Portfolio view** (for [Phase 6](../06-lifecycle/phase-6-optimize-scale.md) and quarterly leadership review)
- All active workflows ranked by Net AI Value
- Cost Density vs. Value Density scatter, one point per workflow
- Trend arrows showing direction over the last quarter

**Level 2 — Workflow view** (for weekly workflow-owner review)
- Cost Density and Value Density over time, for this workflow specifically
- Iteration variance, context size trend, evaluation call ratio
- Value Leakage rate and its component sources

**Level 3 — Trace view** (for investigating an anomaly)
- Individual task traces, filterable by outcome (success/fail/escalated), model tier, iteration count
- Drill-down from any Level 2 anomaly to the specific traces driving it

## Build Spec

Full field-level specification: [templates/cost-value-dashboard-spec.md](../templates/cost-value-dashboard-spec.md)

## Common Anti-Pattern

Building Level 1 before Level 3 exists. Portfolio-level density numbers are only meaningful if they're built on task-level tracing (see [Tracing and Attribution](tracing-and-attribution.md)) — otherwise they're just the old aggregate invoice with a new label.

---

**Previous:** [Metrics Catalog](metrics-catalog.md)
**Next section:** [05-architecture-and-design](../05-architecture-and-design/optimization-levers.md)
