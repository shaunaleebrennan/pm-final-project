# CPO review of my final presentation (Module 6, optional)

> I attached `final-presentation.html` and ran the builder's "Get a critic's read" prompt, with the reviewer acting as a Chief Product Officer asked to fund this bet. The answer is below, unedited. All data in the presentation is hypothetical.

**(a) Would I fund it?** Not on this deck alone. It's a well-reasoned worksheet, not a funding case: every number is labelled hypothetical, there's no price, deal size or revenue at stake anywhere, and I'd have to read six walls of Q&A to find the bet. The strongest section is the Experimentation Plan. You found that your own 8-week, 20-questionnaire test could never reach significance, rebuilt it around a +17-point floor, 120 questionnaires per arm and a fixed read date, and wrote kill and investigate rules before seeing data. That's the discipline I want. The weakest is the Competitive Analysis & Journey Map: it names no competitor, its evidence is a hypothetical interview note, and the advantage over AI answer tools that already claim a fresh library is asserted, not shown.

**(b) Where is the thinking strongest and weakest?** Strongest in the problem and hypothesis. The data moved you off "drafting is slow" (92% drafted within 2 days) to "verification is the leak" (3.5-day security review, 42% sent with a "to confirm" answer), and you cut the AI drafting features the model over-scored. That's a PM reading evidence, not a backlog. The roadmap and PRD follow cleanly from it, and the prototype found real logic gaps. Weakest in the research: no real customer has said any of this yet, so the whole chain from moment of misery to 58% baseline rests on assumptions. The launch plan is honest about tier and goal, but "6 of 8 design partners sign" means nothing to me without a price.

**(c) The single change.** Replace the hypothetical baseline with one real company's numbers: their actual share of questionnaires sent with "to confirm" answers, their security review time, and one deal that slipped or one answer that was wrong after signing, with its cost. One real data point with a dollar figure turns this from a good exercise into a bet I can rank against the rest of the quarter.

---

## Second read, on my final presentation

> I ran the same "Get a critic's read" prompt again on my final presentation. My summary of its answer, then what I changed.

**(a) Would I fund it?** Two weeks of validation, not a build. Strongest: the Module 5 experiment plan, where the numbers met reality. Weakest: Module 2 names no competitors, so it can't answer "why doesn't Loopio ship this as a checkbox next quarter?". No market size, price or revenue figure.

**(b) Strongest and weakest thinking.** Strongest: "92% drafted in 2 days, but security review takes 3.5" turns an AI-drafting pitch into a verification bet. Weakest: every piece of evidence is hypothetical. Two gaps: Module 4 called the flagged-only security queue essential, but Module 5 removed it from the variant; and the primary metric can rise because of the "Ready to submit" lock, not because answers got more accurate.

**(c) The one change.** Run the check backwards on questionnaires 3 to 5 companies have already sent and report the hit rate: how many signed answers were already outdated, and in which categories. About two weeks, real evidence, a view of value for pricing, and a test of whether the posture register can be built.

### What I changed

| Critique | Change | Where |
|---|---|---|
| No named competitors; "why not Loopio?" | Named Loopio, Responsive, Conveyor and trust centres, and answered the incumbent risk | [journey map](../02-discovery/journey-map.md), [competitive analysis](../02-discovery/competitive-and-journey.md), slide 2 |
| M4 queue vs M5 variant | Said why the queue is left out (the test isolates the check) and that a broken turnaround guardrail triggers testing the queue next | [experimentation plan](../05-experimentation/experimentation-plan.md), slide 4 |
| Metric can rise because of the lock | Accuracy is now a ship condition: the blind spot-check must find fewer outdated answers in the variant than in control | [experimentation plan](../05-experimentation/experimentation-plan.md), [builder export](../05-experimentation/experiment-brief-builder-export.md) |
| Fund validation first | Added Phase 0: a two-week backwards check on 3 to 5 companies' already-sent questionnaires before the pilot | [GTM plan](gtm-and-dashboard.md), slide 5 |

Not changed: market size, price and revenue. I don't have real numbers for them, and Phase 0 is where the first real evidence of value comes from.
