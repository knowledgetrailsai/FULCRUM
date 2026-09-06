# Sector Guidance: Document Processing / RAG Workflows

`Home › 09-sector-specific-finops › Document Processing & RAG`

[← Previous: Sector Guidance: Customer Support Agents](customer-support-agents.md) · [Contents](../README.md) · [Next: Case Study Template →](../10-case-studies/case-study-template.md)

## Outcome Definition Guidance

Define success as a correctly grounded, accurate answer — not merely a returned answer. Ungrounded or hallucinated responses that read fluently are a distinct failure mode that simple task-completion tracking misses entirely. See [Value Progression](../03-value-economics/value-progression.md).

## Value per Outcome Guidance

Typically time saved × loaded hourly rate for the person who would otherwise search/read manually. Segment by query complexity — simple lookups and complex synthesis queries have very different underlying costs and value.

## Typical Hidden Multipliers

- **Context Window Tax** is the dominant cost driver in RAG architectures by design. Retrieved document chunks are the primary context payload. Retrieval quality (fewer, more relevant chunks) is the highest-leverage cost control.
- **Agentic Loop Multiplier** appears in multi-hop retrieval (retrieve → assess sufficiency → retrieve again) if not bounded.

## Typical Value Leakage Sources

- Confidently wrong (hallucinated) answers that appear grounded but aren't, a serious and hard-to-detect leakage source
- Stale retrieved content producing outdated answers
- Over-retrieval driving cost without improving answer quality

## Recommended Workload Routing

```
Retrieval → optimize for precision, not recall volume (fewer, better chunks)
Simple factual query → small model
Multi-document synthesis → larger model
Low-confidence or safety-critical answer → evaluation layer / human review
```

See [Workload Routing](../05-architecture-and-design/workload-routing.md) and [Context Window Tax mitigations](../02-cost-economics/hidden-multipliers.md#1-context-window-tax).

---

**Previous:** [Claims Processing](claims-processing.md)
**Next section:** [10-case-studies](../10-case-studies/case-study-template.md)

---

[← Previous: Sector Guidance: Customer Support Agents](customer-support-agents.md) · [Contents](../README.md) · [Next: Case Study Template →](../10-case-studies/case-study-template.md)
