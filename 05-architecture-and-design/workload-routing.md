# Workload Routing

`Home › 05-architecture-and-design › Workload Routing`

[← Previous: Six Optimization Levers](optimization-levers.md) · [Contents](../README.md) · [Next: Lifecycle Overview →](../06-lifecycle/lifecycle-overview.md)

## Beyond Model Routing

[Model routing](model-routing.md) asks: *which model handles this?* Workload routing asks a bigger question: *should this even reach a model?*

## The Decision Tree

Design each workflow as a routing decision tree:

```
Deterministic rule → Database/API lookup → Small model → Larger model → Agent → Human
```

Escalate up this chain only when the step below has genuinely insufficient capability for the task — not by default.

## Examples

- A deterministic business rule may be sufficient to check whether a required field is populated.
- A database query may be sufficient to retrieve an account balance.
- An API may be sufficient to determine whether a customer is active.
- A small model may be sufficient to classify a request.
- A larger model may be required to interpret an ambiguous contractual clause.
- A human may still need to approve an exceptional high-risk decision.

## Why This Matters More Than Model Routing

Workload routing is the sharper lever because the cost difference between "no model call" and "any model call" is categorically larger than the difference between two model tiers. Applying [Lever 6: Don't Ask the Model](optimization-levers.md#6-dont-ask-the-model) at every decision point in a workflow is usually the single highest-leverage step in the [economic design checklist](../templates/economic-design-checklist.md).

## Where This Is Reviewed

Workload routing is a required part of the [Phase 2 architecture review](../06-lifecycle/phase-2-architect.md) and is re-evaluated at [Phase 6](../06-lifecycle/phase-6-optimize-scale.md) as model capability and pricing shift.

---

**Previous:** [Model Routing](model-routing.md)
**Next:** [Economic Design Review](economic-design-review.md)

---

[← Previous: Six Optimization Levers](optimization-levers.md) · [Contents](../README.md) · [Next: Lifecycle Overview →](../06-lifecycle/lifecycle-overview.md)
