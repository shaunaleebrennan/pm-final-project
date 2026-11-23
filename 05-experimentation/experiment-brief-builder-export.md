# A/B Experiment Brief, My own initiative (B2B)

## Parameters
| Parameter | Decision |
|---|---|
| Feature under test | the Pre-Submission Answer Check (flags answers a certification, region or policy change has made outdated) |
| Persona | mid-market sales engineers who answer buyer security questionnaires against deal deadlines |
| Expected outcome | sales engineers fixing flagged answers or getting them confirmed by security before the deadline, instead of sending them marked "to confirm" |
| Primary success metric | % of questionnaires submitted with no "to confirm" answers |
| Baseline rate | 58% of questionnaires go out with no "to confirm" answers today (42% have at least one). Hypothetical M3 snapshot: 40 questionnaires in 90 days at one mid-market SaaS company. |
| Guardrail metric | median questionnaire turnaround (5.2 days today) |
| Guardrail boundary | +0.5 day over the control arm (about 5.7 days) |
| Second guardrail | Outdated answers that still get sent: a security reviewer spot-checks 10 random high-risk answers per submitted questionnaire, blind to arm. To ship, the variant's outdated rate must be lower than control's, because the submit lock alone could lift the primary metric. |
| Minimum Detectable Effect | +17 pts (58% to 75%) |
| Sample size per arm | 120 questionnaires per arm (240 in total), from the calculator. One company sends about 13 a month, so the pilot pools 8 design-partner companies of the same size (hypothetical): about 25 questionnaires a week, so about 300 in 12 weeks, which reaches 240 with a buffer for withdrawn deals. |
| Traffic split | 50 / 50 by questionnaire: each new questionnaire is randomly assigned to A or B when it arrives, behind a per-questionnaire feature flag |
| Test duration | 12 weeks |
| Significance threshold | p < 0.05 (95%) |

## Control vs. Variant
- **Control (A):** Today's process. The SE copies answers from the closest previous questionnaire, lets the AI drafting tool fill the gaps, and judges freshness only by the library's last-modified date. Uncertain answers go to security's Slack channel, where the median reply takes 3.5 days. At the deadline, anything unresolved is marked "to confirm" and sent. Per the M3 snapshot (hypothetical): 70% of questionnaires need security, only 30% get every answer back before the due date, 42% go out with at least one "to confirm" answer, and median turnaround is 5.2 days. Nothing tells the SE which answers a change has made outdated (the M2 moment of misery).
- **Variant (B):** Exactly one change: before submitting, the SE runs the Pre-Submission Answer Check (M4 PRD). Screen 1: questionnaire overview with deal name, due date, the drafted answers and a "Run check" button. Screen 2: check results with flagged answers on top; each flag shows the answer, the conflicting control, its current value and its change date, with Fix and Send to security actions. Screen 3: "Ready to submit" summary. Requirements: compares every answer with the posture register (certifications with scope, regions with status, policies with current values, each with a change date) in under 2 seconds; flags 100% of answers that contradict it; answers naming a control not in the register are marked "Unknown, send to security" and can't be cleared by the SE; sent answers show "Waiting on security"; "Ready to submit" stays disabled until every flag is resolved. Send to security posts the flagged answer, with the changed control attached, to the same security Slack channel the control uses. No new queue and no time-saved estimate. In M4 I called the flagged-only queue essential, so leaving it out here is deliberate: this test isolates the check. The check already sends security fewer questions than today, because the SE clears unflagged answers and only flagged ones go to Slack. If turnaround still crosses the +0.5 day boundary, that is my evidence to test the queue (S3) next, not to ship without it.
- **Held constant (isolation check):** Identical in both arms: the same SEs (every SE works on both A and B questionnaires), the same AI drafting tool and answer library (the check never writes back to the library), the same security reviewers, Slack channel and reply process, the same posture register content, the same buyer portals and export format, and the same deal mix and due dates (random assignment). No SE training beyond a 10-minute walkthrough of the check, given to every SE before the test starts. The only thing an SE sees differently is the check on variant questionnaires.

## Hypothesis
> I believe that the Pre-Submission Answer Check (flags answers a certification, region or policy change has made outdated) for mid-market sales engineers who answer buyer security questionnaires against deal deadlines will result in sales engineers fixing flagged answers or getting them confirmed by security before the deadline, instead of sending them marked "to confirm", as measured by a +17 pts (58% to 75%) change in % of questionnaires submitted with no "to confirm" answers within 12 weeks. We will protect median questionnaire turnaround (5.2 days today) throughout the test.

## Shipping criteria
> We will **ship** if % of questionnaires submitted with no "to confirm" answers improves by ≥ +17 pts (58% to 75%) at p < 0.05 (95%) and median questionnaire turnaround (5.2 days today) does not reach +0.5 day over the control arm (about 5.7 days) after 12 weeks.
> We will **iterate** if direction is positive but lift is below the MDE.
> We will **kill** if the primary metric shows no improvement or moves negatively.
> The read date is fixed at the end of 12 weeks, no results reviewed before this date.
