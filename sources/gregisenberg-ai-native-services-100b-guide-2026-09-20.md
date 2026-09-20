---
title: "Greg Isenberg — AI-native services: a $100B opportunity"
type: source
medium: article
url: https://x.com/gregisenberg/status/2101760050108797268
ingested: 2026-09-20
---

## Summary

[[greg-isenberg|Greg Isenberg]]'s long-form guide to **AI-native services** — sell the finished work rather than the tool, with agents doing most of the delivery. The most complete operational treatment the wiki holds of [[ai-native-service-companies]], and Isenberg's own fuller answer to the question his [[gregisenberg-agents-api-aws-moment-vertical-wedge-2026-09-10|"only businesses left to build"]] list opened.

It also supplies something neither [[pieter-levels|Levels]] nor [[mvernal-barbell-ification-of-software-2026-09-15|Vernal]] offered in the [[domain-specific-harness]] argument: **a path**, not just a position — service → productized service → software, with revenue at every rung.

## Key Claims / Takeaways

### The economic premise

> *"A business pays about $10,000 a year for QuickBooks. It pays about $120,000 a year for the accountant who uses QuickBooks. For twenty years, software companies fought over the $10,000, because that was the part you could sell at scale."*

US businesses spend roughly **$4.6T/year on services, about 6× what they spend on software**. That pool was previously unaddressable because every dollar was attached to a person. *"The customer doesn't want bookkeeping software. They want their books closed."*

### Why now

Three things landing together: models crossed from *"a rough draft a person had to redo"* to *"a finished draft a person checks"*; per-task cost fell from dollars to cents, making **marginal cost of delivery near zero**; and the budget already existed.

### Named receipts

- **Harvey** — roughly **$100M → $190M ARR in about five months**
- **EvenUp** — demand letters at **~$500 each** for work that consumed 8-12 associate hours; **crossed $50M revenue**
- **Kick** — SMB bookkeeping at **$300-500/month**, undercutting a human bookkeeper by half, at **>70% gross margins**

### Why a service beats SaaS, an app, or an agency

The sharpest line, and the one that connects to [[ai-margin-collapse]]:

> *"SaaS is running up a down escalator. You sell a tool, and the tool competes with a foundation model that gets better and cheaper every quarter. Every time a lab ships, your product is worth a little less."*

Against which: *"You sell the finished work, so when the models get better, your business gets better. Model improvement works for you instead of against you."* Apps pay 30% to Apple; agencies sell hours and stay stuck at 20-30% margins.

### The eight pieces

1. **The unit** — one clearly defined deliverable (per claim, per filing, per month of books). *"Never per hour."* Needs a clear finish line.
2. **The intake** — a form, not a scoping call. *"If you can't define intake as a form, your unit isn't clear enough yet."*
3. **The engine** — model + instructions + examples + industry context.
4. **The rulebook** — *"the real product, and almost everyone underrates it."* See below.
5. **The review layer** — per-unit decision on what ships automatically vs what a human checks. *"The review layer is how you own the mistakes without drowning in them, and the rulebook shrinks it over time."*
6. **The delivery** — a dashboard or portal. *"This replaces the account manager."*
7. **The pricing** — per unit or flat retainer, never hourly. **Price against the human alternative, not your costs**: *"If a firm charges $2,500 for the thing, you charge $800."*
8. **The distribution** — cold outbound to the exact check-signer, plus **do the first job free**.

### The rulebook — the part that matters most here

> *"It's the written list of what 'correct' means in your niche and every way the AI gets it wrong… You build this list one mistake at a time, by reading outputs and writing down what you caught. After a few hundred jobs, this rulebook is the thing that makes your output trustworthy and your business defensible."*

This is **compound-engineering accretion pointed at a market rather than a codebase** — the same primitive as [[claude-md-pattern|CLAUDE.md]] rules accruing from failures, and the same verifier discipline [[loop-engineering]] tracks, sold as the moat.

### The 2×2 that decides the business

Two questions: **does the customer already pay an outside firm for this?** and **is there a checkable right answer?**

| | Checkable | Judgment-heavy |
|---|---|---|
| **Already outsourced** | **build here** — budget exists, scope defined, switching cost zero, and you can prove the work | human in the loop, charge a premium near the old firm's price |
| **Done in-house** | real opportunity, harder sell — position as a tool the team keeps | *"skip it. Because that's a job, not a business."* |

The second axis is [[goodhartproof-yc-demo-day-domain-specific-harness-2026-09-11|jessy's *"surface area of verifiable things"*]] restated as a market-entry filter rather than a capability claim — arrived at independently, nine days later.

### The five-step build, and the wedge

Pick a box → **do the work by hand for five customers** → **write down every mistake** → productize (fix scope and price, intake becomes a form, delivery a dashboard) → *only if you want to*, turn it into software.

> *"You climb from service to product with a business paying you at every rung, instead of raising money to guess."*

He names the enterprise version explicitly: *"The forward-deployed engineer model… is a service used as the wedge into an enterprise. It's how the winners get in the door."* → [[forward-deployed-engineer]]

### Worked example, with numbers

Home-health visit-note review: a mid-size agency produces ~2,000 notes/month and pays a nurse reviewer ~$70K/year. Unit = one reviewed note at **$2**. That is **$4,000/month per agency**; ten agencies $40K/month; **fifty ≈ $2.4M/year run by one person**, at a few cents of model cost per note.

### The defensibility argument

*"Why won't the customer just do this themselves with ChatGPT? The answer is that they don't want a tool, they want it done, and they want someone on the hook when it's wrong."* The moat is **owning the mistakes** — which is also why the review layer exists.

And the failure mode: *"Most people building 'AI agencies' point the AI at production and leave everything else the way it was. That gives you a slightly cheaper agency."* The overhead — scoping, account management, QA — is what made agencies bad businesses, and collapsing it is the whole move.

## Pages Updated

- [[ai-native-service-companies]]
- [[domain-specific-harness]]
- [[greg-isenberg]]
- [[forward-deployed-engineer]]
- [[saas-disruption-thesis]]

## Notes

- **Isenberg is promoting throughout** — ideabrowser.com for the opportunity list, his own podcast episode, his newsletter. The framework is independently usable; the urgency is sales.
- **The three company receipts (Harvey, EvenUp, Kick) are asserted, not sourced.** Revenue figures, margins and growth rates carry no citation and were not verified here. The **$100B** headline is a guess he does not derive.
- **$4.6T US services spend** is presented without a source.
- The opportunity list is a *hypothesis list*, not evidence — none of the nine named niches is backed by a working example in the piece.
