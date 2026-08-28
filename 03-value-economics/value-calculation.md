# Value Calculation

`Home › 03-value-economics › Value Calculation`

## The Formula

```
Realized Business Value = Σ (Outcomes Achieved × Value per Outcome) − Value Leakage
```

## Components

**Outcomes Achieved** — count of successful, verified outcomes per workload, per the outcome definition agreed in [Phase 1](../06-lifecycle/phase-1-define-baseline.md). Must be measured against the Level 3 definition (see [Value Progression](value-progression.md)), not task completion.

**Value per Outcome** — pre-agreed monetary or proxy value per unit. Always name the source:

| Value type | Example source |
|---|---|
| Cost avoided | Fully-loaded cost of the equivalent human-handled task |
| Revenue generated | Conversion rate × average order value, for a sales-assist workload |
| Time saved | Hours saved × loaded hourly rate |
| Risk reduced | Expected cost of the risk event × reduction in probability |

**Value Leakage** — value lost to false positives, downstream rework, customer trust erosion, or compliance exposure created by the AI system. See [Value Leakage](value-leakage.md) for the full breakdown — this is the term most commonly omitted from AI ROI calculations.

## Worked Example

A support agent workload:
- Outcomes Achieved: 45,000 resolved tickets/month
- Value per Outcome: $8.40 (fully-loaded human-handled equivalent)
- Value Leakage: $12,000/month (reopened tickets requiring rework, estimated at the reopened-ticket rate × average rework cost)

```
Realized Business Value = (45,000 × $8.40) − $12,000 = $366,000/month
```

This figure, compared against [Total Economic Cost](../02-cost-economics/total-economic-cost.md), produces [Net AI Value and Value Density](../04-measurement-and-observability/cost-value-density.md).

## Why Naming the Source Matters

A Value per Outcome figure with no named source is an assumption dressed as a number. Requiring a source — a cost report, a conversion benchmark, a rate card — forces the value claim to be falsifiable, per [Principle 3](../01-foundations/principles.md#3-value-must-be-calculated-before-its-claimed).

---

**Previous:** [Value Progression](value-progression.md)
**Next:** [Value Leakage](value-leakage.md)
