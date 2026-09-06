# Cost & Value Dashboard Spec

`Home › Templates › Dashboard Spec`

[← Previous: AI FinOps Glossary](../glossary/finops-glossary.md) · [Contents](../README.md) · [Next: AI Economic Design Checklist →](economic-design-checklist.md)

Field specification for the operational dashboard used in [Phase 5 — Operate & Attribute](../06-lifecycle/phase-5-operate-attribute.md). Layout guidance: [04-measurement-and-observability/dashboard-design.md](../04-measurement-and-observability/dashboard-design.md).

## Per-Workflow Metrics

| Metric | Formula | Frequency | Owner |
|---|---|---|---|
| Cost Density | Total AI Consumption ÷ Successful Outcomes | Weekly | Workflow owner |
| Value Density | Realized Business Value ÷ Total Economic Cost | Weekly | Workflow owner |
| Iteration variance | Std. dev. of iteration count across similar tasks | Weekly | Engineering |
| Context size trend | Avg. tokens of context per call, over time | Weekly | Engineering |
| Value Leakage rate | Leaked value ÷ Gross realized value | Monthly | FinOps |
| Net AI Value | Realized Business Value − Total Economic Cost | Monthly | FinOps |

Full catalog with additional metrics: [04-measurement-and-observability/metrics-catalog.md](../04-measurement-and-observability/metrics-catalog.md).

## Trace-Level Fields

Each execution trace should record, at minimum:

- Workflow ID
- Model(s) called, and tier
- Tool calls made
- Evaluation calls made (if any)
- Iteration count for this task
- Total tokens/context size consumed
- Outcome: success / fail / escalated
- Timestamp and business unit

## Alerting Thresholds (suggested starting points — tune per workload)

- Iteration count for a single task exceeds the defined ceiling
- Cost Density for a workflow moves more than 20% week-over-week without a corresponding volume change
- Value Leakage rate exceeds the tolerance agreed in the [Outcome & Value Definition Sheet](outcome-value-definition-sheet.md)

See [11-implementation-playbooks/incident-cost-spike-response.md](../11-implementation-playbooks/incident-cost-spike-response.md) for the response process when a threshold fires.

## Review Cadence

See [07-governance/review-gates.md](../07-governance/review-gates.md#review-cadence).

---

[← Previous: AI FinOps Glossary](../glossary/finops-glossary.md) · [Contents](../README.md) · [Next: AI Economic Design Checklist →](economic-design-checklist.md)
