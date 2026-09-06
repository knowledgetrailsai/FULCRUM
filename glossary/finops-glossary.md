# AI FinOps Glossary

`Home › Glossary`

[← Previous: Playbook: Cost Spike Incident Response](../11-implementation-playbooks/incident-cost-spike-response.md) · [Contents](../README.md) · [Next: Cost & Value Dashboard Spec →](../templates/cost-value-dashboard-spec.md)

| Term | Definition | See |
|---|---|---|
| **AI Cost Density** | Total AI Consumption ÷ Successful Business Outcomes | [04-measurement-and-observability/cost-value-density.md](../04-measurement-and-observability/cost-value-density.md) |
| **AI Value Density** | Realized Business Value ÷ Total Economic Cost | [04-measurement-and-observability/cost-value-density.md](../04-measurement-and-observability/cost-value-density.md) |
| **Agentic Loop Multiplier** | Cost inflation from repeated reasoning/tool-call iterations per task | [02-cost-economics/hidden-multipliers.md](../02-cost-economics/hidden-multipliers.md) |
| **Context Window Tax** | Cost of repeatedly sending full context when only a fraction is needed | [02-cost-economics/hidden-multipliers.md](../02-cost-economics/hidden-multipliers.md) |
| **Inference Paradox** | Falling per-token price coexisting with rising total AI system cost, due to rising call volume | [02-cost-economics/inference-paradox.md](../02-cost-economics/inference-paradox.md) |
| **Model Routing** | Deciding which model tier handles a task already determined to need a model | [05-architecture-and-design/model-routing.md](../05-architecture-and-design/model-routing.md) |
| **Net AI Value** | Realized Business Value − Total Economic Cost | [04-measurement-and-observability/cost-value-density.md](../04-measurement-and-observability/cost-value-density.md) |
| **Outcome** | The completed task producing the intended business result (Level 3 of the value progression) | [03-value-economics/value-progression.md](../03-value-economics/value-progression.md) |
| **Shadow Tax of Evaluation** | The cost of a second inference layer (guardrails, grounding checks) stacked on the task-performing layer | [02-cost-economics/hidden-multipliers.md](../02-cost-economics/hidden-multipliers.md) |
| **Total Economic Cost** | AI cost + failure cost + retry cost + human intervention + latency cost + opportunity cost | [02-cost-economics/total-economic-cost.md](../02-cost-economics/total-economic-cost.md) |
| **Value Leakage** | Value lost to false positives, downstream rework, trust erosion, or compliance exposure | [03-value-economics/value-leakage.md](../03-value-economics/value-leakage.md) |
| **Value per Outcome** | Pre-agreed monetary or proxy value assigned to one successful outcome | [03-value-economics/value-calculation.md](../03-value-economics/value-calculation.md) |
| **Workload Routing** | Deciding whether a task should reach a model at all, versus a deterministic rule, database lookup, or API call | [05-architecture-and-design/workload-routing.md](../05-architecture-and-design/workload-routing.md) |

See also [00-navigation-and-methodology/terminology-and-glossary.md](../00-navigation-and-methodology/terminology-and-glossary.md) for the key distinctions this repository maintains between closely related terms.

---

[← Previous: Playbook: Cost Spike Incident Response](../11-implementation-playbooks/incident-cost-spike-response.md) · [Contents](../README.md) · [Next: Cost & Value Dashboard Spec →](../templates/cost-value-dashboard-spec.md)
