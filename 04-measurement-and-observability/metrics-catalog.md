# Metrics Catalog

`Home › 04-measurement-and-observability › Metrics Catalog`

Full reference of every metric used across this repository, with formula, frequency, and owner.

| Metric | Formula | Frequency | Owner | Reference |
|---|---|---|---|---|
| Cost per token | AI spend ÷ tokens consumed | Continuous | Platform engineering | [Cost Progression](../02-cost-economics/cost-progression.md) |
| Cost per task | AI spend ÷ tasks attempted | Weekly | Workflow owner | [Cost Progression](../02-cost-economics/cost-progression.md) |
| Cost Density | Total AI Consumption ÷ Successful Outcomes | Weekly | Workflow owner | [Cost & Value Density](cost-value-density.md) |
| Value Density | Realized Business Value ÷ Total Economic Cost | Weekly | Workflow owner | [Cost & Value Density](cost-value-density.md) |
| Net AI Value | Realized Business Value − Total Economic Cost | Monthly | FinOps | [Cost & Value Density](cost-value-density.md) |
| Iteration variance | Std. dev. of iteration count across similar tasks | Weekly | Engineering | [Hidden Multipliers](../02-cost-economics/hidden-multipliers.md) |
| Context size trend | Avg. tokens of context per call, over time | Weekly | Engineering | [Hidden Multipliers](../02-cost-economics/hidden-multipliers.md) |
| Evaluation call ratio | Evaluation calls ÷ task-performing calls | Weekly | Engineering | [Hidden Multipliers](../02-cost-economics/hidden-multipliers.md) |
| Value Leakage rate | Leaked value ÷ Gross realized value | Monthly | FinOps | [Value Leakage](../03-value-economics/value-leakage.md) |
| Escalation rate | Tasks escalated to human ÷ total tasks | Weekly | Workflow owner | [Total Economic Cost](../02-cost-economics/total-economic-cost.md) |
| Model tier distribution | % of tasks handled at each model tier | Weekly | Engineering | [Model Routing](../05-architecture-and-design/model-routing.md) |

## Alerting Thresholds (starting points — tune per workload)

- Iteration count for a single task exceeds the defined ceiling (see [economic design checklist](../templates/economic-design-checklist.md))
- Cost Density for a workflow moves more than 20% week-over-week without a corresponding volume change
- Value Leakage rate exceeds the tolerance agreed in the [Outcome & Value Definition Sheet](../templates/outcome-value-definition-sheet.md)

## Review Cadence

See [07-governance/review-gates.md](../07-governance/review-gates.md) for how these metrics map to review gates, and [dashboard-design.md](dashboard-design.md) for how to surface them operationally.

---

**Previous:** [Tracing and Attribution](tracing-and-attribution.md)
**Next:** [Dashboard Design](dashboard-design.md)
