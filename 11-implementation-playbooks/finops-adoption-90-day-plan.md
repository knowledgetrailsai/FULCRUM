# Playbook: 90-Day AI FinOps Adoption Plan

`Home › 11-implementation-playbooks › 90-Day Adoption Plan`

[← Previous: Playbook: Architecture Economic Review](architecture-review-playbook.md) · [Contents](../README.md) · [Next: Playbook: Cost Spike Incident Response →](incident-cost-spike-response.md)

A starting plan for an organization moving from [Maturity Level 0 or 1](../08-maturity-model/maturity-levels.md) toward Level 3.

## Days 1–30: Visibility

- Identify the top 3–5 highest-spending AI workflows from current invoicing.
- Build task-level tracing for those workflows per [Tracing and Attribution](../04-measurement-and-observability/tracing-and-attribution.md).
- Calculate current Cost Density (even if Value Density isn't yet possible) — see [Cost Progression](../02-cost-economics/cost-progression.md).

**Exit target:** Level 1 → 2 on the [maturity model](../08-maturity-model/maturity-levels.md).

## Days 31–60: Value Definition

- For each identified workflow, run [Phase 1 — Define & Baseline](../06-lifecycle/phase-1-define-baseline.md) retroactively: define outcomes, assign value per outcome, identify leakage sources.
- Complete the [Outcome & Value Definition Sheet](../templates/outcome-value-definition-sheet.md) for each.
- Begin tracking Value Density alongside Cost Density.

**Exit target:** Level 2 → 3.

## Days 61–90: Governance

- Stand up the [review gates](../07-governance/review-gates.md). Require the [Economic Design Checklist](../templates/economic-design-checklist.md) for any new workload from this point forward.
- Build the [Level 1–2 dashboards](../04-measurement-and-observability/dashboard-design.md) for ongoing tracking.
- Run the first quarterly portfolio review ([Phase 6](../06-lifecycle/phase-6-optimize-scale.md)) ranking existing workflows by Net AI Value.

**Exit target:** Governance structure in place; Level 3 sustained, Level 4 targeted for highest-spend workflows within the next two quarters.

---

**Previous:** [Architecture Review Playbook](architecture-review-playbook.md)
**Next:** [Cost Spike Incident Response](incident-cost-spike-response.md)

---

[← Previous: Playbook: Architecture Economic Review](architecture-review-playbook.md) · [Contents](../README.md) · [Next: Playbook: Cost Spike Incident Response →](incident-cost-spike-response.md)
