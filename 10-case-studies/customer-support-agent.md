# Case Study: Tier-1 Customer Support Agent

`Home › 10-case-studies › Customer Support Agent`

This example walks a single workload — a billing-inquiry support agent — through all six phases, illustrating how the framework applies in practice. Figures are illustrative, not benchmarks. See [sector guidance](../09-sector-specific-finops/customer-support-agents.md) for general treatment of this workload type.

## Phase 1 — Define & Baseline

- **Outcome definition:** A billing inquiry is "resolved" if the customer does not reopen the same ticket, or open a related one, within 7 days.
- **Value per outcome:** $8.40 — average fully-loaded cost of a human agent handling an equivalent ticket, per the support team's cost report.
- **Baseline cost (pre-AI):** $8.40 per ticket, 100% human-handled, average 6-minute handle time.
- **Expected volume:** 50,000 billing tickets/month.
- **Value Leakage risks identified:** (1) agent gives an incorrect refund amount not caught until a later dispute; (2) agent resolves the immediate question but the underlying billing error recurs next cycle, generating a new ticket that looks unrelated.
- **Leakage measurement:** reopened/related-ticket rate within 7 days, and refund-dispute rate within 30 days.

## Phase 2 — Architect for Economics

- Workload routing applied ([Workload Routing](../05-architecture-and-design/workload-routing.md)): account-balance lookups → direct API call, not a model. Refund-eligibility checks → small classification model. Only ambiguous disputes reach a larger reasoning model.
- Evaluation layer added only for refund-issuing actions (financial risk), not informational queries — applying [proportional evaluation](../02-cost-economics/hidden-multipliers.md#3-shadow-tax-of-evaluation).
- Iteration ceiling set at 6 steps per ticket; anything requiring more escalates to a human.
- **Projected Cost Density:** $0.35/resolved ticket.
- **Projected Value Density:** $8.40 ÷ $0.35 ≈ 24x.

## Phase 3 — Instrument

- Each ticket traced end-to-end: intent classification → tool calls (balance lookup, refund check) → model reasoning step (if triggered) → evaluation (if a refund is issued) → outcome.
- Outcome capture linked to the ticketing system: "successful" only if no related ticket reopens within 7 days.
- Iteration count, context size, and evaluation-trigger rate instrumented per ticket from day one.

## Phase 4 — Pilot & Calibrate

- Piloted on 5,000 tickets/month for one quarter.
- **Actual Cost Density:** $0.52/resolved ticket — higher than projected. Root cause: the small classification model had lower-than-expected accuracy on ambiguous billing categories, pushing more tickets into the larger reasoning model than anticipated.
- **Actual Value Density:** $8.40 ÷ $0.52 ≈ 16x — still strongly positive, below the 24x projection.
- Remediation: retrained the classification model on a broader set of billing categories, reducing large-model escalation rate from 22% to 9% in the next cycle.

## Phase 5 — Operate & Attribute

- Weekly dashboard tracks Cost Density and Value Density per ticket category separately, not as one blended number.
- Value Leakage tracked monthly: reopened-ticket rate held at 3.1%, within the 5% tolerance set in Phase 1. Refund-dispute rate held at 0.4%.
- One cost anomaly caught in month 3: an iteration-count spike traced to a new billing promotion confusing the classifier — routed to engineering within the week rather than surfacing only in the next invoice cycle.

## Phase 6 — Optimize & Scale

- After two quarters at Level 3 maturity ([Maturity Model](../08-maturity-model/maturity-levels.md)), the workflow scaled from 5,000 to the full 50,000 monthly ticket volume.
- The classification/routing pattern was reused for a second workload (shipping inquiries) rather than re-derived from scratch.
- Quarterly portfolio review ranked this workflow's Value Density (16x) as the highest of all active AI workloads, informing the decision to expand it to Tier-2 tickets next.

## Net AI Value at Full Scale (illustrative)

```
Realized Business Value = 50,000 × $8.40 − Value Leakage ≈ $415,000/month
Total Economic Cost      = 50,000 × $0.52 ≈ $26,000/month
Net AI Value              ≈ $389,000/month
```

---

**Back to:** [10-case-studies](case-study-template.md) · [09-sector-specific-finops/customer-support-agents.md](../09-sector-specific-finops/customer-support-agents.md)
