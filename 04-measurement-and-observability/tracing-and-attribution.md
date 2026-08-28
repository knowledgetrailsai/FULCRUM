# Tracing and Attribution

`Home › 04-measurement-and-observability › Tracing and Attribution`

## The Principle

You cannot optimize what you cannot attribute. A cloud invoice can tell an organization it spent $1.4 million on AI. It won't say which workflow generated the cost, which model or agent was responsible, how much came from retries, how much came from evaluation, or whether the outcome was actually successful.

## The Unit of Analysis

```
One business task → one execution trace → multiple model/tool/evaluation events → one business outcome
```

Every trace should be attributable end-to-end, not aggregated at the model or infrastructure level.

## Minimum Observability Bar

- One business task maps to one execution trace
- Trace captures every model call, tool call, and evaluation call within that task
- Each trace records: which workflow, which model, which agent/step, retry count, and outcome (success / fail / escalated)
- Cost is attributable to business unit and workflow — not just visible in aggregate

## Trace-Level Fields

At minimum, each execution trace should record:

- Workflow ID
- Model(s) called, and tier
- Tool calls made
- Evaluation calls made (if any)
- Iteration count for this task
- Total tokens/context size consumed
- Outcome: success / fail / escalated
- Timestamp and business unit

See [templates/cost-value-dashboard-spec.md](../templates/cost-value-dashboard-spec.md) for the full field specification feeding into dashboards.

## Instrumenting the Hidden Multipliers Directly

The leading indicators that predict Cost Density drift before it shows up in the invoice — instrument these explicitly, not just aggregate cost:

- Iteration count per task (see [Agentic Loop Multiplier](../02-cost-economics/hidden-multipliers.md#2-agentic-loop-multiplier))
- Context size per call (see [Context Window Tax](../02-cost-economics/hidden-multipliers.md#1-context-window-tax))
- Evaluation calls per task (see [Shadow Tax of Evaluation](../02-cost-economics/hidden-multipliers.md#3-shadow-tax-of-evaluation))

## Instrumenting Outcome and Value

Cost instrumentation alone is not enough. Outcome capture must be linked to the [Level 3 definition](../03-value-economics/value-progression.md) — was the task actually successful, per the business definition — ideally by linking to downstream systems that confirm business value (CRM, ticketing, ERP, billing) rather than inferring value from task completion alone.

## When to Build This

Before go-live, not after — see [Phase 3 — Instrument](../06-lifecycle/phase-3-instrument.md). Retrofitting tracing after launch means losing months of attributable data.

---

**Previous:** [Cost Density and Value Density](cost-value-density.md)
**Next:** [Metrics Catalog](metrics-catalog.md)
