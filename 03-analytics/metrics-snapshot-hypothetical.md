# Metrics snapshot: security questionnaire answers (hypothetical)

> **Hypothetical metrics snapshot.** The course data snapshots cover StreamLine and RouteLogic only, and my own initiative has no product data yet. I wrote these numbers from my own assumptions, consistent with my [Module 2 sample data](../02-discovery/sample-data-hypothetical.md), so I could practise the Module 3 method. They are not measurements. Every number is an assumption to validate with real questionnaire, review-queue and library data. No real people or companies.

Scope: one mid-market SaaS company, last 90 days, 40 buyer security questionnaires (about 250 questions each).

---

## Snapshot 1 of 3 · Questionnaire workflow funnel (last 90 days)

% of questionnaires that reach each stage.

| Stage | % of questionnaires |
|---|---|
| Questionnaire received | 100% |
| First full draft done (library + AI) within 2 days | 92% |
| Uncertain answers sent to security | 70% |
| Every security question answered before the due date | 30% |
| Every high-risk answer checked against a current source | 0% (no answer links to a source) |

| Metric | Current | 6 months ago | Change |
|---|---|---|---|
| High-risk answers per questionnaire (certifications, regions, policies, sub-processors) | 35 (14%) | 33 | ▲ 2 |
| Questions sent to security per questionnaire | 12 | 9 | ▲ 33% |
| Median security reply time | 3.5 days | 1.5 days | ▲ 2 days |
| Questionnaires submitted with 1+ "to confirm" answer (so 58% go out with none) | 42% | 25% | ▲ 17 pts |
| Outdated answers found after submission (buyer or audit) | 3 | 1 | ▲ 2 |
| Library entries with a named owner | 6% | 6% | no change |

| Workflow step | Avg time | Target | Gap |
|---|---|---|---|
| Draft from library + AI | 1.2 days | 1 day | +0.2 days |
| Security review of uncertain answers | 3.5 days | 1 day | +2.5 days |
| Resolve and submit | 0.5 days | 0.5 days | none |
| **End to end (median turnaround)** | **5.2 days** | **2.5 days** | **+2.7 days** |

**Critical signal:** drafting is fast (92% have a full draft within 2 days). The leak is verification: 70% of questionnaires need security, but only 30% get every answer back before the due date.

---

## Snapshot 2 of 3 · Change cohorts: outdated answers after a posture change

Each row is one certification, region or policy change. Cells show the % of affected library answers that still state the old position, weeks after the change. Read → for one change over time; read ↓ to compare changes at the same age.

| Change (affected answers) | Wk 0 | Wk 2 | Wk 4 | Wk 8 | Wk 12 |
|---|---|---|---|---|---|
| Data retention cut from 90 to 30 days (Jan · 18) | 100% | 94% | 89% | 89% | 83% |
| ISO 27001 scope excludes new product (Mar · 11) | 100% | 100% | 91% | 91% | 91% |
| Sub-processor removed (May · 6) | 100% | 100% | 100% | 83% | 83% |
| EU residency still beta, answers say "available" (Jun · 9) | 100% | 100% | 89% | 89% | n/a |

**Critical signal:** a flatline, not a decline. Twelve weeks after a change, 83 to 91% of affected answers still say the old thing. Every correction that did happen came from buyer pushback or an audit, not from the change itself. By the reference card, a flatline is a ceiling: it needs a new capability, not a fix to the current process.

---

## Snapshot 3 of 3 · Segment performance and answer confidence

**By sales-engineer segment**

| Segment | % of questionnaires | Security questions per questionnaire | Submitted with "to confirm" | Post-submission corrections (90 days) |
|---|---|---|---|---|
| Mid-market SE, no proposal team | 55% | 13 | 52% | 2 |
| Enterprise SE with a proposal manager | 30% | 9 | 15% | 1 |
| New-hire SE (under 6 months) | 15% | 16 | 60% | 0 |

**By answer category**

| Category | % of answers | % of security questions | Post-submission corrections |
|---|---|---|---|
| Certifications and scope | 5% | 30% | 2 |
| Data residency and regions | 3% | 20% | 1 |
| Policies (retention, incident response, access) | 4% | 25% | 0 |
| Sub-processors | 2% | 8% | 0 |
| General product and process | 86% | 17% | 0 |

**Answer confidence heatmap** ("How sure are you this answer is still true today?", 5.0 scale)

| Role | General | Certifications | Residency | Policies | Sub-processors |
|---|---|---|---|---|---|
| Sales engineers | 4.2 | 1.8 | 2.1 | 2.4 | 2.6 |
| Proposal managers | 4.0 | 2.5 | 2.6 | 2.7 | 2.9 |
| Security reviewers | 4.4 | 3.9 | 3.6 | 3.2 | 3.0 |

Strong (4.0+) · OK (3.5 to 3.9) · Watch (3.0 to 3.4) · Weak (2.0 to 2.9) · Critical (under 2.0)

| KPI | Current | 12 months ago | Signal |
|---|---|---|---|
| Security team satisfaction with questionnaire process (internal NPS) | −20 | +15 | 35-point drop |
| Security hours per week on questionnaire review | 14 | 6 | 2.3× increase |
| Late-stage deals slipping a quarter waiting on the questionnaire | 1 in 4 | 1 in 10 | Structural shift |

**Critical signal:** high-risk categories are 14% of answers but 83% of security questions and all 3 post-submission corrections. Sales engineers are least confident exactly where the risk sits (certifications, 1.8).
