# Value Leakage

`Home › 03-value-economics › Value Leakage`

## Definition

Value Leakage is business value lost to false positives, downstream rework, customer trust erosion, or compliance exposure created by the AI system itself. It is subtracted from gross outcome value to arrive at Realized Business Value — see [Value Calculation](value-calculation.md).

**Value Leakage is the most commonly omitted term in AI ROI calculations, and the most common source of overstated ROI.** Any value model that doesn't name its leakage sources should be treated as incomplete.

## Common Sources

| Source | Example | How It's Usually Missed |
|---|---|---|
| **False positives** | Agent marks a claim "approved" that should have been flagged for review | Counted as a successful outcome at the time; cost surfaces later, often in a different system |
| **Downstream rework** | Customer re-contacts support after an AI resolution that didn't actually fix the issue | The original ticket is marked "resolved" and closed before the rework need is visible |
| **Trust erosion** | Users stop trusting AI-generated recommendations after visible errors, reducing adoption and future value | Erosion happens gradually and rarely gets attributed back to specific AI failures |
| **Compliance exposure** | An AI decision creates regulatory or contractual risk not priced into the original value model | Risk materializes months later, disconnected from the original workflow's metrics |

## Why It's Missed

Leakage typically surfaces in a *different* system than the one that generated the original outcome — a reopened ticket in the ticketing system, a dispute in the billing system, a regulatory inquiry in a compliance system. Without deliberate cross-system tracking, each of these looks unrelated to the AI decision that caused it.

## Measuring It

For each identified leakage source, define:
1. A **proxy metric** trackable in an existing system (reopened-ticket rate, dispute rate, escalation-after-resolution rate)
2. A **cost per leaked unit** (average rework cost, average dispute-handling cost)
3. A **review cadence** — see [04-measurement-and-observability/metrics-catalog.md](../04-measurement-and-observability/metrics-catalog.md) and [07-governance/review-gates.md](../07-governance/review-gates.md)

This is defined at [Phase 1](../06-lifecycle/phase-1-define-baseline.md), tested at [Phase 4](../06-lifecycle/phase-4-pilot-calibrate.md), and tracked continuously at [Phase 5](../06-lifecycle/phase-5-operate-attribute.md).

---

**Previous:** [Value Calculation](value-calculation.md)
**Next:** [Value per Outcome — Benchmarking Guidance](value-per-outcome-benchmarks.md)
