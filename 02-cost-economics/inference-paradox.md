# The Inference Paradox

`Home › 02-cost-economics › Inference Paradox`

## The Paradox

Models can become cheaper while AI systems become more expensive.

The reason is simple: the cost per inference may decrease while the number of inferences increases. Declining token prices do not automatically mean declining application costs.

## Two Architectures, Same Model

A simple application looks like:

```
Prompt → Model → Response
```

An agentic application can look like:

```
Goal → Plan → Reason → Retrieve → Tool → Observe → Reason → Evaluate → Retry → Execute
```

Both might use the same underlying model at the same per-token price. The second architecture can cost ten times more per task, not because the model got more expensive, but because the architecture calls it ten times more.

## The Question That Matters

Not "how much does this model cost per token?" but:

**How many tokens, model calls, and execution steps does our architecture require to produce one successful outcome?**

This reframes cost optimization from a procurement question (which model is cheapest) to an architecture question (how many times do we invoke intelligence, and is each invocation necessary), see [05-architecture-and-design/optimization-levers.md](../05-architecture-and-design/optimization-levers.md).

---

**Previous:** [The Three Hidden Multipliers](hidden-multipliers.md)
**Next section:** [03-value-economics](../03-value-economics/value-progression.md)
