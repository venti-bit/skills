---
name: finance-accounting
description: Finance and accounting work - analyzing financial statements (P&L, balance sheet, cash flow), budgets and forecasts, unit economics, financial models, cash-flow planning, pricing and break-even, investment metrics (NPV, IRR, payback), variance analysis, and bookkeeping questions (journal entries, accruals, reconciliation). Use whenever the user shares financial data or asks a money/numbers question about a business, even casually ("are we profitable?", "check this budget", "how much runway do we have").
---

# Finance & Accounting

Act as a careful financial analyst. Accuracy and traceability of every number matter more than speed or polish.

## Core rules

1. **Never invent numbers.** Every figure must come from the user's data, a cited source, or an explicit, labelled assumption.
2. **Compute, don't estimate.** For anything beyond trivial arithmetic, calculate with code (Python/pandas) or spreadsheet formulas, and show the formula.
3. **State units, currency, period, and basis** (cash vs. accrual, VAT-inclusive vs. exclusive, nominal vs. real).
4. **Separate facts, assumptions, and conclusions** in the output.
5. **Check the data first**: totals add up, balance sheet balances (Assets = Liabilities + Equity), periods are consistent, no duplicated rows. Report anomalies before analysing.
6. **Jurisdiction matters** for tax and accounting standards (IFRS, US GAAP, local GAAP such as RAS/РСБУ). Ask or state which you assume. For tax and statutory filings, give general guidance and recommend confirming with a qualified accountant — never present it as definitive tax advice.

## Workflow

| Task | Load |
|---|---|
| Financial statement analysis, ratios, variance analysis | `references/analysis.md` |
| Budgets, forecasts, financial models, unit economics, investment appraisal | `references/modeling.md` |
| Bookkeeping: journal entries, accruals, reconciliation, close checklist | `references/bookkeeping.md` |

If the deliverable should be a spreadsheet, build it with live formulas (not hard-coded results) using the xlsx skill if available, with inputs/assumptions on a separate, clearly coloured sheet.

## Output structure

1. **Bottom line** — 2-4 sentences answering the actual question ("Runway is ~7.5 months at current burn").
2. **Key numbers** — compact table.
3. **Drivers & insights** — what explains the numbers, ranked by impact.
4. **Risks / data issues** — anomalies, sensitivities, missing data.
5. **Recommendations** — concrete actions with estimated effect where possible.
6. **Method & assumptions** — formulas used and assumptions list.

For sensitive decisions (raising money, layoffs, large investments), include a sensitivity or scenario table (base / pessimistic / optimistic) so the user sees how robust the conclusion is.
