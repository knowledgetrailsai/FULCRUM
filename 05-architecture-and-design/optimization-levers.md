# Six Optimization Levers

`Home › 05-architecture-and-design › Optimization Levers`

Use this as a checklist during architecture review ([Phase 2](../06-lifecycle/phase-2-architect.md)) — not after deployment. Full checklist form: [templates/economic-design-checklist.md](../templates/economic-design-checklist.md).

## 1. Route
Send each task to the right model or execution mechanism. Not every request needs the most capable model. See [Model Routing](model-routing.md) and [Workload Routing](workload-routing.md).

## 2. Reduce
Cut unnecessary context, tokens, model calls, retrieval steps, and agent iterations. Directly addresses the [Hidden Multipliers](../02-cost-economics/hidden-multipliers.md).

## 3. Reuse
Cache repeated context, results, and intermediate computations where appropriate.

## 4. Right-size
Match model capability to the workload, not to the ceiling of what's available. A routine extraction task rarely needs a frontier model.

## 5. Measure
Trace execution end-to-end from business request through model, tool, and evaluation calls so cost *and* outcome can be attributed — not just totaled. See [04-measurement-and-observability/tracing-and-attribution.md](../04-measurement-and-observability/tracing-and-attribution.md).

## 6. Don't Ask the Model
If a business rule, SQL query, or API call is sufficient, don't spend inference on it. This lever deserves the most discipline — **the cheapest, safest computation is often the one you never run through a model.**

## Applying the Levers Together

These levers aren't independent — they compound. A well-routed task (Lever 1) that also has pruned context (Lever 2) and a right-sized model (Lever 4) can see multiplicative cost reduction versus applying any single lever alone. Apply all six as a single pass at [Phase 2](../06-lifecycle/phase-2-architect.md), not sequentially after each one is found insufficient alone.

---

**Next:** [Model Routing](model-routing.md)
