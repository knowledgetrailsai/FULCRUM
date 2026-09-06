# Economic Design Review

`Home › 05-architecture-and-design › Economic Design Review`

[← Previous: Tracing and Attribution](../04-measurement-and-observability/tracing-and-attribution.md) · [Contents](../README.md) · [Next: Model Routing →](model-routing.md)

## Why This Exists

By the time a system reaches production, its architecture has already encoded most of its future cost. Waiting for the monthly invoice to reveal this is too late. This review makes economics a design input, reviewed with the same rigor as security or reliability.

## What a Review Should Contain

An architect should be able to explain, before the system ships:

- How many reasoning steps the design requires, and why
- How much context is carried per call, and what's been pruned
- Which model tier handles which task type, and why
- What evaluation exists, and whether its cost is proportional to risk
- What the projected Cost Density and Value Density are, and how they were estimated

The numbers themselves are not the point. **The point is that the architect can explain why the system is expected to consume this much intelligence before it reaches production.**

## The Checklist

Full checklist: [templates/economic-design-checklist.md](../templates/economic-design-checklist.md) — covering cost, value, and traceability readiness.

## Where This Sits in the Lifecycle

This review is the exit criterion for [Phase 2 — Architect for Economics](../06-lifecycle/phase-2-architect.md) and one of the mandatory [governance review gates](../07-governance/review-gates.md). No workflow should proceed to build without it.

---

**Previous:** [Workload Routing](workload-routing.md)
**Next section:** [06-lifecycle](../06-lifecycle/lifecycle-overview.md)

---

[← Previous: Tracing and Attribution](../04-measurement-and-observability/tracing-and-attribution.md) · [Contents](../README.md) · [Next: Model Routing →](model-routing.md)
