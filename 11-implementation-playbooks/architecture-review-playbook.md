# Playbook: Architecture Economic Review

`Home › 11-implementation-playbooks › Architecture Review`

A working script for running the [Phase 2 review gate](../06-lifecycle/phase-2-architect.md) in practice.

## Before the Meeting

1. Architect completes the [Economic Design Checklist](../templates/economic-design-checklist.md) and shares it with reviewers 48 hours in advance.
2. FinOps confirms the [Outcome & Value Definition Sheet](../templates/outcome-value-definition-sheet.md) from Phase 1 is signed off. Do not proceed without it.

## In the Meeting

1. Walk the workload routing decision tree ([Workload Routing](../05-architecture-and-design/workload-routing.md)), and for each major step, confirm why it needs a model at all, and at what tier.
2. Review projected Cost Density and Value Density, and the assumptions behind them.
3. Explicitly review each of the [Three Hidden Multipliers](../02-cost-economics/hidden-multipliers.md) (context size, iteration ceiling, evaluation depth) and confirm each has a stated, deliberate value (not a default).
4. Confirm the instrumentation plan for [Phase 3](../06-lifecycle/phase-3-instrument.md) is concrete, not aspirational.

## Sign-Off

Both the architecture/engineering lead and FinOps lead sign the checklist. Unresolved items get an owner and a date, and the review does not close with open items unassigned.

## After the Meeting

File the signed checklist alongside the workload's [Outcome & Value Definition Sheet](../templates/outcome-value-definition-sheet.md) for reference at [Phase 4 calibration](../06-lifecycle/phase-4-pilot-calibrate.md).

---

**Next:** [90-Day AI FinOps Adoption Plan](finops-adoption-90-day-plan.md)
