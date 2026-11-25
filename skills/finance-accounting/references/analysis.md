# Financial Statement Analysis

## Sanity checks first
- Balance sheet balances; retained earnings roll forward (opening + net income − dividends = closing)
- Cash flow statement reconciles to change in cash on the balance sheet
- Gross margin and opex lines are within plausible ranges; flag sudden jumps > 20-30% period over period

## Key ratios

| Group | Ratio | Formula |
|---|---|---|
| Profitability | Gross margin | (Revenue − COGS) / Revenue |
| | EBITDA margin | EBITDA / Revenue |
| | Net margin | Net income / Revenue |
| | ROE | Net income / Avg equity |
| | ROA | Net income / Avg total assets |
| Liquidity | Current ratio | Current assets / Current liabilities |
| | Quick ratio | (Cash + receivables + ST investments) / Current liabilities |
| Leverage | Debt / Equity | Total debt / Equity |
| | Net debt / EBITDA | (Debt − Cash) / EBITDA |
| | Interest coverage | EBIT / Interest expense |
| Efficiency | DSO | Receivables / Revenue × days |
| | DIO | Inventory / COGS × days |
| | DPO | Payables / COGS × days |
| | Cash conversion cycle | DSO + DIO − DPO |

Interpret ratios against: the company's own history, the industry, and the user's targets — a ratio alone means little.

## Variance analysis (plan vs. actual)
See `variance-analysis.md` for price/volume/mix decomposition, materiality thresholds, commentary and waterfalls.

## Cash & runway
- Monthly net burn = cash out − cash in (operating + investing, excluding financing)
- Runway (months) = current cash / average net burn (use last 3 months; state it)
- Distinguish profit from cash: growing receivables or inventory can make a profitable company run out of cash.
