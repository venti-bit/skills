# Contract Review Checklist

Read the whole contract before commenting: definitions and later clauses often change the meaning of earlier ones.

## 1. Basics
- Parties correctly identified (full legal names, registration numbers, signatories with authority)
- Subject matter clearly defined; scope and deliverables measurable
- Term, start date, renewal (watch for **auto-renewal** and notice windows)
- Governing law and jurisdiction / arbitration venue and language

## 2. Money
- Price, currency, taxes (VAT included or not), indexation
- Payment terms, invoicing, late payment interest, set-off rights
- Prepayment and its protection (refund conditions)
- Price change rights — unilateral changes are a red flag

## 3. Performance & acceptance
- Timelines, milestones, dependencies on the other party
- Acceptance procedure: deadline to object, **deemed acceptance**
- Change request procedure

## 4. Liability & risk allocation (most important)
- Limitation of liability: cap amount, exclusions (indirect damages, lost profit), carve-outs (fraud, gross negligence, IP, confidentiality, data)
- Penalties / liquidated damages — symmetric? proportionate?
- Indemnities: scope, procedure, who controls defence
- Warranties and disclaimers
- Insurance requirements
- Force majeure: definition, notice, consequences, termination right after prolonged FM

## 5. IP & confidentiality
- Who owns results; licence vs. assignment; pre-existing IP; open source
- Confidentiality: definition, exceptions, duration, return/destruction
- Personal data processing: roles (controller/processor), DPA, cross-border transfer, compliance with applicable data protection law

## 6. Exit
- Termination for convenience (who can, notice, fees)
- Termination for breach (cure period)
- Consequences: payment for work done, return of materials, transition assistance, survival clauses

## 7. Boilerplate traps
- Non-compete / non-solicit (scope, duration, enforceability)
- Exclusivity
- Assignment / change of control
- Notices (addresses, email validity)
- Entire agreement clause wiping out earlier promises
- Priority of documents (contract vs. appendices vs. T&Cs)
- Unilateral amendment by reference to a website

## Classify each clause against the playbook

> Classification, redline format and negotiation tiers adapted (modified) from [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) `legal/skills/review-contract`, Apache-2.0.

Compare each material clause to the user's playbook (`playbook-template.md`) or, if there is none, to general market standards — say which basis you used.

- **GREEN — acceptable.** Matches or beats the standard position. Note it; no negotiation needed.
- **YELLOW — negotiate.** Outside the preferred position but within a common market range (e.g. cap at 6 months' fees vs. standard 12; 60-day renewal notice vs. 90). Give redline wording, a fallback, and the business impact of accepting vs. pushing back.
- **RED — escalate / do not sign as is.** Outside the acceptable range or materially risky: uncapped liability, broad uncapped indemnity, assignment of pre-existing IP, no data processing terms where personal data is processed, broad non-compete/exclusivity, hostile forum with mandatory arbitration. Explain the risk, the market alternative, estimated exposure, and who must decide. For a formal rating use `risk-assessment.md`.

Map to the summary table: RED → High, YELLOW → Medium, GREEN → Low/OK.

## Redline format
Provide ready-to-insert wording, firm on critical points but commercially reasonable (overly aggressive redlines slow deals):

```
Clause: s. 8.2 Limitation of liability — RED
Current: "Contractor shall be liable for all losses..."
Proposed: "Each Party's aggregate liability under this Agreement shall not exceed the fees paid
          in the 12 months preceding the claim, except for breach of confidentiality, fraud
          or wilful misconduct."
Rationale (can be shared with the counterparty): caps exposure at a commercially reasonable level.
Priority: Must-have / Should-have / Nice-to-have
Fallback: 24 months' fees, or a fixed amount of [●]
```

## Negotiation priorities
- **Tier 1 — must-haves (deal breakers):** liability protection, mandatory data-protection terms, protection of core IP, anything conflicting with law or regulation.
- **Tier 2 — should-haves:** cap level within range, indemnity scope and mutuality, termination flexibility, audit rights.
- **Tier 3 — concession candidates:** preferred governing law when the alternative is acceptable, notice periods, definitions polish, insurance certificates.

Strategy: lead with Tier 1, trade Tier 3 concessions for Tier 2 wins, never concede Tier 1 without escalation. Adjust tone to the relationship (new vendor vs. strategic partner).

## Practical notes
- Contract not in the user's language → ask whether to review in the original language or translate first; quote the original text.
- Very long contracts (50+ pages) → offer to cover the most material sections first, then the rest.

## Severity guide (without a playbook)
- **High**: unlimited liability, one-sided termination, loss of IP, unclear payment obligation, unenforceable protections for the user, regulatory non-compliance
- **Medium**: unfavourable but bounded terms (short cure periods, asymmetric penalties)
- **Low**: drafting quality, ambiguity unlikely to matter

