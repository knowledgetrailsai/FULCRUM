# Phase 1 — Define & Baseline

`Home › 06-lifecycle › Phase 1`

**Objective:** Establish what "outcome" and "value" mean for this workload before any architecture exists.

## Why This Phase Exists

The single most common failure mode in AI economics is skipping this phase, building the system first, then trying to retrofit a value story once it's live. By then, the outcome definition tends to be whatever the system happens to produce, and the value figure tends to be whatever makes the business case work. This phase forces the definition to come first, from the business owner, before engineering has a stake in the answer.

## Activities

1. **Define the unit of successful outcome**, per the [Level 3 definition](../03-value-economics/value-progression.md). Be specific: "resolved ticket" needs a definition of "resolved."
2. **Assign Value per Outcome** ([formula](../03-value-economics/value-calculation.md)), agreed jointly with the business owner, not estimated unilaterally by engineering. See [benchmarking guidance](../03-value-economics/value-per-outcome-benchmarks.md).
3. **Baseline the current (pre-AI) cost** of achieving that outcome, for comparison. Without this, Net AI Value calculations in later phases have nothing to compare against.
4. **Define acceptable Value Leakage sources** and how they'll be measured. See [Value Leakage](../03-value-economics/value-leakage.md).

## Exit Criteria

A signed-off [Outcome & Value Definition Sheet](../templates/outcome-value-definition-sheet.md), completed **before** design starts.

## Owner

Product/business owner + FinOps lead. See [Stakeholder Roles](../01-foundations/stakeholder-roles.md) for why this split is deliberate.

## Common Pitfalls

- Defining the outcome in technical terms ("model returns a classification") instead of business terms ("customer's issue is resolved without escalation")
- Setting Value per Outcome without a named source. If you can't say where the number came from, it isn't ready
- Skipping the baseline because "there's no AI system to compare against yet": the baseline is the *current* process, AI or not

---

**Next:** [Phase 2 — Architect for Economics](phase-2-architect.md)
