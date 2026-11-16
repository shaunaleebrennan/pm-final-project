# AI Synthesis, Product Health & Insights Summary (Module 2)

## Responses
- **Moment of misery / red flag #1 (e.g., “user gave up after 3 tries”):** Under a Friday deadline, the sales engineer sends answers security hasn't confirmed, marks two "to confirm", and never goes back to them (H-05, T-02). The unchecked answer becomes contract text.
- **Moment of misery / red flag #2:** The GRC lead updates the data retention policy but has no way to find the questionnaire answers that still state the old number (H-06, T-03). The change and the answers that depend on it aren't connected.
- **Moment of misery / red flag #3:** Red flag: a signed contract claimed ISO 27001 covered a product that was out of scope, and it was found in a customer audit, not before submission (T-01, H-08).
- **Product Health & Insights Summary (Claude's output):** Product Health & Insights Summary
Security questionnaire response workflow (assumed sample data)
Executive Summary
Product health is strong on speed and weak on trust. The answer library and AI drafting let sales engineers close questionnaires quickly, but the answers that carry the most risk are not labelled as such. A single unverified certification claim has already damaged a customer relationship, which shows that one stale answer can outweigh an otherwise accurate library, and ownership gaps and a slow review queue make that exposure harder to contain.
Thematic Synthesis
1. Answer Accuracy and Trust
Most answers are reliable, but a small set tied to certifications, regions and policies looks identical to the rest, so no one can tell which ones need checking before submission. Errors have surfaced late, in a customer audit or a signed contract rather than in review. AI-drafted answers add a further gap because they show no source document or date.

* Certification scope stated in a signed contract excluded the product sold, and was found in a customer audit rather than before submission: Critical
* EU data residency was described as available in recent questionnaires while the option was still in beta: High
* High-risk answers are visually indistinguishable from low-risk ones: High
* AI-drafted answers carry no citation to their source or its date, so sales engineers cannot judge how old the content is: Medium

2. Answer Library Governance
The library holds over a thousand entries, but none has a named owner, and entries are not linked to the policy, certificate or region they depend on. Staff rely on the last-modified date, which says nothing about whether the content is still true. When a policy changes, there is no way to find the answers that still state the old position.

* No owner and no dependency links on library entries: High
* Policy changes, such as a revised data retention period, cannot be traced to the questionnaire answers that quote the old value: High

3. Review Workflow and Turnaround
Security reviews run through Slack with no queue, priority or due-date logic, so a request takes three to four days regardless of deal stage. The same questions recur across concurrent deals and are answered from scratch each time, and those answers never return to the library. When review runs late, sales submits partial responses with unresolved items, and deals slip at the stage after legal review.

* Review requests take three to four days, with no prioritisation by deal stage or due date: High
* Deals slip by a quarter while waiting on security after legal review: High
* Answers marked "to confirm" are submitted at the deadline and not revisited: High
* The same dozen questions recur across five concurrent deals, and Slack answers are not saved back to the library: Medium

4. Answer Reuse and Discoverability
Sales engineers start from the nearest previous questionnaire and paste from it. This is fast, but it carries forward whatever that answer said at the time. New hires cannot tell which answers they are permitted to change, so they change none, which leaves the ownership gap unresolved at the point of use.

* Copying from the closest prior questionnaire carries forward outdated wording: Medium
* No clear guidance on which answers may be edited, so new staff avoid editing any: Medium

Minor Technical Debt: Questionnaire formats vary across spreadsheets, portals and PDFs, which breaks copy-paste formatting (Low). The public trust centre still lists a sub-processor removed last quarter (Low).
Scope note: every input here is an assumption you wrote for practice, not research. Treat the themes and severities as hypotheses to validate against real interviews and ticket data.
- **Did the AI catch the specific moment of misery / pain point you found in Step 1?:** Yes, all three. It rated the signed-contract certification error Critical, said the policy change couldn't be traced to the answers quoting the old value, and listed "to confirm" answers that were sent and never revisited.
- **Did it smooth over a critical frustration into a generic bullet point?:** Yes. The "to confirm" moment became the third bullet under Review Workflow and Turnaround, so it reads like a delay. It is the moment an unchecked answer becomes contract text, which makes it an accuracy risk, not a speed problem.
- **Did the AI try to suggest features or a roadmap despite the constraints?:** No. It kept to diagnosis and added a scope note reminding me the data is assumed. Some bullets point at an obvious fix ("no prioritisation by deal stage"), but they restate the tickets rather than recommend anything.
- **Logic leak / hallucination #1 (e.g., “AI suggested a new search bar feature, roadmap leak”):** The Executive Summary says the certification error "damaged a customer relationship". The data only says it was found in a customer audit and caused "a bad week" internally. The consequence for the customer was invented.
- **Logic leak / hallucination #2:** "Product health is strong on speed" contradicts the data: the questionnaire is "the slowest step" after legal (H-07) and security reviews take 3 to 4 days (T-02). Only drafting is fast; the end-to-end workflow is slow.
