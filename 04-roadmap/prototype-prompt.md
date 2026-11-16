Build a working prototype based on this PRD. Use the User Story as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity.

# Pre-Submission Answer Check, Simplified PRD (My own initiative)

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** Sales engineer at a mid-market SaaS company, answering buyer security questionnaires against deal deadlines

## 1. The Big Picture
- **Vision:** Every security questionnaire goes out with answers that are still true today, and security only sees the answers that changed.
- **Press release:** Today, sales engineers can check a drafted security questionnaire before they send it. The Pre-Submission Answer Check compares every answer with the company's current certifications, data regions and policies, and flags the ones a change has made outdated, like an EU residency answer that says "available" while the region is still in beta.

Instead of posting 12 questions in Slack and waiting four days, the sales engineer fixes what they can and sends security only the flagged answers, with the change attached. The questionnaire goes out on time, with no "to confirm" answers and nothing signed that stopped being true last quarter.
- **Success metric:** % of questionnaires submitted with no "to confirm" answers: 58% → 85%
- **Guardrail:** Median questionnaire turnaround stays at or below 5.2 days

## 2. The Details
### User stories
- As a sales engineer, I want to see which answers a certification, region or policy change has made outdated, so that I fix them before the questionnaire goes out.
- As a sales engineer, I want to send security only the flagged answers with the change attached, so that I get a decision before my deadline instead of marking answers "to confirm".
- As a security reviewer, I want to receive only the answers a change affects, so that I stop re-answering the same questions on every deal.
### Screens to build
- 1. Entry: questionnaire overview with deal name, due date, the 12 drafted answers and a "Run check" button
- 2. Core: check results with flagged answers on top; each flag shows the answer, the conflicting control, its current value and change date, and Fix / Send to security actions
- 3. Confirmation: "Ready to submit" summary showing all answers clear, what was fixed, what security confirmed, and the time saved
### Functional requirements
- The system must compare all 12 answers with the posture register in under 2 seconds.
- The system must flag 100% of answers that contradict a register entry (scope, region status or policy value).
- Each flag must show the answer text, the conflicting control, its current value and its last-changed date.
- The sales engineer must be able to fix a flagged answer inline or send it to security.
- Answers sent to security must show as "Waiting on security" until a decision is entered.
- The "Ready to submit" button must stay disabled while any flag is unresolved.
- Unflagged answers must be clearable in one click.
### Smart behaviors (Situation → Outcome)
- If an answer names a certification and a product outside that certificate's scope → flag it as "Out of scope"
- If an answer says a data region is available and the register says beta → flag it as "Region not live"
- If an answer states a policy value (e.g. retention days) that differs from the register → flag it and show the current value
- If an answer mentions a control that isn't in the register → mark it "Unknown, send to security", never clear
- If every flag is resolved → enable "Ready to submit" and show the summary
### Technical constraints
- Single-page React app, useState only
- No backend, database, login or external API calls
- Hard-coded sample: 1 questionnaire (12 answers) and a posture register (6 controls)
- Rule-based keyword matching, no LLM calls
- Security decision is simulated with a button

## 3. The Logistics
### Features out
- AI drafting of answers
- Buyer portal or Slack integrations
- Saving decisions back to the library
- Answer owner management
- Login, roles and history
### Edge cases & safety guard
- No answers loaded → show an empty state with "Load sample questionnaire"
- No flags found → show "All answers clear" and go straight to the summary
- Answer mentions an unknown control → mark "Unknown, send to security"
- Safety: never change an answer's text without the sales engineer's action
- Safety: never mark an answer clear if it mentions a control that changed
### Decision log
- Kept the check rule-based instead of AI so every flag points to a real register entry and can't be invented.
- Moved saving security decisions back to the library (S6) to Next, so the pilot only proves the check and the queue.
### Evals
- Accuracy: flags 5 of 5 seeded outdated answers, with 0 outdated answers cleared
- Time-on-task: check and resolve the 12-answer sample in under 10 minutes
- Safety: 0 questionnaires reach "Ready to submit" with an unresolved flag

## MoSCoW scope
- **Must:** Load a drafted questionnaire (sample of 12 answers); Current posture register: certifications with scope, data regions with status, policies with current values, each with a last-changed date; Flag any answer that contradicts the register (wrong scope, region not live, old policy value); Show each flag with the answer, the control it conflicts with, the current value and the change date; Resolve each flag: fix the answer or send it to security; Block "Ready to submit" until every flag is resolved
- **Should:** Send all flagged answers to security in one batch, ordered by due date; Clear all unflagged answers in one click; Summary bar: X of Y answers clear
- **Could:** Suggested replacement wording for a flagged answer; Export the checked questionnaire; Answers that mention a control not in the register get their own "unknown" tab
- **Won't (now):** AI drafting of answers; Buyer portal or Slack integrations; Saving security decisions back to the library; Answer owner management; Login, roles and history

