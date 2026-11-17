# Feature Roadmap, Module 4 · Security Questionnaire Answer Check

**Team:** 2 engineers + 1 designer

## Strategic anchors
- **Persona:** A sales engineer at a mid-market SaaS company who completes buyer security questionnaires against tight deal deadlines.
- **Primary metric:** % of questionnaires submitted with no "to confirm" answers: from 58% to 85% (+27 points).
- **Moment of misery:** They can't tell which answers a certification, region or policy change has made outdated, and security takes 3 to 4 days to confirm, so answers go out marked "to confirm" (H-05).
- **Guardrail:** Median questionnaire turnaround (now 5.2 days) must not increase.

## Scoring
| Feature | Value | Effort | Quadrant | Decision | Rationale |
|---|---|---|---|---|---|
| S1 Change-Impact Flags | 5 | 2 | Quick Win | Now | The trigger for every flag. Pilot covers only certifications, regions and policies (14% of answers), so effort is small. |
| S2 Pre-Submission Answer Check | 5 | 2 | Quick Win | Now | Directly moves my metric: catches outdated answers before they go out marked "to confirm" (42% today). |
| S3 Flagged-Only Security Queue | 4 | 2 | Quick Win | Now | Security review is the biggest gap (3.5 days vs. a 1-day target). Sending only flagged answers protects turnaround. |
| S4 Source &amp; Date on AI Drafts | 3 | 2 | Fill-In | Later | A source and date don't say whether the answer is still true. Drafting isn't the leak (92% drafted in 2 days). |
| S5 Answer Owner Assignment | 3 | 1 | Fill-In | Next | Only 6% of entries have an owner. Needed to route flags at scale after the pilot, not to prove the check works. |
| S6 Save Security Decisions to Library | 4 | 3 | Major Project | Next | Stops security answering the same questions on 5 deals (T-05), but needs the check and queue live first. |
| S7 AI Auto-Complete Whole Questionnaire | 2 | 5 | Time Sinker | Cut | More AI drafting adds more unsourced answers (H-02). Drafting already works; verifying is the problem. |
| S8 Buyer Portal Auto-Submit | 2 | 5 | Time Sinker | Cut | A different integration per buyer portal, and it makes sending faster without making answers truer. |
| S9 Questionnaire Format Preserver | 2 | 3 | Time Sinker | Cut | Low-severity annoyance (T-07) that doesn't touch answer accuracy or my metric. |
| S10 Trust Centre Sync | 3 | 3 | Time Sinker | Later | Same change event could update the trust centre (T-08), but it's public pages, not questionnaires. After the pilot. |

## Roadmap
### NOW, Pilot (4 weeks, 3 sales teams)
- **S1 Change-Impact Flags**, The trigger for every flag. Pilot covers only certifications, regions and policies (14% of answers), so effort is small.
- **S2 Pre-Submission Answer Check**, Directly moves my metric: catches outdated answers before they go out marked "to confirm" (42% today).
- **S3 Flagged-Only Security Queue**, Security review is the biggest gap (3.5 days vs. a 1-day target). Sending only flagged answers protects turnaround.

### NEXT, Weeks 5-8
- **S5 Answer Owner Assignment**, Only 6% of entries have an owner. Needed to route flags at scale after the pilot, not to prove the check works.
- **S6 Save Security Decisions to Library**, Stops security answering the same questions on 5 deals (T-05), but needs the check and queue live first.

### LATER, backlog
- **S4 Source &amp; Date on AI Drafts**, A source and date don't say whether the answer is still true. Drafting isn't the leak (92% drafted in 2 days).
- **S10 Trust Centre Sync**, Same change event could update the trust centre (T-08), but it's public pages, not questionnaires. After the pilot.

### ✂ Cut List
- **S7 AI Auto-Complete Whole Questionnaire**, More AI drafting adds more unsourced answers (H-02). Drafting already works; verifying is the problem.
- **S8 Buyer Portal Auto-Submit**, A different integration per buyer portal, and it makes sending faster without making answers truer.
- **S9 Questionnaire Format Preserver**, Low-severity annoyance (T-07) that doesn't touch answer accuracy or my metric.
