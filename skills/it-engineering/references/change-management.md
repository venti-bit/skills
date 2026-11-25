# Deploys and Architecture Decisions

> Deploy checklist and ADR format adapted (modified) from [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) `engineering/skills/deploy-checklist` and `engineering/skills/architecture`, Apache-2.0.

## Pre-deploy checklist
Tailor it: ask whether the change has DB migrations, feature flags, breaking API changes, or infrastructure changes.

```
## Deploy checklist: [service / release] — [date], deployer: [name]

Before
- [ ] CI green (tests, lint, security scan)
- [ ] Code reviewed and approved
- [ ] No known critical bugs in the release
- [ ] DB migrations tested on a production-like copy; backward compatible (expand → migrate → contract)
- [ ] Backup / snapshot taken if data changes are involved
- [ ] Feature flags configured; default off for risky features
- [ ] Rollback plan written (how, how long, who)
- [ ] On-call and stakeholders notified; not deploying right before a weekend/holiday unless necessary

During
- [ ] Deploy to staging, run smoke tests
- [ ] Production rollout: canary / one node first if possible
- [ ] Watch error rate, latency, saturation for 15+ minutes
- [ ] Check key user flows (login, checkout, …)

After
- [ ] Metrics back to baseline
- [ ] Changelog / release notes updated
- [ ] Related tickets closed, stakeholders informed

Rollback triggers (decide BEFORE deploying)
- Error rate > [x]% (baseline [y]%)
- p95 latency > [x] ms
- [critical flow] fails
```
Extra steps: breaking API change → notify consumers, version the API, keep the old version during a deprecation window. Infrastructure change → `terraform plan` / dry run reviewed, change window agreed.

## Architecture Decision Record (ADR)
Use when choosing between technologies or documenting a design trade-off. Ask for constraints first: load, latency, budget, deadline, team skills, compliance. Always compare at least two real options (including "do nothing / keep current").

```
# ADR-[n]: [title]
Status: Proposed / Accepted / Deprecated / Superseded by ADR-[m]
Date · Deciders

## Context
Situation, forces, constraints, non-functional requirements.

## Options
### A: [name]
| Dimension | Assessment |
|---|---|
| Complexity | Low/Med/High |
| Cost (build + run) | … |
| Scalability / performance | … |
| Reliability / operations burden | … |
| Team familiarity | … |
| Lock-in / reversibility | … |
Pros · Cons
### B: …

## Decision
What we chose and the main reason.

## Consequences
What becomes easier · what becomes harder · what we must revisit and when

## Action items
- [ ] …
```
Store ADRs in the repository (e.g. `docs/adr/`) so decisions are versioned with the code.
