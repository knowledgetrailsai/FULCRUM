# Model Routing

`Home › 05-architecture-and-design › Model Routing`

## The Question

Why should every request go to the most capable model? It shouldn't. Model routing decides which model tier handles a task that has already been determined to need a model at all (that prior decision is [Workload Routing](workload-routing.md)).

## The Routing Layer

```
Request → Routing Layer → Appropriate Model → Result
```

The routing layer should consider:

- Task complexity
- Required quality
- Latency requirements
- Data sensitivity
- Business criticality
- Model availability
- Historical success rate (see [Metrics Catalog](../04-measurement-and-observability/metrics-catalog.md))
- Cost
- Current budget

## The Reframed Question

Model optimization is not "which model is cheapest?" and not "which model is best?" It's:

**Which model is sufficient for this workload?**

"Sufficient" is defined jointly by the [outcome definition](../06-lifecycle/phase-1-define-baseline.md) and the [Total Economic Cost](../02-cost-economics/total-economic-cost.md) equation; a model that's technically cheaper but pushes failure/retry cost up is not sufficient in the economic sense.

## Guarding Against Under-Routing

Don't let cost minimization alone drive model tier selection; see [the cheapest-model trap](../02-cost-economics/total-economic-cost.md#why-this-matters-the-cheapest-model-trap). Track success rate by model tier (see [Metrics Catalog](../04-measurement-and-observability/metrics-catalog.md)) to catch under-routing before it shows up as elevated retry cost.

---

**Previous:** [Optimization Levers](optimization-levers.md)
**Next:** [Workload Routing](workload-routing.md)
