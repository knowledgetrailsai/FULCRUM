# Core Principles

`Home › 01-foundations › Core Principles`

These six principles anchor every section of this repository. If a decision conflicts with one of these, the decision is wrong, not the principle.

## 1. Token cost is not outcome cost

Consumption without value is waste. Two systems can spend identical tokens and deliver entirely different business value. Measure cost and outcome together, always — never cost alone. See [Two Ledgers](two-ledgers-cost-and-value.md).

## 2. Cost is architectural, not incidental

Every major cost driver (context size, agent loop count, evaluation depth, model routing) is a design decision made before deployment. The invoice is simply the financial record of decisions made months earlier. See [Cost Economics](../02-cost-economics/hidden-multipliers.md).

## 3. Value must be calculated before it's claimed

No AI investment case is valid without an explicit, falsifiable value model: a defined outcome, an agreed value per outcome, and a named source for that figure. "Users like it" is not a value model. See [Value Economics](../03-value-economics/value-calculation.md).

## 4. Shift left

Economics belongs in architecture review, alongside security and reliability — not in a finance review that happens after the system ships. See [Phase 2: Architect for Economics](../06-lifecycle/phase-2-architect.md).

## 5. Optimize for total economic cost, not minimum spend

The cheapest model is not always the most economical choice. A weaker model with more retries and escalations can cost more overall than a stronger, pricier one. See [Total Economic Cost](../02-cost-economics/total-economic-cost.md).

## 6. You cannot manage what you cannot attribute

Cost and value must both be traceable to a specific workflow, agent, and step, not just visible in aggregate. A monthly invoice total is not FinOps. Attribution down to the workflow is. See [Measurement and Observability](../04-measurement-and-observability/tracing-and-attribution.md).

---

**Previous:** [What Is AI FinOps](what-is-ai-finops.md)
**Next:** [The Two Ledgers, Cost and Value](two-ledgers-cost-and-value.md)
