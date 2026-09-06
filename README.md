# Fulcrum:  AI FinOps ( Part of OASIS)

A comprehensive AI FinOps knowledge base covering cost economics, value economics, measurement, architecture, lifecycle, and governance. Think of it as the control layer for economic decisions, not a reference encyclopedia. Content flows through a consistent chain so any economic decision can be traced from principle to proof:

```
PRINCIPLE → COST/VALUE DRIVER → DESIGN LEVER → MEASUREMENT → DECISION → GOVERNANCE
```

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-yellow.svg)](LICENSE)
![Status](https://img.shields.io/badge/status-draft%20v1.0-orange)

See [00-navigation-and-methodology/knowledge-map.md](00-navigation-and-methodology/knowledge-map.md) for the full model, including a worked example tracing one decision end-to-end through every section below.

## Why This Exists

Most enterprise AI cost overruns are not caused by model pricing. They are caused by architecture decisions made before anyone thought about cost: how much context gets sent, how many times an agent loops, how many models are stacked for evaluation.

At the same time, most organizations track AI **cost** without tracking AI **value**. A system can be cheap and worthless, or expensive and highly profitable; cost alone tells you neither.

```
Net AI Value = Realized Business Value − Total Economic Cost
```

This repository treats AI economics as two ledgers, tracked together, from architecture through operation.

## Six Principles

Every section traces back to six principles, and if a decision conflicts with one of them, the decision is wrong, not the principle: token cost is not outcome cost, so cost and outcome get measured together, never cost alone; cost is architectural, not incidental, since context size, agent loop count, evaluation depth, and model routing are design decisions made months before an invoice arrives; value must be calculated before it's claimed, so "users like it" is never an accepted value model without a defined outcome, an agreed value per outcome, and a named source for that figure; economics shifts left into architecture review, alongside security and reliability, rather than surfacing in a finance review after the system has already shipped; and the target is total economic cost, not minimum spend, since a weaker model with more retries and escalations can cost more overall than a stronger, pricier one. See [01-foundations/principles.md](01-foundations/principles.md).

## Two Ledgers, Read Together

AI FinOps has historically tracked one ledger, cost. This repository tracks two, at the same granularity, for every workload: a Cost Ledger that climbs from cost-per-token through cost-per-successful-outcome, and a Value Ledger that climbs the corresponding value hierarchy. Neither is meaningful alone — cost without value looks like waste even when it isn't, and value without cost looks like success even when it's unprofitable — which is why `Net AI Value = Realized Business Value − Total Economic Cost` sits at the top of this README rather than a cost figure by itself. See [01-foundations/two-ledgers-cost-and-value.md](01-foundations/two-ledgers-cost-and-value.md).

## Where Cost Actually Comes From

Two ideas in [02-cost-economics](02-cost-economics) explain why AI spend routinely surprises the people who approved the budget. The Inference Paradox: models can get cheaper while AI systems get more expensive, because the same per-token price applied across ten times more calls costs ten times more, independent of pricing — a simple prompt-to-response architecture and an agentic goal-plan-reason-retrieve-tool-observe-retry architecture can run the identical model at wildly different total cost. And the three hidden multipliers that drive that call count up without anyone deciding to spend more: the context-window tax (full history and retrieved documents carried on every call, worse for long-running agents as context accumulates), the agentic loop multiplier (fifteen or twenty model calls per task instead of one or two, where a five-iteration task at $0.02/iteration costs $0.10 and a twenty-iteration task costs $0.40 — a 4x cost difference with no change in model price), and a third multiplier covered alongside them. See [02-cost-economics/inference-paradox.md](02-cost-economics/inference-paradox.md) and [hidden-multipliers.md](02-cost-economics/hidden-multipliers.md); [total-economic-cost.md](02-cost-economics/total-economic-cost.md) is where all of it gets accounted for in one figure rather than left scattered across a model-pricing invoice.

## Value Has to Be Calculated, Not Asserted

The value ledger runs through the same discipline as the cost ledger: a progression from raw output through task completion, outcome, and finally value (four levels of claim routinely conflated in AI ROI reporting), and an explicit calculation with a named source for the value-per-outcome figure. [03-value-economics/value-leakage.md](03-value-economics/value-leakage.md) is the term most AI ROI calculations omit and the most common source of overstated ROI: business value lost to false positives, downstream rework, trust erosion, or compliance exposure the AI system itself created, subtracted from gross outcome value to arrive at realized business value. Leakage is easy to miss because it typically surfaces in a different system than the one that produced the original outcome — a reopened support ticket, a billing dispute, a regulatory inquiry — so without deliberate cross-system tracking each looks unrelated to the AI decision that actually caused it. A value model that doesn't name its leakage sources should be treated as incomplete, not conservative.

## Two Densities, Not One

[04-measurement-and-observability/cost-value-density.md](04-measurement-and-observability/cost-value-density.md) gives the two headline metrics this repository is built around: Cost Density (total AI consumption divided by successful business outcomes — how much it costs to produce one unit of outcome) and Value Density (realized business value divided by total economic cost — how much value comes back per dollar spent). Reading Cost Density alone, the historical default, hides the distinction between a workload that's expensive but worth it and one that's cheap but pointless; both densities get reported together, per workflow, not as a single blended figure. [tracing-and-attribution.md](04-measurement-and-observability/tracing-and-attribution.md) is what makes either density trustworthy: cost and outcome traced end-to-end from business request through model, tool, and evaluation calls, attributed rather than merely totaled.

## Six Levers, Applied at Design Time

[05-architecture-and-design/optimization-levers.md](05-architecture-and-design/optimization-levers.md) is meant to be run as a checklist during architecture review, not after deployment: route each task to the right model or execution mechanism rather than defaulting every request to the most capable one; reduce unnecessary context, tokens, calls, and iterations, directly attacking the hidden multipliers; reuse cached context, results, and intermediate computation; right-size model capability to the workload instead of the ceiling of what's available; measure by tracing execution so cost and outcome can both be attributed; and — the lever the guide says deserves the most discipline — don't ask the model at all when a business rule, SQL query, or API call is sufficient, since the cheapest, safest computation is often the one that never runs through a model.

## A Loop, Not a Line

AI FinOps is a continuous lifecycle, not a one-time exercise: [06-lifecycle/lifecycle-overview.md](06-lifecycle/lifecycle-overview.md) runs six phases — define and baseline (agree what "outcome" and "value" mean before design starts), architect for economics, instrument, pilot and calibrate (validate projected density against real usage), operate and attribute, and optimize and scale (reallocate based on Value Density) — with Phase 6 explicitly feeding back into Phase 1 so leakage patterns and benchmarks compound into the next workload rather than resetting each time. Cost and value get calculated at every phase, not bolted on at the end once the invoice has already arrived.

## Governance as a Blocking Gate, Not a Formality

No AI workflow proceeds past Phase 2 without projected Cost Density and Value Density signed off alongside the functional design — [07-governance/review-gates.md](07-governance/review-gates.md) treats this the same way a security or reliability review gets treated, not as paperwork. Four gates run through the lifecycle (outcome and value sign-off, architecture economic review, pilot calibration review, scale/retire review) on weekly, monthly, and quarterly cadences, with quarterly review ranking the full workload portfolio by Net AI Value to inform which workloads scale and which get retired. [decision-rights.md](07-governance/decision-rights.md) names who actually holds that call.

## Maturity: Most Organizations Are at Level 1

[08-maturity-model/maturity-levels.md](08-maturity-model/maturity-levels.md) scores an organization from Level 0 (ad hoc — monthly invoice only, no value tracking, no review gate) through Level 4 (optimized — Cost Density and Value Density tracked continuously, leakage measured, workflows ranked and reallocated by Net AI Value). Most organizations sit at Level 1: they can see the total AI bill and maybe break it down by model, but cannot say which workflow drove the spend or whether it produced value. The guidance is concrete: target Level 3 before scaling any workload (a workload shouldn't move from Phase 4 to Phase 5 until cost and value are both tracked per outcome, not just per request), and target Level 4 for high-spend or high-criticality workloads specifically.

## From Sector Patterns to a 90-Day Rollout

[09-sector-specific-finops](09-sector-specific-finops) and [10-case-studies](10-case-studies) ground all of the above in specific workload shapes — customer support agents, coding agents, claims and document processing, RAG workflows — rather than leaving cost/value density as an abstract formula. [11-implementation-playbooks](11-implementation-playbooks) turns the methodology into three concrete working documents: an architecture economic review playbook, a 90-day AI FinOps adoption plan for rolling this out organization-wide, and a cost-spike incident response playbook for when Total Economic Cost moves unexpectedly and someone needs to find out why before the next invoice.

## Start Here

New to this repository? Read [00-navigation-and-methodology/how-to-use-this-repository.md](00-navigation-and-methodology/how-to-use-this-repository.md). It routes you to the right section based on your role and task.

## Repository Structure

### 00 · Navigation and Methodology
- [Knowledge Map](00-navigation-and-methodology/knowledge-map.md)
- [How to Use This Repository](00-navigation-and-methodology/how-to-use-this-repository.md)
- [Terminology: Key Distinctions](00-navigation-and-methodology/terminology-and-glossary.md)

### 01 · Foundations
- [What Is AI FinOps](01-foundations/what-is-ai-finops.md)
- [Core Principles](01-foundations/principles.md)
- [The Two Ledgers: Cost and Value](01-foundations/two-ledgers-cost-and-value.md)
- [Stakeholder Roles](01-foundations/stakeholder-roles.md)

### 02 · Cost Economics
- [Cost Progression](02-cost-economics/cost-progression.md)
- [Total Economic Cost](02-cost-economics/total-economic-cost.md)
- [The Three Hidden Multipliers](02-cost-economics/hidden-multipliers.md)
- [The Inference Paradox](02-cost-economics/inference-paradox.md)

### 03 · Value Economics
- [Value Progression](03-value-economics/value-progression.md)
- [Value Calculation](03-value-economics/value-calculation.md)
- [Value Leakage](03-value-economics/value-leakage.md)
- [Value per Outcome: Benchmarking Guidance](03-value-economics/value-per-outcome-benchmarks.md)

### 04 · Measurement and Observability
- [Cost Density and Value Density](04-measurement-and-observability/cost-value-density.md)
- [Tracing and Attribution](04-measurement-and-observability/tracing-and-attribution.md)
- [Metrics Catalog](04-measurement-and-observability/metrics-catalog.md)
- [Dashboard Design](04-measurement-and-observability/dashboard-design.md)

### 05 · Architecture and Design
- [Six Optimization Levers](05-architecture-and-design/optimization-levers.md)
- [Model Routing](05-architecture-and-design/model-routing.md)
- [Workload Routing](05-architecture-and-design/workload-routing.md)
- [Economic Design Review](05-architecture-and-design/economic-design-review.md)

### 06 · Lifecycle
- [Lifecycle Overview](06-lifecycle/lifecycle-overview.md)
- [Phase 1: Define & Baseline](06-lifecycle/phase-1-define-baseline.md)
- [Phase 2: Architect for Economics](06-lifecycle/phase-2-architect.md)
- [Phase 3: Instrument](06-lifecycle/phase-3-instrument.md)
- [Phase 4: Pilot & Calibrate](06-lifecycle/phase-4-pilot-calibrate.md)
- [Phase 5: Operate & Attribute](06-lifecycle/phase-5-operate-attribute.md)
- [Phase 6: Optimize & Scale](06-lifecycle/phase-6-optimize-scale.md)

### 07 · Governance
- [Review Gates](07-governance/review-gates.md)
- [Decision Rights](07-governance/decision-rights.md)
- [Escalation and Scale/Retire Decisions](07-governance/escalation-and-scale-retire.md)

### 08 · Maturity Model
- [Maturity Levels](08-maturity-model/maturity-levels.md)

### 09 · Sector-Specific FinOps
- [Customer Support Agents](09-sector-specific-finops/customer-support-agents.md)
- [Coding / Engineering Agents](09-sector-specific-finops/coding-agents.md)
- [Claims / Document Processing](09-sector-specific-finops/claims-processing.md)
- [Document Processing / RAG Workflows](09-sector-specific-finops/document-processing-rag.md)

### 10 · Case Studies
- [Case Study Template](10-case-studies/case-study-template.md)
- [Worked Example: Tier-1 Customer Support Agent](10-case-studies/customer-support-agent.md)

### 11 · Implementation Playbooks
- [Architecture Economic Review](11-implementation-playbooks/architecture-review-playbook.md)
- [90-Day AI FinOps Adoption Plan](11-implementation-playbooks/finops-adoption-90-day-plan.md)
- [Cost Spike Incident Response](11-implementation-playbooks/incident-cost-spike-response.md)

### Glossary
- [AI FinOps Glossary](glossary/finops-glossary.md)

### Templates
- [Outcome & Value Definition Sheet](templates/outcome-value-definition-sheet.md)
- [AI Economic Design Checklist](templates/economic-design-checklist.md)
- [Cost & Value Dashboard Spec](templates/cost-value-dashboard-spec.md)

Not sure which section has what you need? See [INDEX.md](INDEX.md) for every file in a single flat list, or [00-navigation-and-methodology/how-to-use-this-repository.md](00-navigation-and-methodology/how-to-use-this-repository.md) for role-based routing.

## Key Distinctions This Repository Maintains

- **Cost ≠ Spend ≠ Total Economic Cost**: three different claims, kept separate. See [terminology](00-navigation-and-methodology/terminology-and-glossary.md).
- **Output ≠ Task Completion ≠ Outcome ≠ Value**: four levels of claim, frequently conflated in AI ROI reporting. See [Value Progression](03-value-economics/value-progression.md).
- **Model Routing ≠ Workload Routing**: which model handles a task vs. whether a model is needed at all. See [05-architecture-and-design](05-architecture-and-design/workload-routing.md).
- **Lifecycle ≠ Governance**: lifecycle is *when*, governance is *who decides*. Kept as separate sections (06 vs. 07), matching the same distinction used in the companion [Responsible-AI](https://github.com/knowledgetrailsai/Responsible-AI) repository.

## Quick Start

1. Read [Core Principles](01-foundations/principles.md) and [The Two Ledgers](01-foundations/two-ledgers-cost-and-value.md).
2. Copy the [Outcome & Value Definition Sheet](templates/outcome-value-definition-sheet.md) for your workload and fill it in with your business owner (**before** any architecture work starts).
3. Run the [Economic Design Checklist](templates/economic-design-checklist.md) at architecture review.
4. See the [worked example](10-case-studies/customer-support-agent.md) for how this applies end-to-end, or check [09-sector-specific-finops](09-sector-specific-finops/claims-processing.md) if your workload type is covered.
5. New to rolling this out organization-wide? Start with the [90-Day Adoption Plan](11-implementation-playbooks/finops-adoption-90-day-plan.md).

## Relationship to companion repositories

Fulcrum is the [OASIS](https://github.com/knowledgetrailsai/OASIS) companion for Chapter 22, Economics, FinOps and Sustainability, covering the economic layer: cost, value, and the discipline connecting them. See the [Companion Repository Index](https://github.com/knowledgetrailsai/OASIS/blob/main/References/companion-repository-index.md) for how the other Part III chapters map to their own companions.

- **[Compass](https://github.com/knowledgetrailsai/responsible-ai)**: the responsible-AI, security, and governance companion (Chapters 19–20). A use case's regulatory obligations there often carry cost implications this repository's unit-economics tracking should surface.
- **[Helm](https://github.com/knowledgetrailsai/HELM)**: the deployment/AgentOps companion. The Economic plane in Helm's observability spec is the raw telemetry Fulcrum's cost-progression and value-per-outcome benchmarks depend on.
- **[Nexus](https://github.com/knowledgetrailsai/Nexus)**: the opportunity catalog. A use case's projected cost and value shape are estimated here once it reaches Fulcrum's cost/value framework.
- **[Forge](https://github.com/knowledgetrailsai/Forge)**, **[Loom](https://github.com/knowledgetrailsai/Loom)**, **[Verity](https://github.com/knowledgetrailsai/Verity)**, **[Ageis](https://github.com/knowledgetrailsai/Ageis)**, **[Axiom](https://github.com/knowledgetrailsai/Axiom)** — the data/knowledge, human-AI workflow, evaluation, coding-delivery, and model-architecture companions respectively; none carry direct cost dependencies on Fulcrum, but any of them can be the source of the effort or compute line items Fulcrum's cost model tracks.

## Contributing

This is a living methodology. See [CONTRIBUTING.md](CONTRIBUTING.md). Real Cost/Value Density benchmarks, Value Leakage patterns, sector-specific guidance, and case studies from production systems are especially welcome.

## Disclaimer

This repository provides general guidance and methodology. It is not financial or accounting advice. Figures used in examples are illustrative, not benchmarks. Always source your own Value per Outcome figures per [Phase 1](06-lifecycle/phase-1-define-baseline.md).

## License

Licensed under [CC BY-SA 4.0](https://github.com/knowledgetrailsai/OASIS/blob/main/LICENSE.md). Reuse and adaptation are welcome with credit to KnowledgeTrails-OASIS, a link to the license, an indication of changes, and release of adaptations under the same license.

## About Us

**Shripadraj Mujumdar** is an Agentic AI & Automation Strategist, Advisor, and Responsible AI Expert with 28+ years of experience in enterprise architecture and AI-driven transformation, including deep hands-on work in Agentic AI, Generative AI, and enterprise data and knowledge platforms. His practice spans designing multi-agent systems, knowledge-graph and RAG architectures, accelerated delivery capabilities, and Responsible AI governance frameworks aligned to global regulatory standards. This methodology ecosystem distills that practitioner experience (architecture, delivery, evaluation, governance, and economics) into a single, reusable body of work.

**Ankit Mirajkar** is a Data & AI Architect and technology consultant specializing in modern data platforms, enterprise data architecture, and Agentic AI. His expertise spans scalable data engineering, AI-ready data platforms, Generative AI, and cloud technologies, with a strong focus on turning complex data challenges into practical, production-ready solutions. He also works at the intersection of architecture, technology strategy, and innovation to help organizations build intelligent, scalable data ecosystems.
