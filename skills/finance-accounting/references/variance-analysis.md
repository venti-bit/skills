# Variance Analysis (Plan vs. Actual vs. Forecast)

> Adapted (modified) from [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) `finance/skills/variance-analysis`, Apache-2.0. Currency-neutral; thresholds are defaults to adapt.

Always calculate with code or spreadsheet formulas and check that drivers add up to the total variance.

## Decomposition techniques

### Price / volume (/ mix)
```
Total variance = Actual − Budget (or Prior)
Volume effect  = (Actual qty − Budget qty) × Budget price
Price effect   = (Actual price − Budget price) × Actual qty
Check: Volume + Price = Total
```
Three-way (separating mix across products/segments):
```
Volume effect = (Actual total qty − Budget total qty) × Budget avg price at budget mix
Mix effect    = Σ (Actual qty_i − Actual total qty × Budget mix_i) × Budget price_i
Price effect  = Σ (Actual price_i − Budget price_i) × Actual qty_i
Check: Volume + Mix + Price = Total
```
Example: budget 10,000 units × 50 = 500,000; actual 11,000 × 48 = 528,000 → total +28,000 = volume +50,000 (more units) − price 22,000 (lower average price).

### Rate / mix (blended margins)
Product A margin 60%, B 40%. Budget mix 50/50 → 50% blended; actual mix 40/60 → 48%. Mix explains −2 pp of margin even if each product's margin is unchanged.

### Payroll
1. Headcount = (Actual HC − Budget HC) × Budget avg cost
2. Rate = (Actual avg cost − Budget avg cost) × Budget HC
3. Mix = shift in levels / departments
4. Timing = hires earlier/later than planned
5. Attrition = savings from unplanned departures (net of backfill/recruiting costs)

### Operating expenses
Split by: headcount-driven · volume-driven (hosting, fees, commissions, shipping) · discretionary (travel, events, consultants, marketing) · contractual/fixed (rent, insurance, subscriptions) · one-time (severance, settlements, write-offs) · timing/phasing.

## Materiality — what to investigate

| Comparison | % threshold (default) | Absolute threshold |
|---|---|---|
| Actual vs. budget | 10% | set by size, often 0.5-1% of revenue for P&L lines |
| Actual vs. prior period | 15% | same |
| Actual vs. forecast | 5% | same |
| Month over month | 20% | same |
Investigate when **either** threshold is exceeded. Prioritise: largest absolute amount → largest % (may be an error) → unexpected direction → newly off-track item → growing trend.

## Narrative for each material variance
```
[Line]: [favourable/unfavourable] [amount] ([%]) vs. [basis], [period]
Driver: 2-3 sentences with the business cause and quantified contributions.
Outlook: one-time / will continue / improving / worsening
Action: none / monitor / investigate / update forecast
```
Good commentary is specific, quantified, causal, forward-looking, actionable and short.
Avoid: "revenue is higher due to higher revenue" (circular); "costs were elevated" (vague); "timing" without saying what shifted and when it reverses; "one-off" without naming the item; "various small items" for a material amount; ignoring offsetting items.

## Waterfall (bridge)
Start value → 5-8 signed drivers (group the rest as "Other") → end value; verify start + drivers = end. Order drivers logically or largest positive to largest negative. Text version when no chart is available:
```
Q4 budget revenue                     10,000
  [+] New customers                     +800
  [+] Expansion of existing             +400
  [−] Discounts                         −200
  [−] Churn / contraction               −350
  [+] FX                                 +50
  [−] Deals slipped to Q1               −150
Q4 actual revenue                     10,550   (+550, +5.5% favourable)
```
Add a reconciliation table: driver | amount | % of total variance | cumulative. Individual drivers can exceed 100% when there are offsets. If a chart is wanted, use the dataviz guidance available (green favourable, red unfavourable, plus a total bar).

## Which comparison to use
- **Actual vs. budget** — annual performance, bonuses, board reporting (budget is fixed)
- **Actual vs. forecast** — operational management, spotting emerging issues
- **Forecast vs. budget** — how expectations have shifted since planning
- **Actual vs. prior period / prior year** — trends and seasonality; when the budget isn't meaningful

Three-way table: metric | budget | forecast | actual | var vs. budget (abs, %) | var vs. forecast (abs, %).

## Forecast accuracy
Accuracy = 1 − |Actual − Forecast| / |Actual|; MAPE = average of |Actual − Forecast| / |Actual| over periods.
Patterns: consistently favourable → budget too conservative; consistently unfavourable → too aggressive or execution problems; growing unfavourable → deterioration; shrinking through the year → normal; volatile → weak forecasting method.
