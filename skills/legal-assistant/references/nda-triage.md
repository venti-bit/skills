# NDA Triage (GREEN / YELLOW / RED)

> Adapted (modified) from [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) `legal/skills/triage-nda`, Apache-2.0. Generalised for any jurisdiction.

Use for a fast go/no-go on an incoming NDA. If the document contains substantive commercial terms (exclusivity, pricing, IP licences), it is not really an NDA — classify RED and do a full contract review instead (`contract-review.md`).

## Defaults (when the user has no playbook)
State that defaults are used.
- Mutual obligations (unless only one side discloses)
- Agreement term 1-3 years; confidentiality survives 2-5 years (trade secrets: as long as they remain secret)
- All five standard carve-outs present (below)
- No non-solicit, non-compete, exclusivity, standstill (outside M&A)
- No residuals clause, or narrowly scoped
- Governing law in a reasonable jurisdiction for both parties

## Screening checklist
1. **Structure** — mutual vs. one-way; matches the relationship; standalone document
2. **Definition** — not overbroad ("all information of any kind whether or not marked"); workable marking rules (e.g. written confirmation of oral disclosures within 30 days); excludes public / independently developed info
3. **Obligations** — reasonable standard of care; use limited to the stated purpose; disclosure only on need-to-know to people bound by similar duties; no impractical obligations (encrypt everything, physical logs)
4. **Standard carve-outs** — all must be present:
   - publicly available through no fault of the recipient
   - already known before disclosure
   - independently developed without use of the confidential info
   - rightfully received from a third party without restriction
   - disclosure required by law / court / regulator (with notice where legally allowed)
5. **Permitted disclosures** — employees, contractors/advisers under similar duties, affiliates if needed, regulators
6. **Term** — reasonable; not perpetual (except trade secrets)
7. **Return / destruction** — on termination or request; exception for copies required by law or kept in backups; simple certification (not sworn affidavit)
8. **Remedies** — injunctive relief acknowledgement is normal; no liquidated damages / penalties; symmetric in a mutual NDA
9. **Red-flag provisions** — non-solicit, non-compete, exclusivity, standstill, broad residuals, IP assignment or licence, audit rights
10. **Law & forum** — reasonable and consistent; no mandatory arbitration in an unfavourable seat

## Classification
**GREEN — sign under standard authority.** All defaults met: mutual (or correct direction), all carve-outs, term in range, no restrictive covenants, reasonable law, standard remedies, permitted disclosures include staff and advisers, retention exception, reasonable definition.

**YELLOW — lawyer review, likely one pass of small edits.** For example: definition broader than preferred; term longer but within market range (5 years term / 7 years survival); one missing carve-out that is easy to add; narrow residuals clause; acceptable but non-preferred jurisdiction; minor asymmetry; no explicit retention exception; unusual but harmless clauses.

**RED — do not sign as is.** Any of: one-way in the wrong direction; missing independent-development or legal-compulsion carve-out; non-solicit / non-compete / exclusivity / standstill; 10+ years or perpetual without trade-secret reason; definition that captures public or independently developed info; broad residuals (a de-facto licence); hidden IP assignment or licence; liquidated damages; unrestricted audit rights; hostile jurisdiction with mandatory arbitration; not actually an NDA.

## Report
```
## NDA Triage: [GREEN / YELLOW / RED]
Parties: … | Type: mutual / one-way (who discloses) | Term: … | Governing law: … | Basis: playbook / defaults

| Criterion | PASS / FLAG / FAIL | Notes (quote section) |
|---|---|---|

### Issues
[#] [YELLOW/RED] What — Risk — Proposed wording

Recommendation: sign / send to lawyer with these notes / reject and send our standard NDA
```
Typical routing: GREEN same day; YELLOW 1-2 business days; RED full review, counter with own standard form.

## Standard fixes
- **Overbroad definition** → limit to non-public information disclosed for the Purpose that is marked confidential or that a reasonable person would understand to be confidential.
- **No independent-development carve-out** → add it; without it, the counterparty could claim your own later products derive from their information.
- **Non-solicit** → delete; if insisted on, limit to active targeted solicitation (general job ads excluded) for ≤ 12 months.
- **Residuals** → resist; if required, limit to general know-how retained in unaided memory, exclude trade secrets and patentable info, and state that no IP licence is granted.
- **Perpetual term** → fixed 2-5 years from disclosure, with a trade-secret exception.
