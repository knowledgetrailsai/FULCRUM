# Sector Guidance: Coding / Engineering Agents

`Home › 09-sector-specific-finops › Coding Agents`

## Outcome Definition Guidance

Define success as an **accepted** change (merged, or approved by a human reviewer) not merely a generated suggestion. A rejected or heavily-edited suggestion has near-zero or negative value; counting generated output as an outcome significantly overstates value. See [Value Progression](../03-value-economics/value-progression.md).

## Value per Outcome Guidance

Use engineer time saved × loaded hourly rate, measured only against accepted changes. Track review time separately. High review overhead on rejected suggestions is a [Value Leakage](../03-value-economics/value-leakage.md) source, not a neutral cost.

## Typical Hidden Multipliers

- **Agentic Loop Multiplier** is often the dominant cost driver — agentic coding workflows can involve many tool calls (read file, run tests, read error, retry) per task.
- **Context Window Tax** grows with codebase size; whole-repo context on every call is a common and expensive default.

## Typical Value Leakage Sources

- Rejected or heavily-edited suggestions counted as "output produced" but not adopted
- Introduced bugs requiring later remediation, a serious leakage source, often invisible until a downstream incident
- Reviewer time spent on low-quality suggestions

## Recommended Workload Routing

```
Syntax/lint fixes → deterministic tooling (not a model)
Boilerplate generation → small-to-mid model
Complex logic / architecture changes → larger model, with mandatory human review
```

See [Workload Routing](../05-architecture-and-design/workload-routing.md).

---

**Previous:** [Customer Support Agents](customer-support-agents.md)
**Next:** [Claims Processing](claims-processing.md)
