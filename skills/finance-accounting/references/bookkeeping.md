# Bookkeeping Essentials

## Journal entries
Present as: date | account (Dr) | account (Cr) | amount | description. Debits always equal credits.

Common patterns:
- Sale on credit: Dr Accounts receivable / Cr Revenue (+ Cr VAT payable if applicable)
- Customer payment: Dr Cash / Cr Accounts receivable
- Prepaid expense: Dr Prepaid expenses / Cr Cash; monthly: Dr Expense / Cr Prepaid
- Accrued expense: Dr Expense / Cr Accrued liabilities
- Deferred revenue: Dr Cash / Cr Deferred revenue; on delivery: Dr Deferred revenue / Cr Revenue
- Depreciation: Dr Depreciation expense / Cr Accumulated depreciation
- Payroll: Dr Salary expense / Cr Salaries payable, Cr payroll taxes payable

Account names and numbering differ by jurisdiction's chart of accounts — map to the user's chart if provided.

## Bank reconciliation
1. Start with ending balance per bank and per books
2. Adjust bank side: deposits in transit (+), outstanding cheques/payments (−)
3. Adjust books side: bank fees (−), interest (+), errors, NSF
4. Adjusted balances must match; list every reconciling item
With CSV exports, match transactions programmatically by amount + date window + reference, then review unmatched items.

## Month-end close

> Close calendar and dependency levels adapted (modified) from [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) `finance/skills/close-management`, Apache-2.0. Compress for a small business (often 2-3 days) or extend for groups.

### Calendar (T = month end, business days)
- **Pre-close (T−3…T):** send calendar and deadlines; agree cut-off with payables, receivables, payroll, treasury; preliminary bank rec; review open purchase orders for accruals; collect info on unusual transactions.
- **T+1:** subledgers closed; accrue goods/services received but not invoiced; payroll and payroll accrual; cash receipts/payments to month end; intercompany postings; final bank rec; depreciation; prepaid amortisation.
- **T+2:** revenue recognition and deferred revenue; remaining accruals; receivables and payables subledger recs; inventory adjustments; FX revaluation; start balance sheet recs.
- **T+3:** finish all balance sheet recs and post adjustments; intercompany rec and eliminations; preliminary trial balance and P&L; first flux review.
- **T+4:** tax entries (income tax, VAT/sales tax); equity roll-forward; soft close; draft statements; detailed flux with variance commentary (`variance-analysis.md`); management review.
- **T+5:** final adjustments; hard close and lock the period; distribute reporting pack; update forecast; short retrospective on what slowed the close.

### Dependencies (what must finish first)
1. Cash entries, bank statements, payroll, depreciation, prepaid amortisation, payables accruals, intercompany postings — no dependencies
2. Bank rec, revenue recognition, receivables/payables recs, FX revaluation, remaining accruals — need level 1
3. All balance sheet recs, intercompany rec, adjusting entries, preliminary trial balance — need level 2
4. Tax, equity roll-forward, consolidation, draft statements, flux — need level 3
5. Management review, final adjustments, period lock, reporting, forecast update — need level 4

When asked to plan or track a close, produce a table: task | owner | day | depends on | status (not started / in progress / done / blocked) | notes — and highlight blocked items on the critical path.

### Close checklist
- All bank and card accounts reconciled
- Receivables/payables ageing reviewed; doubtful debt provision considered
- Accruals and prepayments posted
- Depreciation and amortisation posted
- Inventory counted/valued
- Intercompany balances agreed
- VAT/sales tax reconciled to ledger
- Trial balance reviewed for unusual balances
- Management reports produced and variances explained

## Caution
Tax rates, filing deadlines, and statutory forms are jurisdiction-specific and change. Provide them only with a source and a recommendation to verify with a licensed accountant.
