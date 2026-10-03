---
title: "How to become a forward deployed engineer (53 min masterclass)"
type: source
medium: twitter-thread
url: https://x.com/gregisenberg/status/2105793758616866834
published: 2026-10-01
ingested: 2026-10-03
---

## Summary

[[greg-isenberg|Isenberg]] promoting a 53-minute Startup Ideas Podcast episode with a practising **forward-deployed engineer** who does the work *"all day long for Fortune 500 companies"* (credited to @vasuman). The X post carries **five numbered takeaways**, which is the folded content — **the video itself was not watched and no transcript was obtained.**

His framing for why it exists: *"almost nobody talks about HOW they do it in any detail. It's basically nowhere online."* Also claims *"some forward deployed engineers are getting PAID $1M+/year"* — **unsourced**.

## Key Claims / Takeaways

> **1. They start by listening, not building.** *"They interview the people doing the work and let agents quietly read the company's data for a few weeks. **The real process is almost always 3x longer than the one on paper.**"*

> **2. Four buckets.** *"They sort every step into four buckets: **delete it**, automate it with a simple rule, give it to an AI agent, or keep a human on it. **A surprising amount ends up in the first bucket.**"*

> **3. Build inside the tools the company already uses.** *"Nobody has to learn a new app. When a human needs to sign off, it's just a Slack message."*

> **4. Cheapest model that works.** *"Most of this work doesn't need the most expensive AI."*

> **5. Measure before and after.** *"Then come back 6 months later and prove it worked."*

## Judgment

**Point 2 is a genuine improvement on something the wiki already holds, and the improvement is one word.** Isenberg's own [[gregisenberg-ai-roll-ups-5t-guide-2026-09-26|roll-up automation map]] sorts tasks into *automate now / automate with human review / assist only / keep human* — **four buckets, none of which is "delete it."** The FDE taxonomy puts deletion first and reports that *"a surprising amount"* lands there. **A framework that can conclude the work shouldn't exist is strictly better than one whose cheapest option is still to automate it**, and the roll-up guide — published six days earlier by the same person — cannot reach that answer.

**Point 1 is the most useful operational claim here.** *"The real process is almost always 3x longer than the one on paper"* is the reason the automation map requires 20–50 real work samples rather than a process document, and it gives a number to something the roll-up guide asserted qualitatively. **It also explains the listening period**: weeks of agents reading company data before building is the discovery step that produces the real process. Unmeasured, but falsifiable.

**Point 3 matches an independent convergence the wiki has tracked all year.** *"Build inside the tools the company already uses… when a human needs to sign off, it's just a Slack message"* is [[river|Shopify's River]] (agents in public Slack channels), [[buzz|Block's Buzz]] (a feature branch becomes a channel), and Claude Tag — **three independent systems and now an FDE practice arriving at the same answer: the agent goes where the work already is.**

**Point 4 is corroborated with numbers elsewhere.** *"Most of this work doesn't need the most expensive AI"* is exactly what [[anthropic-automating-eval-design-hillclimbing-2026-09-28|Anthropic's hillclimbing example]] found when it stepped *down* from Opus 4.8 high-effort to Sonnet 5 low-effort and got **88.9% at a fifth of the cost**.

**Point 5 is the one almost nobody does**, and it is the reason this wiki carries so many unmeasured productivity claims. *"Come back 6 months later and prove it worked"* is a commitment the September agentic-coding claims the wiki catalogued ([[developer-productivity-measurement]]) uniformly lack.

**Discount the economics.** *"$1M+/year"* is asserted with no source, sample or role definition, and the post is promotion for his own podcast — *"a full course pretty much on the topic available to you 100% for free"* is marketing copy. **The five points are worth more than the headline number.**

**The practitioner is credited only as a handle.** No name, employer, or verifiable track record; the claims about Fortune 500 practice are secondhand through Isenberg.

## Pages Updated

- [[forward-deployed-engineer]]
- [[ai-native-service-companies]]
- [[greg-isenberg]]
