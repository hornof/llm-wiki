---
title: "LLM Routing Can Cost More Than Not Routing"
type: source
medium: twitter-thread
url: https://x.com/akshay_pachaar/status/2096601734072402054
published: 2026-09-06
ingested: 2026-10-07
---

## Summary

**[[akshay-pachaar|Akshay Pachaar]] on why the routing pattern the wiki has treated as settled cost-control can make costs worse** — specifically inside agent loops. **A backfill (published 2026-09-06)** and **sponsored content** for DigitalOcean's Inference Router, which does not make the technical findings wrong but does shape what it concludes.

> *"A classifier reads the request, a cheap model handles the easy ones, and the frontier model handles the rest. That is the version of routing everyone knows, and **it is also the version that breaks in production.**"*

## The Uber receipt, in full

The wiki holds [[uber-ai-tool-cap-1500-2026-06-03|Uber's $1,500/month cap]] as a procurement datapoint. **This is the story behind it:**

- **[[claude-code|Claude Code]] rolled out to ~5,000 engineers in December 2025.**
- **By April 2026 the entire annual AI budget was gone.**
- **Power users at $500–$2,000/month. One executive spent $1,200 in a single two-hour session.**
- *"Nothing broke. Engineers used the tool for exactly the workloads it was built for."*
- The fix was the $1,500 monthly cap, which Pachaar reads as *"throttles productivity to control cost and **treats the symptom**."*

> **"The actual problem is that a docstring lookup and a distributed systems refactor cost the same."**

## The case *for* routing, with citations

- **RouteLLM (ICLR 2025)** — routers trained on Chatbot Arena human-preference data. The **matrix-factorization router hit 95% of GPT-4 Turbo's quality on MT Bench while sending only 14% of queries to the strong model: an 85% cost reduction.** It also **generalized to model pairs it wasn't trained on**, so the technique isn't overfit to one setup.
- **The blended-rate arithmetic**: 70% of requests to a $0.10/M model and 30% to a $3/M model gives **$0.97/M against $3/M**.
- A 2026 arXiv survey on dynamic routing claims a well-designed router *"can outperform even the single best model by using each model's specialized strengths."*

> *"The technique is proven. Teams still hardcode a single model because **the routing layer itself is the hard part.**"*

## Four ways DIY routing breaks

1. **You pay for two inference calls instead of one.** A small LLM in front as classifier adds *"a fixed tax to every request."* Savings survive only if the classifier is much cheaper than the gap between tiers **and** accurate enough that misroutes don't eat the difference.
2. **General models are mediocre at routing.** *"'Fix this' or 'make it faster' carries almost no signal alone. **The intent lives in the conversation history.**"* And: *"coding workloads are where they slip most."*
3. **The routing logic rots.** *"Add a model, rename a task, change a price tier, and you're editing routing code **with no evaluation harness attached**. Nothing signals when a routing change quietly degrades quality. You find out when someone files a bug."*
4. **Model switching destroys your cache.** *"This one is specific to agents, and it's the failure most implementations miss."*

## The cache finding — the core of the piece

- **Cached input tokens bill at roughly 10% of the normal input rate.**
- **A 15-turn coding session: *"around 90% of what you're sending is text the model already processed."***
- **In that loop, model affinity produces 45–80% savings on input tokens. Switching models means zero cache hits and full price every turn.**

**Three things break at once when the router re-decides mid-session:** cost (cache destroyed — *"all 50,000 tokens get recomputed at full input price"*), **behavioural consistency** (*"models differ in output style and tool-calling format, and switching mid-loop breaks the agent's parsing"*), and **coherence** (*"the reasoning thread gets handed to a model that formats its thinking differently"*).

**The fix is session pinning**: route on the first request of a session, then pin every subsequent request to the same model (DigitalOcean exposes it as an `X-Model-Affinity` header).

## A purpose-built router model beats frontier models at routing

- **Arch-Router** (Katanemo): **1.5B parameters fine-tuned for one job** — read a conversation, compare against route descriptions, emit JSON. **It beat Claude 3.7 Sonnet on routing accuracy while running 28× faster.**
- The reasoning: *"routing needs no prose generation, no tool calls, no multi-step reasoning, so the capability surface is small enough that a tiny model covers it completely."*
- **It runs inside the proxy rather than as a second billed API call** — *"the cost shows up as roughly 200ms of added latency, not as a second line on your invoice."*
- **Plano-Orchestrator** (in production) trained on *"ambiguous follow-ups, mid-conversation topic shifts, and messages that shouldn't be routed at all"*; **edges out GPT-5.1 and Claude Sonnet 4.5, with the widest margin on coding.**

**Also worth keeping:** *"Provider latency varies by 2-3x through the day depending on load. **A model that's fastest at 2am is often the slowest at 2pm.**"* Ranking policies offered: cost efficiency, speed (time to first token), manual, or benchmarked-optimal, with metrics refreshed in a background loop and a fallback list per router.

## Judgment

**This complicates the wiki's own best routing receipt and the page should say so.** [[spotify-portal-model-routing-2026-09-04|Spotify's Portal]] is recorded as cutting Claude Code token usage **90%** via two-model routing with hard architectural blocks. **If Portal re-decides per turn inside an agent session, this source says the cache destruction should partly offset that** — so either **Portal pins sessions** (and the 90% is real and the wiki is missing the mechanism that makes it work), or **the 90% is measured on a workload where prefix caching wasn't doing much anyway.** The wiki cannot tell which, and **the Spotify post was never deeply fetched.** That is now a specific, answerable question rather than a general caveat.

