# Stakeholder Roles

`Home › 01-foundations › Stakeholder Roles`

AI FinOps fails when one role tries to own both ledgers alone. This methodology deliberately splits ownership.

| Role | Owns | Does Not Own |
|---|---|---|
| **Business/Product Owner** | Outcome definition, value per outcome, acceptable Value Leakage (see [Phase 1](../06-lifecycle/phase-1-define-baseline.md)) | Cost architecture decisions |
| **Architecture/Engineering Lead** | Cost architecture — routing, context design, evaluation depth (see [Phase 2](../06-lifecycle/phase-2-architect.md)) | Value-per-outcome figures |
| **Platform Engineering** | Instrumentation and tracing (see [Phase 3](../06-lifecycle/phase-3-instrument.md)) | Outcome/value definitions |
| **FinOps Lead** | Ongoing attribution, reporting, review cadence (see [Phase 5](../06-lifecycle/phase-5-operate-attribute.md)) | Architecture decisions |
| **Platform + Business Leadership** | Scale/retire decisions using Net AI Value (see [Phase 6](../06-lifecycle/phase-6-optimize-scale.md)) | Day-to-day workflow operation |

## Why the Split Matters

If engineering sets the value-per-outcome figure, the business case tends to justify the build already underway. If the business owner sets cost architecture, technical tradeoffs get made without engineering judgment. The split forces the two ledgers to be independently defensible — see [Principle 3: Value must be calculated before it's claimed](principles.md#3-value-must-be-calculated-before-its-claimed).

Full decision-rights detail, including escalation: [07-governance/decision-rights.md](../07-governance/decision-rights.md).

---

**Previous:** [The Two Ledgers](two-ledgers-cost-and-value.md)
**Next section:** [02-cost-economics](../02-cost-economics/cost-progression.md)
