# Sector Guidance: Claims / Document Processing

`Home › 09-sector-specific-finops › Claims Processing`

## Outcome Definition Guidance

Define success as an **accurately** processed claim, not merely a processed one — accuracy verified against a sampled audit or downstream dispute rate. This is a high-risk workload category where the [Shadow Tax of Evaluation](../02-cost-economics/hidden-multipliers.md#3-shadow-tax-of-evaluation) is often justified rather than a cost to minimize.

## Value per Outcome Guidance

Use fully-loaded cost of equivalent manual processing, **adjusted for accuracy** — a faster but less accurate process may have lower net value once downstream correction cost is included. See [Total Economic Cost](../02-cost-economics/total-economic-cost.md).

## Typical Hidden Multipliers

- **Shadow Tax of Evaluation** is typically the largest and most justified cost here — financial and compliance risk warrants a dedicated evaluation layer.
- **Context Window Tax** from large supporting documents (policy documents, claim history, correspondence) attached to every call.

## Typical Value Leakage Sources

- Incorrectly approved claims (false positives) — often the single largest leakage source in this category
- Compliance exposure from decisions that don't meet regulatory documentation standards
- Downstream disputes and appeals

## Recommended Workload Routing

```
Field validation / completeness check → deterministic rule
Standard, low-value claim → small-to-mid model with evaluation layer
High-value or ambiguous claim → larger model + evaluation + human approval
```

See [Workload Routing](../05-architecture-and-design/workload-routing.md) and the companion [Responsible-AI](https://github.com/knowledgetrailsai/Responsible-AI) repository for risk-tiering guidance that should inform evaluation design here.

---

**Previous:** [Coding Agents](coding-agents.md)
**Next:** [Document Processing / RAG](document-processing-rag.md)
