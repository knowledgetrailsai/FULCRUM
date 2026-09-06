# Phase 5 — Operate & Attribute

`Home › 06-lifecycle › Phase 5`

[← Previous: Phase 4 — Pilot & Calibrate](phase-4-pilot-calibrate.md) · [Contents](../README.md) · [Next: Phase 6 — Optimize & Scale →](phase-6-optimize-scale.md)

**Objective:** Run the system in production with continuous cost and value attribution. This phase is ongoing; it does not have a fixed exit.

## Activities

1. Report Cost Density and Value Density per workflow, not just aggregate spend, on the cadence in [07-governance/review-gates.md](../07-governance/review-gates.md).
2. Route cost anomalies (iteration spikes, context bloat, unexpected evaluation volume) to the owning team directly.
3. Track Value Leakage as an ongoing metric, not a one-time estimate.
4. Maintain the dashboards defined in [templates/cost-value-dashboard-spec.md](../templates/cost-value-dashboard-spec.md).

## Exit Criteria

None. This phase is continuous for the life of the workflow. It feeds the review cadence in [Governance](../07-governance/review-gates.md) and the scale/retire decisions in [Phase 6](phase-6-optimize-scale.md).

## Owner

FinOps + workflow owners, jointly. See [Stakeholder Roles](../01-foundations/stakeholder-roles.md).

## Common Pitfalls

- Reverting to aggregate invoice review once pilot excitement fades, losing per-workflow attribution built in Phase 3
- Treating Value Leakage as fixed at the Phase 1/4 estimate rather than monitoring it as usage evolves
- No clear owner for responding to a cost anomaly, see [11-implementation-playbooks/incident-cost-spike-response.md](../11-implementation-playbooks/incident-cost-spike-response.md)

---

**Previous:** [Phase 4, Pilot & Calibrate](phase-4-pilot-calibrate.md)
**Next:** [Phase 6 — Optimize & Scale](phase-6-optimize-scale.md)

---

[← Previous: Phase 4 — Pilot & Calibrate](phase-4-pilot-calibrate.md) · [Contents](../README.md) · [Next: Phase 6 — Optimize & Scale →](phase-6-optimize-scale.md)
