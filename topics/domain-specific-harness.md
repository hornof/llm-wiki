---
name: Domain-Specific Harness
type: topic
last_updated: 2026-09-12
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

## Open Objections

These are live and mostly unanswered by the proponents. Kept here deliberately.

1. **"Is harness the new term for wrapper?"** (@glass_hamlet; echoed by @nareshrockyn, @pareen asking *"how does one monetise a harness?"*). No proponent in the 2026-09-11 thread answered. The honest distinction available is that a wrapper passes prompts through while a harness owns state, tools, verification and recovery — but that distinction is the *engineering* one, and it does not by itself establish a business moat.
2. **Platform absorption** (@lgrig): *"They'll use the agents you create to learn all your flows and tool calling then offer those services directly. The whole thing is basically a training exercise to replace every piece where a human might be involved."* The structural counter to renting your substrate from the model vendor you compete with — same shape as the platform-risk caveat in [[saas-disruption-thesis]].
3. **The term dissolves into "product."** [[alex-lieberman|Alex Lieberman]], 2026-08-24: *"harness engineering won't be a phrase in 12 months — it folds into 'product.'"* ([[businessbarista-harness-engineering-product-2026-08-24]]). The 2026-09 cluster is **not** evidence against this; a term can be everywhere in a YC batch and still be absorbed. Lieberman's clock runs to 2027-08 — worth checking then.
4. **Feedback capture** (@signalgaining): *"these harnesses are training the models."* Unelaborated, but it names the mechanism by which #2 would actually happen.

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

## Resources

- [[goodhartproof-yc-demo-day-domain-specific-harness-2026-09-11]] — the YC-batch observation, the verifiability line, and the wrapper objection
- [[gregisenberg-agents-api-aws-moment-vertical-wedge-2026-09-10]] — the AWS-moment reading of the Agents API + the 13-category list
- [[croovies-loop-orchestrator-mission-note-2026-09-10]] — a working orchestrator's mission note, published in full
- [[businessbarista-harness-engineering-product-2026-08-24]] — Lieberman's 12-month dissolution prediction
- [[spotify-portal-model-routing-2026-09-04]] — harness-level routing as firm-scale cost control
