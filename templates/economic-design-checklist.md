# AI Economic Design Checklist

`Home › Templates › Economic Design Checklist`

Complete at architecture review (see [Phase 2](../06-lifecycle/phase-2-architect.md) and the [review playbook](../11-implementation-playbooks/architecture-review-playbook.md)), alongside functional design review.

## Cost

- [ ] Expected cost per successful outcome estimated, with method shown ([Cost Progression](../02-cost-economics/cost-progression.md))
- [ ] Average and ceiling iteration count per workflow defined ([Agentic Loop Multiplier](../02-cost-economics/hidden-multipliers.md#2-agentic-loop-multiplier))
- [ ] Context passed per call reviewed — filtered/pruned where possible ([Context Window Tax](../02-cost-economics/hidden-multipliers.md#1-context-window-tax))
- [ ] Model tier justified per task complexity, not defaulted to the most capable option ([Model Routing](../05-architecture-and-design/model-routing.md))
- [ ] Evaluation/guardrail cost checked for proportionality to decision risk ([Shadow Tax of Evaluation](../02-cost-economics/hidden-multipliers.md#3-shadow-tax-of-evaluation))
- [ ] Each model-call step checked against: could deterministic logic replace this? ([Workload Routing](../05-architecture-and-design/workload-routing.md))
- [ ] Escalation threshold defined for tasks that become disproportionately expensive relative to value

## Value

- [ ] Outcome definition confirmed against the signed-off [Outcome & Value Definition Sheet](outcome-value-definition-sheet.md)
- [ ] Value per outcome confirmed and sourced
- [ ] Value Leakage sources identified for this specific architecture ([Value Leakage](../03-value-economics/value-leakage.md))
- [ ] Baseline (pre-AI) cost of the same outcome documented for comparison

## Traceability

- [ ] End-to-end tracing planned from business request through every model/tool/evaluation event to outcome
- [ ] Cost and value both attributable to workflow and business unit, not just visible in aggregate
- [ ] Plan in place to instrument this before go-live (see [Phase 3](../06-lifecycle/phase-3-instrument.md))

## Projected Metrics

| Metric | Projected Value | Method/Assumptions |
|---|---|---|
| Cost Density | | |
| Value Density | | |
| Net AI Value (at expected volume) | | |

---

## Sign-off

| Role | Name | Date |
|---|---|---|
| Architecture/Engineering Lead | | |
| FinOps Lead | | |

If any checkbox above is unchecked, note the reason and remediation plan before proceeding to build.
