# Incident Response: Triage, Communication, Postmortem

> Adapted (modified) from [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) `engineering/skills/incident-response`, Apache-2.0. Technical diagnosis itself lives in `troubleshooting.md`.

Ask which phase the incident is in if unclear: **new**, **update**, or **postmortem**.

## 1. Triage
| Level | Criteria | Response |
|---|---|---|
| SEV1 | Service down or data loss/security breach, all or most users affected | Immediately, all hands |
| SEV2 | Major feature degraded, many users affected, no workaround | Within 15 min |
| SEV3 | Minor feature broken, some users, workaround exists | Within 1 hour |
| SEV4 | Cosmetic / low impact | Next business day |
When in doubt, pick the higher severity; downgrading later is cheap.

Roles (one person may hold several in a small team):
- **Incident commander** — coordinates, decides, keeps the timeline; does not debug
- **Technical lead(s)** — diagnose and mitigate
- **Communications** — status updates to staff, customers, management

Start a timeline immediately (UTC timestamps): detection, actions, decisions, findings.

## 2. Mitigate before root-causing
Rollback the last change, fail over, disable a feature flag, scale up, block abusive traffic, free disk — restore service first. Record each action and its effect in the timeline. Destructive actions still need explicit confirmation.

## 3. Communicate
Update at a fixed cadence (SEV1: every 30 min; SEV2: hourly) even if nothing changed. Facts only: what is happening, who is affected, what we are doing, when the next update is. No speculation, no blame.

```
## Incident update: [title]
Severity: SEV[1-4] | Status: Investigating / Identified / Monitoring / Resolved
Impact: [who/what is affected]
Last updated: [time UTC] | Next update: [time]

Current status: …
Actions taken: …
Next steps: … (ETA if known)
```
Customer-facing version: plain language, no internal system names, acknowledge impact, give workaround if any, commit to the next update time.

## 4. Postmortem (blameless)
Write within a few days while memory is fresh. Focus on systems and processes, not individuals.

```
## Postmortem: [title]
Date · Duration · Severity · Authors · Status: draft/final

Summary — 2-3 sentences in plain language
Impact — users affected, duration, business impact (orders, revenue, SLA)
Timeline (UTC) — | time | event |
Root cause — technical explanation
5 whys
  1. Why did [symptom]? → because …
  …
  5. Why …? → [root cause, usually a process / safeguard gap]
Contributing factors — monitoring gaps, alert noise, missing runbook, risky deploy
What went well / what went poorly / where we got lucky
Action items — | action | owner | priority P0/P1/P2 | due date |
Lessons learned
```
Good action items are specific and verifiable ("add alert on disk > 85% on db hosts"), each with an owner and date. Prefer fixes that prevent a whole class of incidents (guardrails, automation, tests) over "be more careful".
