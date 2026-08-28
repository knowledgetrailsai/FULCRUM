# Contributing to OASIS AI FinOps

This is a living methodology, released under MIT to support AI-led digital transformation. Contributions are welcome from practitioners applying it in real deployments.

## What's Most Valuable

- **Real benchmarks** — Cost Density and Value Density figures from production workloads, anonymized.
- **Value Leakage patterns** — documented cases where realized value was overstated, and how it was caught.
- **Case studies** — filled examples following `10-case-studies/case-study-template.md`.
- **Sector-specific guidance** — new files under `09-sector-specific-finops/` for workload types not yet covered.
- **Instrumentation patterns** — concrete approaches to tracing iteration count, context size, and evaluation-layer cost per task.
- **Playbooks** — new implementation playbooks under `11-implementation-playbooks/`.

## How to Contribute

1. Fork the repository.
2. For new case studies, use `10-case-studies/case-study-template.md`.
3. For changes to core methodology (`01-foundations/` through `08-maturity-model/`), open an issue first — these sections anchor the templates and playbooks, so changes should be deliberate.
4. Submit a pull request with a clear description of what changed and why.
5. If you add or rename a file, update `INDEX.md` and the relevant section listing in `README.md` — they should never drift from the actual file tree.

## Issue Templates

Use the templates under `.github/ISSUE_TEMPLATE/` for proposing a case study, reporting a methodology gap, or suggesting a new metric.

## Code of Conduct

Be direct, be constructive, and back claims with real data where possible. This methodology improves through practitioners sharing what actually happened in production — including failures.
