# Knowledge Map

`Home › 00-navigation-and-methodology › Knowledge Map`

This repository is organized as a **control plane**, not an encyclopedia. Every AI economic decision can be traced through a consistent chain:

```
PRINCIPLE → COST/VALUE DRIVER → DESIGN LEVER → MEASUREMENT → DECISION → GOVERNANCE
```

## The Chain, Applied

| Stage | Question it answers | Section |
|---|---|---|
| **Principle** | What do we believe about AI economics? | [01-foundations](../01-foundations/principles.md) |
| **Cost driver** | What actually generates AI spend? | [02-cost-economics](../02-cost-economics/cost-progression.md) |
| **Value driver** | What actually generates business value? | [03-value-economics](../03-value-economics/value-calculation.md) |
| **Design lever** | What architectural choice controls this? | [05-architecture-and-design](../05-architecture-and-design/economic-design-review.md) |
| **Measurement** | How do we see it, per workflow? | [04-measurement-and-observability](../04-measurement-and-observability/cost-value-density.md) |
| **Lifecycle checkpoint** | When in the workflow's life does this get decided? | [06-lifecycle](../06-lifecycle/lifecycle-overview.md) |
| **Governance** | Who decides, and what triggers escalation? | [07-governance](../07-governance/decision-rights.md) |

## Worked Example: Tracing One Decision End-to-End

Take the decision *"should this task use a frontier model?"*

1. **Principle:** [Optimize for total economic cost, not minimum spend](../01-foundations/principles.md#5-optimize-for-total-economic-cost-not-minimum-spend).
2. **Cost driver:** Model tier is one component of [Total Economic Cost](../02-cost-economics/total-economic-cost.md); a cheaper model that fails more often can cost more overall.
3. **Value driver:** The [Value per Outcome](../03-value-economics/value-calculation.md) for this workload sets how much error is tolerable.
4. **Design lever:** [Model routing and workload routing](../05-architecture-and-design/model-routing.md) decide which tier handles this task.
5. **Measurement:** [Cost Density and Value Density](../04-measurement-and-observability/cost-value-density.md) reveal whether the routing choice was right, after real usage.
6. **Lifecycle checkpoint:** This decision is made explicit at [Phase 2 — Architect for Economics](../06-lifecycle/phase-2-architect.md) and revisited at [Phase 6 — Optimize & Scale](../06-lifecycle/phase-6-optimize-scale.md).
7. **Governance:** Sign-off happens at the [architecture economic review gate](../07-governance/review-gates.md); persistent negative Net AI Value triggers the [escalation path](../07-governance/escalation-and-scale-retire.md).

Any question in this repository can be traced the same way — from belief, to number, to decision, to owner.

## Three Ways to Navigate

| You know... | Use |
|---|---|
| The section (e.g. "I need cost economics") | The structure in [README.md](../README.md), or browse folders directly |
| The topic, not the section (e.g. "value leakage," "model routing") | Search by filename — this repo's naming is descriptive by design |
| Nothing yet, want to scan everything | [INDEX.md](../INDEX.md) — every file, one flat list |

---

**Next:** [How to Use This Repository](how-to-use-this-repository.md)
