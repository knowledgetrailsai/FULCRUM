# Terminology — Key Distinctions

`Home › 00-navigation-and-methodology › Terminology`

This repository uses specific terms deliberately. Conflating them is the most common source of confusion in AI economics conversations — see the [full glossary](../glossary/finops-glossary.md) for complete definitions.

## Cost ≠ Spend ≠ Total Economic Cost

- **Spend** — what appears on the AI vendor invoice (tokens, API calls, infrastructure).
- **Cost** — spend attributed to a specific workflow, task, or outcome.
- **Total Economic Cost** — cost plus failure cost, retry cost, human intervention, latency cost, and opportunity cost. See [02-cost-economics/total-economic-cost.md](../02-cost-economics/total-economic-cost.md).

Most invoices show spend. Few organizations calculate Total Economic Cost. This repository is built around the latter.

## Output ≠ Task Completion ≠ Outcome ≠ Value

Four different claims, often conflated:

- **Output** — the system produced a result.
- **Task completion** — the intended action finished without failure or escalation.
- **Outcome** — the completed task produced the intended business result.
- **Value** — the outcome converted into measurable business value (revenue, cost avoided, time saved).

See [03-value-economics/value-progression.md](../03-value-economics/value-progression.md).

## Cost Density ≠ Value Density

- **Cost Density** = Total AI Consumption ÷ Successful Outcomes — how much it costs to produce one unit of outcome.
- **Value Density** = Realized Business Value ÷ Total Economic Cost — how much value returns per dollar spent.

These answer different questions and must be read together — see [04-measurement-and-observability/cost-value-density.md](../04-measurement-and-observability/cost-value-density.md).

## Model Routing ≠ Workload Routing

- **Model routing** — which model handles a task that's already been decided to need a model.
- **Workload routing** — whether the task needs a model at all, versus a deterministic rule, database lookup, or API call.

See [05-architecture-and-design/workload-routing.md](../05-architecture-and-design/workload-routing.md).

## Lifecycle ≠ Governance

- **Lifecycle** ([06-lifecycle](../06-lifecycle/)) is *when* — the six phases a workload moves through.
- **Governance** ([07-governance](../07-governance/)) is *who decides* — review gates, decision rights, escalation.

Kept as separate sections deliberately, matching the same distinction used in the companion [Responsible-AI](https://github.com/knowledgetrailsai/Responsible-AI) repository.

---

**Previous:** [How to Use This Repository](how-to-use-this-repository.md)
**Full glossary:** [glossary/finops-glossary.md](../glossary/finops-glossary.md)
