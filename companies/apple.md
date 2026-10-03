---
name: Apple
type: company
status: active
last_updated: 2026-09-15
---

## What It Is

Apple is the consumer-hardware and platform company whose AI strategy ("Apple Intelligence") emphasizes **on-device / privacy-preserving** inference with selective cloud offload. In the wiki's frame Apple matters less as a frontier-model builder than as (a) a **distribution platform** that gates how AI reaches billions of devices and (b) an increasingly active **legal actor** shaping frontier-AI IP norms. This page opens as a stub, created when Apple became a frontier-AI litigant.

## Traction Signals

- **2026-09-14/15: iOS 27 ships a rebuilt Siri, and code shows Siri can be swapped for Claude or ChatGPT** ([[dailybrief-roundup-2026-09-15]], MacRumors + Digg): the rebuilt assistant adds conversational ability, personal-context and onscreen awareness, and app actions (English first, beta on iPhone 15 Pro / 16 and later). The **swappability** is the structural item — third-party LLM optionality inside Apple's default assistant slot, which makes iOS a **distribution surface** for [[anthropic]] and [[openai]] rather than only a competitor. Timeline and execution unclear; sourced from code inspection, not an Apple announcement. *(Not confirmed by Apple; no shipping date for third-party swap.)*
## Traction Signals

- **2026-07-10 — sues [[openai|OpenAI]] over alleged trade-secret theft** ([[apple-openai-trade-secret-lawsuit-2026-07-10]]): Apple's suit reportedly advances a **leadership-directed-misconduct** theory, not a rogue-employee framing — first wiki-captured Apple-vs-OpenAI litigation and a candidate IP-precedent event ("the first real test of whether IP law can even apply to LLM training"). Pairs with [[anthropic-alibaba-claude-extraction-ip-dispute-2026-06-24|Anthropic–Alibaba]] as a second 2026 frontier-AI IP-dispute datapoint. *(Primary not fetched.)*

## Narrows Full Disk Access because of agents (2026-10-02)

**Apple is adding controls around macOS Full Disk Access, warning that *"AI agents have increased the risks of this level of access"*** ([[dailybrief-roundup-2026-10-02]], TechCrunch via Techmeme).

**This is the first platform-owner permission change the wiki holds that is attributed to agents.** Everything else in its security record comes from labs, agent-tooling vendors or researchers; **Apple is changing the boundary rather than instructing the agent.**

**The structural problem it responds to is that the permission predates the actor.** Full Disk Access was designed as a coarse, one-time grant to an application a user chose, installed and could reason about. **An agent running inside that application inherits the whole grant with none of the deliberation** — and agents now routinely run inside terminals and editors that hold it. That is the same shape as the [[loop-engineering|hard-blocks-over-written-rules]] finding: the boundary was never specified against this adversary.

**Worth watching for whether it generalises.** Full Disk Access is one permission; the same argument applies to Accessibility, Screen Recording and automation entitlements, all of which an agent can use to act on a machine. → [[ai-vulnerability-discovery]]

*(Techmeme-linked TechCrunch coverage, not fetched; the actual controls, timeline and whether they are opt-in are uncaptured.)*

## Key People

- *[unsourced in wiki]* — leadership references to be added when a sourced page or event covers them.

## Compared To

- **Frontier labs ([[openai|OpenAI]], [[anthropic|Anthropic]], [[google-deepmind|Google DeepMind]])**: Apple is a platform/distribution and IP actor here rather than a model-capability competitor tracked by benchmark.

## Resources
- [[apple-openai-trade-secret-lawsuit-2026-07-10]] — Apple v. OpenAI trade-secret suit (2026-07-10)
