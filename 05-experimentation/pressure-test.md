# Pressure test: experiment brief (Module 5)

> I ran the builder's pressure-test prompt on my first draft, acting as a senior PM reviewer, and fixed what it found before writing the final brief. All numbers come from my hypothetical metrics snapshot (assumptions, not measurements).

## First draft I tested

- **Hypothesis:** I believe the Pre-Submission Answer Check with a flagged-only security queue for mid-market sales engineers will result in more questionnaires submitted with every high-risk answer confirmed, measured by a +27 pts (58% to 85%) change in % of questionnaires submitted with no "to confirm" answers within 8 weeks. We will protect median questionnaire turnaround (5.2 days).
- **Baseline:** 58% · **MDE:** +27 pts · **Sample:** 20 questionnaires (M3 window) · **Split:** 50 / 50 · **Significance:** p < 0.05
- **Control:** copy the closest previous questionnaire, AI fills gaps, uncertain answers go to security's Slack channel, anything unresolved is marked "to confirm" at the deadline.
- **Variant:** run the check; flagged answers go to a new flagged-only security queue; the summary shows time saved.
- **Held constant:** same SEs, same AI drafting tool, same answer library.

## Review

| # | Question | Finding | Fix |
|---|---|---|---|
| 1 | Exactly one change? | No. The variant bundled three things: the check, a new security queue (a separate Now-lane item) and a "time saved" banner. If the rate improved, I couldn't tell whether the flags or the faster queue did it. | Variant is the check only. "Send to security" posts to the same Slack channel and reviewers as control. Removed the time-saved banner. |
| 2 | Does the metric measure the moment of misery? | Mostly. The misery is not knowing which answers to doubt and running out of time, and "to confirm" is how that shows up. Two gaps: the metric must be read from the file sent to the buyer, not the tool's status, and the "Ready to submit" lock could push SEs to clear answers just to submit. | Defined the metric on the submitted file. Added a blind spot-check guardrail so clearing an answer without checking it shows up. |
| 3 | Primary distinct from guardrail? | Yes: one is answer quality, the other is speed. But "must not increase" isn't a boundary, since any noise would breach it. | Boundary is now +0.5 day over the control arm (about 5.7 days), compared with the concurrent control, not last quarter's 5.2. |
| 4 | Sample size and duration realistic? | No. M3's 20 questionnaires (10 per arm) can't detect even a jump from 58% to 99%. The +27 target needs 43 per arm, about 6.6 months at one company. | MDE set to the M3 "scale" floor of +17 pts (58% to 75%), not the 85% goal. The calculator gives 120 per arm. One company sends about 13 a month, so the pilot pools 8 design-partner companies (hypothetical) over 12 weeks, about 300 questionnaires. Kept p < 0.05. |
| 5 | A rule a stakeholder could hold me to? | Partly. "Must not increase" and "after 8 weeks" were vague, there was no rule for an underpowered result and no Investigate outcome. | Rewrote the rule with numbers, added Investigate (a guardrail breaks or companies disagree) and a rule that fewer than 240 questionnaires at the read date can't trigger a Ship. |

## Not changed

- **Randomizing by questionnaire, not by SE or company.** With 8 companies there aren't enough SEs or companies to split. The same SE works on both arms, so lessons from a flag can carry over to a control questionnaire. That only makes the result smaller (it can't fake a win), and the check never writes back to the library, which limits it.
- **Significance.** p < 0.10 would cut the sample to 95 per arm, but a false Ship means SEs trust a check that misses outdated answers, so I kept 0.05.
