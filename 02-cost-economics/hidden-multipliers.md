# The Three Hidden Cost Multipliers

`Home › 02-cost-economics › Hidden Multipliers`

Architecture decisions that silently inflate spend, independent of model pricing. These are the most common reasons a Cost Density projection ([Phase 2](../06-lifecycle/phase-2-architect.md)) diverges from reality ([Phase 4](../06-lifecycle/phase-4-pilot-calibrate.md)).

## 1. Context Window Tax

Every call often carries full conversation history, retrieved documents, and system instructions — even when the model needs a fraction of it. Long-running agents make this worse, because context accumulates with every iteration.

**Mitigations:** (see [05-architecture-and-design/optimization-levers.md](../05-architecture-and-design/optimization-levers.md#2-reduce))
- Context filtering and summarization before each call
- Selective memory — retrieve only what's relevant to the current step
- Tool-result pruning — don't pass raw payloads forward unmodified
- Caching for repeated or static context blocks

## 2. Agentic Loop Multiplier

A simple chatbot might make one or two model calls per interaction. An agent reasoning, retrieving, calling tools, checking its own work, and retrying can easily turn that into fifteen or twenty. The difference isn't model price — it's the number of times the architecture invokes intelligence.

**Illustration:** at $0.02 per iteration, 5 iterations cost ~$0.10/task; 20 iterations cost ~$0.40/task. At one million tasks, that's $100K vs. $400K — with no change in model pricing.

**Mitigations:**
- Set a maximum iteration ceiling per task type
- Instrument iteration count as a first-class metric — see [04-measurement-and-observability/metrics-catalog.md](../04-measurement-and-observability/metrics-catalog.md)
- Investigate any workflow where iteration count varies widely across similar tasks — that variance is usually a bug, not natural complexity

## 3. Shadow Tax of Evaluation

Guardrails, grounding checks, and safety validation increasingly run on models themselves — creating a second inference layer stacked on top of the first task-performing layer.

```
User request → Agent → Model → Result → Evaluation → Accept or Retry
```

This doesn't mean evaluation should be minimized — in high-risk workflows it's often justified. The question is whether it's *proportional*. This is also where AI FinOps intersects with AI governance — see the companion [Responsible-AI](https://github.com/knowledgetrailsai/Responsible-AI) repository's guardrails guidance.

**Mitigations:**
- Right-size evaluation to risk: a low-risk summarization task doesn't need the same evaluation depth as an autonomous financial transaction
- Ask explicitly: is the cost of evaluating this decision proportional to the cost of getting it wrong?

---

**Previous:** [Total Economic Cost](total-economic-cost.md)
**Next:** [The Inference Paradox](inference-paradox.md)
