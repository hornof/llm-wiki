---
title: "Elvis Saravia (@omarsar0) — 'Should you build an agent harness?' + a from-scratch guide"
type: source
medium: twitter-thread
url: https://x.com/omarsar0/status/2099208894866178204
ingested: 2026-09-15
---

## Summary

Two posts from **Elvis Saravia** (@omarsar0, DAIR.AI — Prompt Engineering Guide, DAIR Academy) on 2026-09-12 and 2026-09-14. The first is the **builder-side case for building your own harness**; the second is a concrete from-scratch guide. Together they are the most direct rebuttal the wiki holds to [[levelsio-harness-startups-software-is-dead-2026-09-13|Pieter Levels's absorption argument]] — and notably they were posted **before** it, in response to the same YC-batch observation.

Saravia also answers, head-on, the *"is harness the new word for wrapper?"* question that went unanswered in [[goodhartproof-yc-demo-day-domain-specific-harness-2026-09-11|the original thread]].

## Key Claims / Takeaways

### The case for building one (2026-09-12)

- **The framing**: *"As an AI engineer, learning how to build a harness is one of the best ways to stay ahead and unlock unique value from agents."* Even if you never ship your own, *"you can, at a minimum, transfer that knowledge to tune whatever harness or set of harnesses (closed or open) you use."*
- **Direct answer to the wrapper objection**: *"you are not building a wrapper here; you are building an important part of your intelligence stack. Something you want to control completely."*
- **Against "models will generate harnesses on the fly"**: *"harness engineering isn't something models are great at."* He cites Anthropic's dynamic workflows as the example. The underlying argument: *"We assume too much that tools will remain static, data won't change, or knowledge will not evolve. A custom harness lets you own these issues and solve them at your desired pace."*
- **The reliability gap is domain-shaped, not capability-shaped** — the most load-bearing claim here: *"While general frontier models get better at verifiable (math, code, and the like) tasks, I haven't seen evidence that they solve reliability issues when you apply them to domain-specific and more dynamic environments."* Named verticals already doing it: **bio, health, legal, finance**.
- **Vendor lock-in as the strategic argument**: *"it's not hard to see a world where we leverage a set of frontier models (open and closed) to address issues like cost and diversity of intelligence. Are you going to rely on some company to build that harness solution for you, or, even worse, trust a single model to do that for you?"*
- **Conclusion**: *"Building your own harness is about working towards building your own intelligence stack. I don't think that's optional where things are headed if you really want to have a differentiated business or offering."*
- In the quoted parent post he connects it to the batch observation directly: *"It's not surprising to me that so many YC builders want to build domain-specific harnesses. If you work long enough on a domain-specific problem, you quickly realize the opportunity."* (quote-linking [[garry-tan|Garry Tan]]).

### The from-scratch guide (2026-09-14)

Three modules, deliberately minimal:

1. **An LLM module** for inference, *"ideally support several models"* — he used OpenRouter. System prompt can live here or be separated if you want to explore context engineering.
2. **A tools module** — *"I recommend building them as MCP tools for interoperability"* ([[mcp]]), or plain functions.
3. **An agent loop** encapsulating tools + LLM. *"ReAct is one of the more basic loops you can implement"* — he built his first from the ReAct paper.

Practical notes worth keeping:

- *"try to keep your system prompt minimal and experiment with different models; a mini version of all frontier lab models should be good enough to get you started."*
- **Log everything at three boundaries**: inputs/outputs of the loop, of the LLM, and of tool calls. Then *"set up a simple set of diverse tasks to test your agent loop on. So with every change, you can run the tasks and inspect the results manually."* — a hand-rolled eval harness as step one, consistent with the [[loop-engineering|verifier-first discipline]].
- **Order of extension**: get the three modules working, then add memory, skills, and subagents.
- Resource: the DAIR Academy *harness-engineering* paper collection, which he suggests feeding to an agent as a research task.

## Counter-position in the replies

Kinan Hamwi: *"Building a harness is no trivial matter, I have been building mine over weekends since December 2025 and trust me, it takes a lot of work and effort into every single piece."* His conclusion diverges — *"the need is not for a harness, the current need is an AI controller that can drive models"* — promoting his own local-first control plane. The effort datapoint (nine months of weekends) is the useful part, and it cuts against the "just build one" framing.

## Pages Updated

- [[domain-specific-harness]]
- [[loop-engineering]]

## Notes

- **Elvis Saravia / @omarsar0 — create-candidate, held.** This is his first wiki surface. The two posts are one argument two days apart, so they count as a single cluster rather than two independent surfaces. He is a substantial AI-education voice (DAIR.AI, Prompt Engineering Guide) and is likely to clear the bar soon; **page on the next independent surface.**
- Saravia is promoting his own academy's paper collection. The argument stands on its own; note the interest.
- Timing worth preserving: the bull case (09-12) **predates** the bear case (09-13). They are not responses to each other — both are reactions to the same YC-batch post.
