# Value per Outcome — Benchmarking Guidance

`Home › 03-value-economics › Value per Outcome Benchmarks`

This file provides a starting framework for setting Value per Outcome figures by workload type. These are illustrative structures, not universal numbers — every organization must source its own figures per [Phase 1](../06-lifecycle/phase-1-define-baseline.md).

## Approach by Workload Type

| Workload type | Recommended value basis | Notes |
|---|---|---|
| Customer support / service agents | Fully-loaded cost of equivalent human-handled interaction | Pull from existing support cost reporting, not estimation |
| Sales / lead qualification agents | Conversion rate uplift × average deal value | Requires a controlled comparison against a non-AI baseline |
| Coding / engineering agents | Engineer time saved × loaded hourly rate, for accepted changes only | Only count *accepted* changes — rejected suggestions have near-zero value and may carry review-time cost |
| Claims / document processing | Fully-loaded cost of equivalent manual processing, adjusted for accuracy | Weight by accuracy — a faster but less accurate process may have lower net value |
| Onboarding / account setup | Cost of manual onboarding + value of reduced time-to-first-value | Time-to-value effects are real but harder to isolate — treat conservatively |

## Principles for Setting Benchmarks

1. **Always use an existing, defensible source** — a cost report, a rate card, a conversion benchmark — never an engineering estimate. See [Value Calculation](value-calculation.md).
2. **Segment by outcome quality, not just completion.** A "resolved" outcome that later reopens is not the same value as one that doesn't — see [Value Leakage](value-leakage.md).
3. **Revisit quarterly.** Labor costs, conversion rates, and process costs shift — a Value per Outcome figure set a year ago may be stale. See [07-governance/review-gates.md](../07-governance/review-gates.md).
4. **Prefer sector-specific guidance where available** — see [09-sector-specific-finops/](../09-sector-specific-finops/claims-processing.md) for deeper treatment of individual workload types.

## Contributing Real Benchmarks

This repository intentionally avoids publishing specific dollar figures as universal benchmarks — value varies too much by industry, geography, and labor market. If you have real, anonymized Cost Density / Value Density figures from production, contribute them per [CONTRIBUTING.md](../CONTRIBUTING.md) as a [case study](../10-case-studies/case-study-template.md) rather than a benchmark table.

---

**Previous:** [Value Leakage](value-leakage.md)
**Next section:** [04-measurement-and-observability](../04-measurement-and-observability/cost-value-density.md)
