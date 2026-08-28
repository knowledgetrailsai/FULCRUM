# Playbook: Cost Spike Incident Response

`Home › 11-implementation-playbooks › Cost Spike Response`

A working response process for the [alerting thresholds](../04-measurement-and-observability/metrics-catalog.md#alerting-thresholds-starting-points--tune-per-workload) defined in the metrics catalog.

## Trigger

Cost Density for a workflow moves more than 20% week-over-week without a corresponding volume change, or iteration count for a task exceeds its defined ceiling.

## Response Steps

1. **Isolate.** Pull the [trace-level data](../04-measurement-and-observability/tracing-and-attribution.md) for the affected workflow over the anomaly window. Identify whether the spike traces to context size, iteration count, or evaluation call volume — see [Hidden Multipliers](../02-cost-economics/hidden-multipliers.md).
2. **Diagnose.** Common root causes:
   - A new input pattern (e.g., a promotion, a product change) confusing a routing/classification step
   - A model or prompt change that inadvertently increased context size
   - A degraded upstream tool causing retries
3. **Contain.** If the workflow has a defined iteration ceiling or escalation threshold (see [Economic Design Checklist](../templates/economic-design-checklist.md)), confirm it's enforced. If not, apply a temporary ceiling.
4. **Fix.** Apply the relevant [Optimization Lever](../05-architecture-and-design/optimization-levers.md) — typically Reduce or Route.
5. **Report.** Log the incident and remediation against the workflow's record — this feeds the [Phase 6 portfolio review](../06-lifecycle/phase-6-optimize-scale.md) and should inform whether Total Economic Cost assumptions need revisiting.

## Distinction From Sustained Escalation

This playbook covers a sudden, isolated anomaly. A persistent trend of negative Net AI Value over multiple review cycles follows the separate [escalation and scale/retire path](../07-governance/escalation-and-scale-retire.md) instead.

---

**Previous:** [90-Day AI FinOps Adoption Plan](finops-adoption-90-day-plan.md)
**Back to:** [README](../README.md)
