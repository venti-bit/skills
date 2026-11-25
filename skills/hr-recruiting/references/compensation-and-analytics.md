# Compensation & People Analytics

> Compensation framework, people-report metrics and calibration steps adapted (modified) from [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) `human-resources/skills/comp-analysis`, `people-report` and `performance-review`, Apache-2.0. Currency- and country-neutral.

Pay and HR data are highly sensitive personal data: work with the minimum needed, prefer employee IDs to names, and report demographic breakdowns only in aggregate for groups of 5 or more people.

## Compensation analysis

### Total compensation
Base salary (state gross/net per local practice) · variable pay (bonus, commission) · equity (options, RSUs, phantom shares) · one-off (sign-on, relocation) · benefits (insurance, pension, perks).

Benchmark by **role, level, location, company stage, industry**. Always state data sources and their date. Without a salary data tool, use public salary surveys, job boards and the user's own data — label figures as estimates.

### Market benchmark output
| Percentile | Base | Variable | Equity (annualised) | Total |
|---|---|---|---|---|
| P25 | | | | |
| P50 | | | | |
| P75 | | | | |
| P90 | | | | |
Sources: … (date). Typical positioning: P50 for most roles, P75 for critical/scarce skills.

### Pay bands
- Band: min / midpoint / max; spread commonly 30-50% (min to max); adjacent levels overlap 10-20%
- **Compa-ratio** = salary / band midpoint (0.9-1.1 is normal; < 0.85 retention risk; > 1.15 check level or band)
- **Range penetration** = (salary − min) / (max − min)

Band analysis table: employee ID | level | salary | min | mid | max | compa-ratio | position (below/in/above) | note.
Flag outliers, people below band, pay compression (new hires paid more than tenured staff at the same level) and unexplained gaps between comparable roles.

### Pay equity check
Compare pay for the same role and level across groups, controlling for legitimate factors (level, location, tenure, performance). Unexplained gaps should be investigated and fixed; recommend legal input where pay transparency / equal-pay laws apply.

### Offers
Recommend a range, not a point: where in the band and why (skills, market, internal equity). Note negotiation room and the internal-equity impact of going above band.

## People reports

### Metrics
- **Headcount** — by team, location, level, tenure; hires and leavers in period
- **Attrition rate** = leavers in period / average headcount in period (annualise monthly figures × 12); split voluntary / involuntary and **regrettable** (people you wanted to keep)
- **First-year attrition** — leavers with < 12 months tenure / hires in the cohort (signals hiring or onboarding problems)
- **Retention rate** = employees at start still employed at end / headcount at start
- **Average tenure**, **time to fill**, **time to productivity**, **offer acceptance rate**
- **Span of control** = direct reports per manager (typical healthy range 5-10); number of management layers
- **Engagement** — survey scores, eNPS, participation rate, themes from comments
- **Revenue per employee**
- **Representation** — by level and team, promotion rates by group (aggregate only, groups ≥ 5)

### Approach
1. Clarify the question behind the report (e.g. "why is engineering losing people?")
2. Check data quality (duplicates, missing end dates, inconsistent team names)
3. Calculate with code; show formulas and the period used
4. Compare to the previous period and, if available, to benchmarks
5. Recommend actions; separate facts from hypotheses

### Report format
```
## People report: [type] — [period]
Summary: 2-3 key takeaways
| Metric | Value | Previous | Trend |
Analysis: by team / level / tenure, with charts if useful
Recommendations: …
Method & caveats: formulas, period, exclusions, small-group suppression
```
Flight-risk signals to mention (as hypotheses, never as automated decisions): below-band pay, no promotion for a long time, manager change, low engagement scores in a team, high regrettable attrition in the same team.

## Performance calibration
Before calibration, prepare: rating distribution per team and overall; outliers (all-high or all-low managers); each rating with evidence. In the session, compare people at the same level against the level expectations, not against each other's personalities; watch for recency, halo, similarity and leniency bias; record the reason for every changed rating. Check rating distributions across demographic groups in aggregate afterwards.
