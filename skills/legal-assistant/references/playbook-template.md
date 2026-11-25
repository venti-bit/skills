# Company Legal Playbook — Template

> Concept adapted from [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) `legal` plugin (Apache-2.0).

Offer this template when the user reviews contracts regularly. Once filled in and saved (e.g. as `legal-playbook.md` in the project or uploaded to the conversation), reviews compare each clause with *their* positions instead of generic market standards.

```markdown
# Legal Playbook — [Company]
Jurisdiction(s): …   Default governing law: …   Language of contracts: …
Usual role: customer / vendor / both

## Signing authority
- GREEN items: [role] can sign
- YELLOW: needs [lawyer / head of legal]
- RED / value above [amount]: needs [CEO / outside counsel]

## Standard positions
| Clause | Preferred | Acceptable without escalation | Escalate if |
|---|---|---|---|
| Liability cap | 12 months' fees, mutual | 6-24 months' fees | Uncapped / < 3 months |
| Cap carve-outs | Fraud, wilful misconduct, confidentiality, data | + IP indemnity | Any breach uncapped |
| Indirect damages | Excluded mutually | Excluded with carve-outs | Not excluded |
| Indemnities | Mutual, IP + third-party claims | Unilateral IP from vendor | Broad "any breach" |
| IP | Each keeps pre-existing; we own deliverables we pay for | Licence to deliverables | Assignment of our pre-existing IP |
| Personal data | DPA signed, breach notice ≤ 72 h | | No DPA |
| Payment | Net 30, no unilateral price changes | Net 15-45, CPI indexation | Prepayment > 50% without security |
| Term / renewal | 1 year, auto-renew with 60-90 days' notice | | Auto-renew with < 30 days' notice |
| Termination for convenience | Both, 30-90 days | Only us | Only them |
| Governing law / forum | … | … | … |
| Non-compete / exclusivity | None | Narrow, ≤ 12 months | Broad |

## NDA defaults
Mutual · term … years · survival … years · required carve-outs … · forbidden: non-solicit, non-compete, residuals

## Clauses we always add
- …
```
