---
name: hr-recruiting
description: HR and recruiting workflows - writing job descriptions and vacancy posts, screening and comparing resumes/CVs against requirements, structured interview plans and scorecards, test assignments, candidate outreach and rejection messages, offers, compensation benchmarking and pay bands, people analytics (headcount, attrition), onboarding plans, performance reviews, calibration and feedback, competency matrices, employee surveys, and HR policies. Use whenever the user is hiring, evaluating candidates or employees, or writing people-related documents, even if phrased casually ("help me find a good backend dev", "how do I give feedback to my team lead").
license: Apache-2.0. Includes material adapted from anthropics/knowledge-work-plugins; see LICENSE.txt
---

# HR & Recruiting

Help hire well and manage people fairly. Output should be structured, evidence-based, and free from discrimination.

## Core rules

1. **Job-related criteria only.** Evaluate candidates and employees on skills, experience, and behaviour relevant to the role. Never score, filter, or comment on protected characteristics (age, gender, ethnicity, religion, disability, pregnancy, marital status, sexual orientation, nationality, etc.), and avoid proxies (graduation year as age, photos, "culture fit" without definition). If the user asks for such filtering, explain the legal and ethical problem and offer a compliant alternative.
2. **Evidence over impressions.** Every assessment must cite what in the resume / answer supports it. Mark gaps as "not evidenced" rather than "no".
3. **Humans decide.** Screening output is a recommendation for a recruiter, not an automated rejection.
4. **Local labour law** governs contracts, probation, termination, overtime, and data retention — flag when something should be checked with HR legal.
5. **Confidentiality.** Treat candidate and employee data as personal data; don't add it to external tools without need.

## Workflow

| Task | Load |
|---|---|
| Job descriptions, vacancy posts, sourcing, outreach | `references/hiring.md` (section 1-2) |
| Resume screening, interviews, scorecards, test tasks, offers | `references/hiring.md` (section 3-5) |
| Onboarding, performance reviews, feedback, competency matrix, policies, surveys | `references/people-management.md` |
| Salary benchmarks, pay bands, compa-ratio, pay equity; headcount/attrition reports; rating calibration | `references/compensation-and-analytics.md` |

If the company has an HR settings file (levels, pay bands, review cycle, policies, e.g. `hr-settings.md`), load it first and use it over generic defaults.

## Resume screening output

Start from a requirements list (must-have vs. nice-to-have, agreed with the user). Then for each candidate:

| Candidate | Must-haves met | Nice-to-haves | Evidence | Red flags / questions | Score (1-5) | Recommendation |
|---|---|---|---|---|---|---|

Follow with a ranked shortlist and 3-5 tailored interview questions per shortlisted candidate to probe the gaps. Note: "Scores are based only on resume content; verify in interview."

## Tone for candidate-facing messages

Respectful, specific, concise. Rejections: thank, give a brief (non-legal-risk) reason if appropriate, leave the door open; never mention protected characteristics.
