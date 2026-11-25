# Budgets, Forecasts & Models

## Model structure (spreadsheet)
1. **Inputs / Assumptions** — every driver in one place, coloured (e.g. blue font), with source/comment
2. **Calculations** — formulas only, no hard-coded numbers
3. **Outputs** — P&L, cash flow, balance sheet (if needed), KPI dashboard
4. **Checks** — balance check, cash ≥ 0 warning, totals tie out

Monthly granularity for the first 12-24 months, then quarterly/annual.

## Driver-based forecasting
Revenue = customers × conversion × average check × frequency (or MRR build: opening MRR + new + expansion − churn − contraction).
Costs: split into fixed, variable (% of revenue or per unit), and step costs (e.g. new hire every N customers).

## Unit economics
- Contribution margin per unit = price − variable cost per unit
- CAC, LTV, LTV/CAC, payback period = CAC / (monthly contribution per customer)
- Break-even volume = fixed costs / contribution margin per unit
- Break-even revenue = fixed costs / contribution margin ratio

## Investment appraisal
- NPV = Σ CF_t / (1 + r)^t − initial investment; state the discount rate and why
- IRR: rate where NPV = 0; beware multiple IRRs with sign-changing cash flows
- Payback & discounted payback
- Always include a sensitivity table on the 2-3 most uncertain drivers

## Scenarios
Base / pessimistic / optimistic with explicit driver differences; present in a single comparison table. Optionally a tornado-style ranking of drivers by impact.

## Pricing
Check cost-plus floor, competitor range, and value-based ceiling. Model the volume needed to keep the same gross profit after a price change:
required volume change = −Δprice / (current margin % + Δprice %).
