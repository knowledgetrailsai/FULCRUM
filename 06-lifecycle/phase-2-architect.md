# Phase 2 — Architect for Economics

`Home › 06-lifecycle › Phase 2`

**Objective:** Design the system against the cost and value model established in Phase 1, not just against functional requirements.

## Activities

1. Run the [Economic Design Checklist](../templates/economic-design-checklist.md) against the proposed architecture.
2. Apply the [Six Optimization Levers](../05-architecture-and-design/optimization-levers.md).
3. Apply the [workload routing decision tree](../05-architecture-and-design/workload-routing.md) to every major decision point.
4. Model **expected** Cost Density and Value Density before build starts ([formulas](../04-measurement-and-observability/cost-value-density.md)), using the Phase 1 definitions.
5. Explicitly account for the [Three Hidden Multipliers](../02-cost-economics/hidden-multipliers.md) in the cost projection.

## Exit Criteria

Architecture review sign-off ([review gate](../07-governance/review-gates.md)) that includes projected Cost Density and Value Density, not just a functional design review.

## Owner

Architecture/engineering lead, with FinOps input.

## Common Pitfalls

- Treating model selection as the only cost lever, ignoring context size and iteration count. Usually the bigger drivers
- Defaulting to the most capable model "to be safe," rather than right-sizing to the task
- Designing evaluation depth uniformly across all tasks, regardless of risk
- Skipping the projected Value Density because "we'll know once it's live": a rough projection forces the assumptions into the open

---

**Previous:** [Phase 1 — Define & Baseline](phase-1-define-baseline.md)
**Next:** [Phase 3, Instrument](phase-3-instrument.md)
