# Maturity Model

`Home › 08-maturity-model › Maturity Levels`

Use this to assess where an organization or workload currently sits, and what "next" looks like. (Note: [OASIS's own nine-dimension engineering maturity model](https://github.com/knowledgetrailsai/OASIS/blob/main/assessments/oasis-ai-engineering-maturity-model.md) also scores an "Economics and FinOps" dimension on a Level 0-4 scale, a different, coarser measure of overall economics-engineering practice, not this cost/value-tracking-specific scale. The two Level numbers are not interchangeable.)

| Level | Cost Tracking | Value Tracking | Governance |
|---|---|---|---|
| **0 — Ad hoc** | Monthly invoice only | None | No review gate |
| **1 — Visible** | Cost per token/request | Anecdotal ("users like it") | Cost reviewed post-hoc |
| **2 — Attributed** | Cost per task, traced to workflow | Outcome counted, not valued | Cost included in architecture review |
| **3 — Valued** | Cost per successful outcome | Value per outcome assigned and tracked | Both ledgers reviewed jointly pre-deployment |
| **4 — Optimized** | Cost Density tracked continuously | Value Density tracked continuously, Leakage measured | Workflows ranked and reallocated by Net AI Value |

## Guidance by Level

**Most organizations sit at Level 1.** They can see the total AI bill and maybe break it down by model, but cannot say which workflow drove the spend or whether it produced value.

**Target Level 3 before scaling any workload.** A workload should not move from [Phase 4 to Phase 5](../06-lifecycle/phase-4-pilot-calibrate.md) until cost and value are both tracked per outcome, not just per request.

**Target Level 4 for high-spend or high-criticality workloads.** At this level, Cost Density and Value Density are live metrics reviewed on a cadence (see [07-governance/review-gates.md](../07-governance/review-gates.md)), and resource allocation decisions are made using Net AI Value — not volume, visibility, or executive sponsorship.

## Self-Assessment Questions

- Can you name, right now, the three highest-spending AI workflows in your organization? (Level 0 → 1)
- Can you attribute that spend to specific workflows, agents, and steps — not just an aggregate model bill? (Level 1 → 2)
- Does every AI workflow have an agreed value-per-outcome figure, signed off by a business owner? (Level 2 → 3)
- Do you track Value Leakage as an ongoing metric, and use Value Density to decide what scales? (Level 3 → 4)

## Moving Between Levels

| Transition | What's required | Reference |
|---|---|---|
| 0 → 1 | Break down invoice by model/workflow | [02-cost-economics/cost-progression.md](../02-cost-economics/cost-progression.md) |
| 1 → 2 | Build task-level tracing | [04-measurement-and-observability/tracing-and-attribution.md](../04-measurement-and-observability/tracing-and-attribution.md) |
| 2 → 3 | Define outcomes and value per outcome for every active workflow | [06-lifecycle/phase-1-define-baseline.md](../06-lifecycle/phase-1-define-baseline.md) |
| 3 → 4 | Build continuous density dashboards, measure leakage, use Net AI Value for portfolio decisions | [04-measurement-and-observability/dashboard-design.md](../04-measurement-and-observability/dashboard-design.md), [06-lifecycle/phase-6-optimize-scale.md](../06-lifecycle/phase-6-optimize-scale.md) |

---

**Next section:** [09-sector-specific-finops](../09-sector-specific-finops/claims-processing.md)
