# Phase 3 — Instrument

`Home › 06-lifecycle › Phase 3`

[← Previous: Phase 2, Architect for Economics](phase-2-architect.md) · [Contents](../README.md) · [Next: Phase 4 — Pilot & Calibrate →](phase-4-pilot-calibrate.md)

**Objective:** Build observability for both the cost ledger and the value ledger before the system goes live.

## Activities

1. Implement end-to-end tracing per [04-measurement-and-observability/tracing-and-attribution.md](../04-measurement-and-observability/tracing-and-attribution.md).
2. Instrument outcome capture against the Phase 1 definition — not just "did it complete without a technical error."
3. Instrument value capture where feasible — link to downstream systems (CRM, ticketing, ERP, billing).
4. Instrument the hidden multipliers directly: iteration count, context size, evaluation calls per task.

## Minimum Observability Bar

See [tracing-and-attribution.md](../04-measurement-and-observability/tracing-and-attribution.md#minimum-observability-bar) for the full field-level bar.

## Exit Criteria

Cost and outcome events are traceable per task **before rollout**, not retrofitted after Phase 4 or 5 has already started.

## Owner

Platform engineering.

## Common Pitfalls

- Instrumenting cost but not outcome, leaving Value Density impossible to calculate later
- Aggregating traces at the model level instead of the task level, losing the ability to attribute cost to a specific workflow
- Treating this as a "nice to have" that can be added post-launch: by the time the invoice reveals a problem, the attributable data to diagnose it doesn't exist

---

**Previous:** [Phase 2 — Architect for Economics](phase-2-architect.md)
**Next:** [Phase 4 — Pilot & Calibrate](phase-4-pilot-calibrate.md)

---

[← Previous: Phase 2, Architect for Economics](phase-2-architect.md) · [Contents](../README.md) · [Next: Phase 4 — Pilot & Calibrate →](phase-4-pilot-calibrate.md)
