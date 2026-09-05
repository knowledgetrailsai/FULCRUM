# Sector Guidance: Customer Support Agents

`Home › 09-sector-specific-finops › Customer Support Agents`

## Outcome Definition Guidance

Define "resolved" precisely, e.g., no reopened or related ticket within a defined window (commonly 7 days). Avoid defining success as "response sent" or "ticket closed," both of which can be gamed by premature closure. See [Value Progression](../03-value-economics/value-progression.md).

## Value per Outcome Guidance

Use the fully-loaded cost of the equivalent human-handled ticket as the primary basis. See [Value per Outcome Benchmarks](../03-value-economics/value-per-outcome-benchmarks.md). Segment by ticket complexity if human handle time varies significantly by category.

## Typical Hidden Multipliers

- **Context Window Tax** is often severe here — full conversation history, customer profile, and order history are commonly sent on every turn. Prune aggressively.
- **Agentic Loop Multiplier** shows up in multi-step troubleshooting flows (diagnose → check account → check order → recommend fix). Set iteration ceilings per ticket category.

## Typical Value Leakage Sources

- Reopened tickets (the primary leakage signal)
- Refund/credit errors that surface as disputes later
- Customer trust erosion from visibly wrong resolutions, reducing self-service adoption

## Recommended Workload Routing

```
Account/order lookup → API call (not a model)
Intent classification → small model
Standard resolution → small-to-mid model
Ambiguous dispute or goodwill exception → larger model or human
```

See [Workload Routing](../05-architecture-and-design/workload-routing.md).

## Reference

Full worked example: [10-case-studies/customer-support-agent.md](../10-case-studies/customer-support-agent.md)

---

**Next:** [Coding Agents](coding-agents.md)
