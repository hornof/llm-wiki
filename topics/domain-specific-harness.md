---
name: Domain-Specific Harness
type: topic
last_updated: 2026-09-16
---

## What This Is

The **company-shape** thesis that sits on top of [[loop-engineering]]: if frontier models are converging on general competence and the platform machinery for running agents is becoming rentable, then the durable unit of value is a **harness pointed at one industry's work** — the tools, data, approvals, and definition-of-done for a single painful workflow.

This page tracks the **market layer** of the harness argument: what gets built, what the moat is, and whether it holds. The **practice layer** — how to build loops and harnesses — lives in [[loop-engineering]]; the **unit-economics layer** lives in [[ai-margin-collapse]]; the **quality-bar layer** lives in [[agentic-engineering]].

The position was a create-candidate in the wiki from 2026-08-22 onward ([[nvidia|NVIDIA's]] *"the harness, not the model, is the hero"*) and is paged here on 2026-09-12 after it appeared as the observed shape of a whole YC batch.

## Why It Matters

For the wiki owner this is the shape of most of the companies now worth evaluating as a leadership or co-founder seat. The thesis makes a testable claim about where engineering leverage sits: **not in model work, and increasingly not in agent infrastructure either, but in domain encoding and verification**. If it holds, the scarce skill is knowing what "done" means in a specific business — which is closer to the [[ai-roi-gap|integration-labor]] side of the ledger than to ML.

## Current State

### The batch-level observation (2026-09-11)

jessy (**@goodhartproof**), posting from YC Demo Day: *"Besides hardware/physical things, everyone is just basically just building a domain-specific harness."* Corroborated geographically by a Paris-based reply — *"This is 100% what people are doing right now even around us."* See [[goodhartproof-yc-demo-day-domain-specific-harness-2026-09-11]].

This is an impression of a batch, not a counted tally. Treat as directional.

*Pickup was fast: by 2026-09-12 the observation carried on Digg as "YC Demo Day Spotlights AI Domain-Specific Harnesses" ([[dailybrief-roundup-2026-09-13]]), and by 09-13 [[pieter-levels|Pieter Levels]] had turned it into the bear case below. The phrase is moving faster than the evidence under it.*

### The stated moat — and its instability

Nobody in the cluster claims the harness itself is defensible. The named moats are all **adjacent** to it:

- **jessy**: *"the next wedge is domain RL, data and customer relationships"* — said twice, to two different repliers.
- **@Doublerightvc**: *"the model is becoming the commodity and the harness is the product. The real moat is probably the messy domain context, integrations, and distribution around it."*
- **[[greg-isenberg|Greg Isenberg]]**: *"owning one painful workflow with your own tools, data, approvals, and a clear ROI"* — freight exceptions, insurance reviews, security triage, revenue leakage, healthcare admin, compliance ops.
- **@YGaitsgory**, the sharpest version: *"The moat is knowing which work should stop existing."*

So the thesis is really **harness as the delivery vehicle, domain RL + proprietary data + distribution as the moat**. That is a different and weaker claim than "the harness is the product," and the cluster does not consistently distinguish them.

### Verification as the market-expansion variable

jessy's answer to what actually unlocks a domain: *"the key unlock is increasing the surface area of verifiable things."*

This is the most load-bearing line in the cluster. It restates [[samuel-mcdonald|Samuel McDonald's]] verifier-discipline corrective ([[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|design the verifier, not the prompt]]) as an *addressable-market* statement rather than an engineering practice: a domain becomes harness-able exactly when you can cheaply check whether the work was done right. It predicts the observed ordering — GTM automation early (qualitative, low governance stakes, per @AlexWhitelawCA: *"nobody really sweats the small stuff as they do in finance/acct"*), finance/accounting and clinical work later — and it links the company-shape thesis to [[verifiability-and-jagged-intelligence]].

Whitelaw's third company shape follows from the same logic: **building evaluation datasets to enable RLVR in new domains** (bio, drug development), betting on the math/coding breakout repeating where verification can be manufactured.

### "The AWS moment" — the platform layer gets rented (2026-09-10)

Isenberg's reading of OpenAI's **Agents API** launch: *"everything that made agents hard to build is now something you rent instead of build… If your whole company is an agent platform, the thing you spent the last year building is now included for the price of tokens."* The AWS analogy is explicit — the hard part becomes a line item, and value moves up to whoever knows the job.

Note what OpenAI actually shipped, in its own words: *"Build and run cloud agents with the **Codex harness**, fully managed by OpenAI. We handle orchestration, long-running sessions, and context management."* **The vendor ships the harness as managed substrate.** That cuts both ways for this thesis and is the cleanest available test of it: if "harness" is a durable product category, vendor-managed harnesses should not absorb it; if it is a transitional integration layer, they will.

Isenberg's argument from OpenAI's revealed preference: *"if [software were over], OpenAI wouldn't be shipping infrastructure for other people to build agents on. The general model is theirs, the 10,000+ specific jobs it needs to be pointed at are yours."* See [[gregisenberg-agents-api-aws-moment-vertical-wedge-2026-09-10]].

### Where it sits in Isenberg's category list

His 2026-09-12 *"only businesses left to build"* list puts **domain-specific harnesses** (#5, *"the agent that runs one industry's work"*) and **vertical agents** (#12) as separate items — a distinction he does not defend, and which a replier flagged: *"Item 5 and item 12 are the exact same pitch deck with different valuation multiples."* Recorded as an unresolved category confusion in the thesis, not a settled taxonomy.

### Demand side — the category gets shopped for (2026-09-13)

Two days after the YC-batch post and the same day [[pieter-levels|Levels]] made the bear case, [[sarah-guo|Sarah Guo]] (Conviction) asked simply: *"best multi agent harness outside of the labs?"* ([[saranormous-best-multi-agent-harness-2026-09-13]]).

Worth holding for the framing rather than the answers. The term is used as **settled vocabulary** — no definition, no hedging, investor to professional audience, answered in kind. And the qualifier *"outside of the labs"* **concedes the absorption asymmetry as a premise**: the labs are assumed to have the best ones, and the question is what else exists. That is Levels's argument accepted as a shopping constraint rather than contested.

The answers were AmpCode (named twice), [[cognition]]/Devin, openscout and Herdr — **every one a general-purpose multi-agent coding harness, none domain-specific**. The question did ask about multi-agent harnesses specifically, so this is not a clean test. But it is the one moment in this cluster where someone asked the market to *name* harnesses and nobody named the thing a YC batch is reportedly building.

### A third position — "do it all," not "own one workflow" (Mike Vernal, 2026-09-15)

[[mvernal-barbell-ification-of-software-2026-09-15]] disagrees with **both** sides of this page. Where [[greg-isenberg|Isenberg]] says own *one painful workflow* and [[pieter-levels|Levels]] says the labs absorb it, Vernal argues the winner **owns an entire buying center** — one AI-native system per Sales, Marketing, Finance, HR, IT — and that *"most mid-sized point solutions will likely be consolidated or die off."*

That is a direct challenge to the wedge strategy, not a variation on it. Isenberg's *"freight exceptions, insurance reviews, revenue leakage"* are precisely mid-sized point solutions. Vernal's advice to venture-backed founders is the opposite of a wedge: *"do it all. Just build the whole thing… I fear there is no safety in the middle."*

He agrees with Levels on the mechanism (moats erode as engineering cost falls) and rejects his conclusion (software isn't dead, it barbells). He agrees with Isenberg that something durable remains and disagrees about its shape — **domain knowledge scoped to a workflow, or scale scoped to a buyer.**

**The three positions now on this page are mutually exclusive and all falsifiable**, which is the useful state:

| | Durable unit | Prediction |
|---|---|---|
| Isenberg | one painful workflow, domain-encoded | vertical wedges win |
| Levels | nothing at this layer | labs ship "Claude Medical", harnesses become features |
| Vernal | an entire buying center, won by scale | mid-sized point solutions consolidate or die |

Note that Vernal's and Levels's predictions are **compatible in outcome** — both end with the middle gone — while disagreeing completely about who eats it.

## Open Objections

These are live and mostly unanswered by the proponents. Kept here deliberately.

1. **"Is harness the new term for wrapper?"** (@glass_hamlet; echoed by @nareshrockyn, @pareen asking *"how does one monetise a harness?"*). No proponent in the 2026-09-11 thread answered. The honest distinction available is that a wrapper passes prompts through while a harness owns state, tools, verification and recovery — but that distinction is the *engineering* one, and it does not by itself establish a business moat.
2. **Platform absorption** — **the strongest objection, and it got its full articulation two days after this page was filed.** The original form (@lgrig, 2026-09-10): *"They'll use the agents you create to learn all your flows and tool calling then offer those services directly. The whole thing is basically a training exercise to replace every piece where a human might be involved."* Same shape as the platform-risk caveat in [[saas-disruption-thesis]]. See the dedicated section below.
3. **The term dissolves into "product."** [[alex-lieberman|Alex Lieberman]], 2026-08-24: *"harness engineering won't be a phrase in 12 months — it folds into 'product.'"* ([[businessbarista-harness-engineering-product-2026-08-24]]). The 2026-09 cluster is **not** evidence against this; a term can be everywhere in a YC batch and still be absorbed. Lieberman's clock runs to 2027-08 — worth checking then.
4. **Feedback capture** (@signalgaining): *"these harnesses are training the models."* Unelaborated, but it names the mechanism by which #2 would actually happen.

## The bear case — Pieter Levels, and the mechanism (2026-09-13)

Two days after jessy's post, [[pieter-levels|Pieter Levels]] quote-posted it and drew the opposite conclusion ([[levelsio-harness-startups-software-is-dead-2026-09-13]]):

> *"@ycombinator's batch literally only has harness startups or hardware startups… And it's debatable if anyone will actually need a custom harness or it won't just be generically offered by the AI frontier companies. So software is mostly dead and hardware it is."*

**The mechanism is the part worth keeping.** Levels endorsed a replier's version outright (*"That's it exactly"*) — Henno (@henno_4e):

> *"It's gonna be pretty hard for any harness to outperform a frontier team over time, especially if frontier teams have infinite compute on models that aren't publicly available."*

That is a sharper claim than "big companies copy small ones." The asymmetry named is **unreleased models plus unmetered compute**: a harness company optimizes against a public API while the lab optimizes against the next model, which the harness company cannot see or test. Every integration gap the harness exists to close is a gap the lab can close first, silently, and ship as a default.

The supporting analogy (Chainfire): *"Every new software startup seems to be yet-another-harness, but for domain X. If successful, the big players will just include and kill them next cycle. It's like system tools vs OS maker 15 years ago."* Levels: *"Yes they sound like features not startups. Like ChatGPT for Accountants or Claude Medical."*

### The one claim that decides it

Told that harnesses are simply the new form factor — *"just like software moved from Desktop to SaaS in 2000s"* (Marc Köhlbrugge) — Levels conceded the category and rejected the outcome:

> *"Their models are big enough to do niches well. That's why it's completely different now than before."*

**This is the load-bearing disagreement of the whole thesis, and it is falsifiable.** Every prior platform shift left room for application companies *because the platform could not serve niches economically*. Levels argues frontier models can. If he is right, the domain-specific harness is a feature with a temporary moat. If he is wrong, it is the next application layer. Nothing else in this page settles it, and the evidence below (harnesses carrying real capability) is compatible with both readings — a harness can close a 70-point capability gap and still be absorbed next cycle.

### The builder's rebuttal — Elvis Saravia, and it predates the bear case (2026-09-12)

The strongest answer to the absorption argument was posted **a day before** it, by **Elvis Saravia** (@omarsar0, DAIR.AI), reacting to the same YC-batch observation ([[omarsar0-should-you-build-a-harness-2026-09-12]]). Neither is a reply to the other; both are readings of the same event, which is what makes the pair useful.

**He answers the wrapper objection directly** — the one nobody in [[goodhartproof-yc-demo-day-domain-specific-harness-2026-09-11|the original thread]] engaged:

> *"You are not building a wrapper here; you are building an important part of your intelligence stack. Something you want to control completely."*

**And the "models will just generate them" objection**: *"harness engineering isn't something models are great at… We assume too much that tools will remain static, data won't change, or knowledge will not evolve. A custom harness lets you own these issues and solve them at your desired pace."*

**The load-bearing claim is narrower and better than either of those**, and it is the direct counter to [[pieter-levels|Levels's]] *"their models are big enough to do niches well"*:

> *"While general frontier models get better at verifiable (math, code, and the like) tasks, I haven't seen evidence that they solve reliability issues when you apply them to domain-specific and more dynamic environments."*

That splits the disagreement cleanly. Levels assumes capability gains generalize into niches; Saravia argues **the gains are concentrated in verifiable domains and reliability in messy ones is a separate, unsolved problem**. Both accept that frontier models keep improving. They disagree about *what improves*. Named verticals already building: **bio, health, legal, finance**.

**His strategic argument is vendor lock-in rather than capability** — and it is the one the bear case does not address at all: a multi-model future (open and closed, for cost and "diversity of intelligence") means *"are you going to rely on some company to build that harness solution for you, or, even worse, trust a single model to do that for you?"* A harness you do not control is a dependency on the vendor you are competing with — which is [[levelsio-harness-startups-software-is-dead-2026-09-13|@lgrig's absorption worry]] pointed at the *buyer* instead of the startup.

**The honest weakness**: his answer to "should you build one" is partly *"you should learn to build one"* — which is a much weaker claim, and true regardless of who wins. A reply supplies the cost: nine months of weekends, *"a lot of work and effort into every single piece."* Saravia is also promoting his own academy's paper collection.

### What weakens the bear case

- **Levels has a standing anti-VC prior** and is disposed to reach *"VC-backed software startups are largely dead"* (David Galbraith's escalation in the same thread). He is also the wiki's most-cited proof that solo operators run profitable *software* businesses — which cuts against his own framing.
- **Neither Levels nor Galbraith attended Demo Day.** Both are reacting to one attendee's impression, now repeated louder.
- **His escape hatch leaks**, per Jon Yongfook in-thread: *"even a lot of the hardware is essentially some meat space wrapper around a harness."* If hardware is harness-plus-enclosure, "hardware it is" does not escape the absorption argument.
- **The unresolved bridge** (Cam @camhart73): the benefits still have to reach non-technical users, and whether the mobile gatekeepers permit that is undecided — a distribution question neither side priced.

### What to watch

The test is cheap and specific: **does a frontier lab ship a named vertical offering** — a "Claude Medical" or "ChatGPT for Accountants" — within the next few cycles? Levels predicts yes and treats it as decisive. [[greg-isenberg|Isenberg's]] counter-prediction from the bull side is already on record: *"if that were true, OpenAI wouldn't be shipping infrastructure for other people to build agents on."* Both cannot be right.

## Evidence the harness layer carries real capability

Distinct from the market claim, and better attested:

- **[[nvidia|NVIDIA]], 2026-08-21** — a custom harness (memory + supervisor component) took Opus 5 from **30% → 100%** on ARC-AGI-3 with **no model change**. The strongest harness-as-capability anchor the wiki holds.
- **Spotify "Portal", 2026-09-04** — two-model routing with hard blocks cut Claude Code token spend **~90%** ([[spotify-portal-model-routing-2026-09-04]]). Harness as cost control at firm scale.
- **[[addy-osmani|Addy Osmani]]** — *Agent = Model + Harness*, the ratchet principle, and the most complete single-author harness taxonomy ([[loop-engineering]]).
- **[[croovies-loop-orchestrator-mission-note-2026-09-10]]** — a published mission note running 16 agents per orchestrator with plan-review-before-build and cross-vendor adversarial review, at $500/month.

## Related Concepts

- [[loop-engineering]] — the practice layer; harness/loop vocabulary and the verifier discipline
- [[ai-margin-collapse]] — why the model layer commoditizes in the first place ([[martin-alderson]])
- [[agentic-engineering]] — the quality bar the harness has to hold
- [[saas-disruption-thesis]] — the incumbent-displacement face of the same argument
- [[ai-native-organizations]] — [[alex-lieberman|Lieberman]]/Garry Tan enterprise framing: *systems of record must become AI harnesses or be replaced*
- [[verifiability-and-jagged-intelligence]] — what bounds which domains are harness-able
- [[ai-roi-gap]] — cheap inference, expensive integration
- [[pieter-levels]] — the bear case; [[greg-isenberg]] — the bull case

## Resources

- [[goodhartproof-yc-demo-day-domain-specific-harness-2026-09-11]] — the YC-batch observation, the verifiability line, and the wrapper objection
- [[gregisenberg-agents-api-aws-moment-vertical-wedge-2026-09-10]] — the AWS-moment reading of the Agents API + the 13-category list
- [[croovies-loop-orchestrator-mission-note-2026-09-10]] — a working orchestrator's mission note, published in full
- [[businessbarista-harness-engineering-product-2026-08-24]] — Lieberman's 12-month dissolution prediction
- [[omarsar0-should-you-build-a-harness-2026-09-12]] — the builder's rebuttal: reliability in messy domains is a separate problem from capability; plus a from-scratch build guide
- [[levelsio-harness-startups-software-is-dead-2026-09-13]] — the bear case: absorption by the frontier, and why this cycle may not rhyme with desktop→SaaS
- [[spotify-portal-model-routing-2026-09-04]] — harness-level routing as firm-scale cost control
