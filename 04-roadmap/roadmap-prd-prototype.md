# Roadmap, PRD & Prototype (Module 4)

## Your strategic anchors
- **Persona (M2), who are you solving for?:** A sales engineer at a mid-market SaaS company who completes buyer security questionnaires against tight deal deadlines.
- **Primary success metric (M3), your leading indicator:** % of questionnaires submitted with no "to confirm" answers: from 58% to 85% (+27 points).
- **Moment of misery (M2), the specific friction blocking the goal:** They can't tell which answers a certification, region or policy change has made outdated, and security takes 3 to 4 days to confirm, so answers go out marked "to confirm" (H-05).
- **Guardrail metric (M3), what must not drop or break:** Median questionnaire turnaround (now 5.2 days) must not increase.

## Scan the backlog & set a human baseline
- **My instinctive “quick wins” before touching the AI (2 to 3 feature IDs + why):** S2 Pre-Submission Answer Check and S1 Change-Impact Flags. Together they attack my moment of misery head on: an SE can see which answers a change made outdated before the questionnaire goes out. I also marked S4 Source & Date on AI Drafts, because it looked cheap and AI-related.

## Audit, override & decide
- **Where did you override the AI? (feature + old vs. new score + why):** S1 Change-Impact Flags: effort 3 → 2. The AI sized it as matching all 1,000+ library answers, but my M3 risk mix shows certifications, regions and policies are only 14% of answers, so the pilot only maps that set. That moves it from Major Project to Quick Win. S3 Flagged-Only Security Queue: value 3 → 4. Security review is the biggest gap in my workflow data (3.5 days vs. a 1-day target), and it's where the guardrail breaks. S4 Source & Date on AI Drafts: value 4 → 3, Quick Win → Fill-In (see below). S7 AI Auto-Complete: value 4 → 2, effort 4 → 5.
- **Did the AI over-value a Sales/Eng request your M2 interviews don’t support?:** Yes. It scored S7 AI Auto-Complete Whole Questionnaire, a Sales request, as a value-4 Major Project because it "speeds up drafting". My M2 notes say the opposite: drafting isn't the pain (H-01, H-02), and my snapshot has 92% of questionnaires fully drafted within 2 days. More AI drafting means more answers nobody can trace to a source. It also gave S4 a 4 for the same "AI" reason. Showing a source and date doesn't tell you the source is still true.
- **Did it underweight something your M3 cohort/funnel data strongly supports?:** Yes, S3 Flagged-Only Security Queue. The AI saw it as workflow plumbing (value 3). My M3 funnel shows 70% of questionnaires need security but only 30% get every answer back before the due date, and security review takes 3.5 days. Without a short, prioritised queue the flags just create more Slack questions and turnaround (my guardrail) gets worse.

## Generate your interactive roadmap
- **My “Now” lane (this sprint), the 2 to 3 quick wins I’ll build first:** S2 Pre-Submission Answer Check, S1 Change-Impact Flags and S3 Flagged-Only Security Queue. Built together, they cover the whole verify step: a change flags the answers it affects, the check catches them in this questionnaire, and only those go to security.
- **What I cut, and the “no” I’m protecting the scope from:** S7 AI Auto-Complete, S8 Buyer Portal Auto-Submit and S9 Format Preserver. The "no" I'm protecting is "just make it faster to send". This pilot is about whether answers are still true, not about drafting or sending speed, so anything that adds AI answers or new integrations is out.
- **Prototype/roadmap screenshot link (paste into your deliverables):** [Interactive roadmap screenshot](roadmap-screenshot.png) · [interactive roadmap (HTML)](interactive-roadmap.html)
