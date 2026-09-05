# Total Economic Cost

`Home › 02-cost-economics › Total Economic Cost`

## The Formula

Raw AI spend understates true cost. Use the full equation:

```
Total Economic Cost = AI cost + failure cost + retry cost + human intervention + latency cost + opportunity cost
```

## Components

| Component | Definition | Example |
|---|---|---|
| **AI cost** | Tokens, model calls, tool calls, evaluation calls, retrieval, infrastructure | The number on the vendor invoice |
| **Failure cost** | Cost of incorrect outputs reaching production | A wrong refund amount issued to a customer |
| **Retry cost** | Cost of repeated attempts at the same task | An agent looping 20 times instead of 5 — see [Agentic Loop Multiplier](hidden-multipliers.md#2-agentic-loop-multiplier) |
| **Human intervention** | Cost of escalation to a human agent | A ticket the AI couldn't resolve, now handled by a support rep |
| **Latency cost** | Cost of slower resolution | Customer churn or SLA penalties from delayed response |
| **Opportunity cost** | Cost of capacity/attention diverted to fixing AI-driven issues | Engineering time spent debugging a cost spike instead of shipping features |

## Why This Matters: The Cheapest Model Trap

If the only objective is minimizing AI spend, organizations may systematically choose models too weak for the task. Suppose a low-cost model succeeds 70% of the time while a more expensive model succeeds 95% of the time. The cheaper model may generate more retries, more human escalation, more incorrect actions, more support effort, more downstream remediation.

The actual economic equation is broader than model cost. The objective isn't minimum AI spend. It's **minimum Total Economic Cost for the required level of quality, risk, and business value**.

## Where This Is Applied

- Compared against [Realized Business Value](../03-value-economics/value-calculation.md) to compute [Value Density](../04-measurement-and-observability/cost-value-density.md)
- Evaluated at the [architecture economic review gate](../07-governance/review-gates.md)
- Tracked continuously in [Phase 5 — Operate & Attribute](../06-lifecycle/phase-5-operate-attribute.md)

---

**Previous:** [Cost Progression](cost-progression.md)
**Next:** [The Three Hidden Multipliers](hidden-multipliers.md)