**It also resolves a tension the wiki created yesterday — in both directions.** [[simon-willison|Willison's]] *"default hard budget caps"* (2026-10-03) argues caps are the only control that works unattended. Pachaar calls Uber's cap *"treats the symptom."* **Both are right about different things**: a cap is the only thing that holds when nobody is watching, **and** it is a symptom treatment if the underlying defect is that uniform pricing meets non-uniform work. **The cap bounds the damage; routing addresses the cause; neither substitutes for the other.**

**The Arch-Router result is a [[jev|Jev]]-shaped finding from a different vendor, and it is the stronger version.** Jev's claim is that decisions belong to a purpose-built model rather than a frontier one. **A 1.5B router beating Claude 3.7 Sonnet at routing while running 28× faster is that claim, measured, on a named task, against a named comparator.** And it sharpens the economics point folded on 2026-10-04 — *the capability was never about a special model, it was about not generating text*: routing needs no generation at all, which is precisely why 1.5B suffices.

**The cache argument generalises past routing.** *"Cached input tokens bill at roughly 10% of the normal input rate"* and *"~90% of a 15-turn session is already-processed text"* together mean **anything that invalidates a prefix mid-session is expensive** — not only model switching, but context compaction, tool-set changes, and system-prompt edits. **That is a cost dimension [[loop-engineering]] has not been tracking at all**, and it argues against the stage-based clean-window discipline the harness essay recommends. **The two are in genuine tension**: clean windows per stage buy reliability by discarding exactly the cache that makes long sessions cheap.

**Caveats.** **Sponsored content** — the four failure modes all route to one vendor's product as the answer, and the piece's structure is problem-then-sponsor. **The numbers divide cleanly**: RouteLLM and the Uber figures are externally checkable; the Arch-Router and Plano comparisons are the sponsor's own benchmarks of the sponsor's own models, shown as images this ingest did not read. **The 45–80% model-affinity range is unattributed.** Treat the mechanism as sound and the product claims as marketing.

## Pages Updated

- [[ai-margin-collapse]]
- [[loop-engineering]]
- [[kv-cache-optimization]]
- [[jev]]
- [[akshay-pachaar]]
