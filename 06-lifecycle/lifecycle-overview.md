# Lifecycle Overview

`Home › 06-lifecycle › Overview`

AI FinOps is not a one-time exercise — it's a continuous lifecycle applied to every workload, from first definition through ongoing operation. Cost and value are calculated and tracked at every phase, not bolted on at the end.

## The Six Phases

| Phase | Objective | Owner |
|---|---|---|
| [1. Define & Baseline](phase-1-define-baseline.md) | Agree what "outcome" and "value" mean before design starts | Business owner + FinOps |
| [2. Architect for Economics](phase-2-architect.md) | Design against cost/value model, not just function | Architecture/engineering |
| [3. Instrument](phase-3-instrument.md) | Build tracing for cost and outcome before go-live | Platform engineering |
| [4. Pilot & Calibrate](phase-4-pilot-calibrate.md) | Validate projected density against real usage | Product + engineering |
| [5. Operate & Attribute](phase-5-operate-attribute.md) | Continuous cost/value attribution | FinOps + workflow owners |
| [6. Optimize & Scale](phase-6-optimize-scale.md) | Reallocate based on Value Density | Platform + business leadership |

## The Loop, Not the Line

Phase 6 feeds back into Phase 1: learnings, benchmarks, and known leakage sources compound as new or revised workloads enter the lifecycle. This is deliberately a loop, not a one-way pipeline — matching the operating-lifecycle model used in the companion [OASIS](https://github.com/knowledgetrailsai/OASIS) methodology.

## How the Two Ledgers Move Through the Phases

| Phase | Cost Ledger Activity | Value Ledger Activity |
|---|---|---|
| 1 | Baseline pre-AI cost documented | Outcome and value-per-outcome defined |
| 2 | Cost architecture designed, projected Cost Density | Projected Value Density |
| 3 | Cost tracing instrumented | Outcome/value tracing instrumented |
| 4 | Actual Cost Density measured | Actual Value Density measured, leakage identified |
| 5 | Cost Density tracked continuously | Value Density and leakage tracked continuously |
| 6 | Cost patterns reused across workloads | Workloads ranked by Value Density |

## Governance Overlay

Each phase transition is gated — see [07-governance/review-gates.md](../07-governance/review-gates.md) for the specific sign-off required at each boundary.

---

**Next:** [Phase 1 — Define & Baseline](phase-1-define-baseline.md)
