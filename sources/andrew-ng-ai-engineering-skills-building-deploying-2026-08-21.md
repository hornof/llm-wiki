---
title: "Andrew Ng — AI Engineering Skills Map: Building & Deploying AI Applications (Skill #1 deep-dive)"
type: source
medium: twitter-thread
url: https://x.com/AndrewYNg/status/2090840747738374568
ingested: 2026-08-24
---

## Summary

[[andrew-ng|Andrew Ng]] publishes the first **per-skill deep-dive** promised in the [[andrew-ng-ai-engineering-skills-map-2026-08-14|AI Engineering Skills Map]] (2026-08-14): a breakdown of **Skill #1, "Building & Deploying AI Applications"** into six sub-skills. The framing that ties them together: *"the key difference between AI applications and non-AI software is that the former's output is less predictable"* — so building AI systems is **iterative, not plannable up front**; you *"repeatedly build, examine, and decide what to try next… create reliable software systems based on unreliable AI components."* Anchors/expands [[ai-engineering-skills]]. SWE-fundamentals deep-dive (Skill #2) promised next. *(Primary fetched.)*

## Key Claims / Takeaways — the six sub-skills of "Building & Deploying"

1. **LLM foundations** — tokenization + generation mechanics → *when to trust vs. when they fail*; multimodal choice; context-window tradeoffs; cache hits, knowledge cutoff, reasoning-effort level, sampling params, tool-calling; when to fine-tune or self-host.
2. **Grounding models with data** — beyond early RAG/vector-search: choose prompt-vs-tool-retrieval, and the right representation (**vector index / knowledge graph / semantic layer over structured data**); turn text/PDF/HTML/images into LLM-ready inputs; pipelines to keep data clean + fresh.
3. **Building agentic systems** — pick the architecture (predefined workflow ↔ open agent harness); chain vs parallelize, code vs LLM; design the agent loop (tools incl. **MCP/CLI/sandbox**, memory architecture, long-session context management, single- vs **multi-agent**); harden to production (**guardrails, adversarial inputs, data-exfiltration risk, governance**); plus frontier techniques (voice agents, computer-use, generative UI).
4. **Evaluation-driven development** — *"the most important trait that distinguishes someone great at building AI systems is whether you can drive a disciplined evals/error-analysis loop."* Building good evals is a deep technical skill: read traces, EDA + product insight to decide what to measure; know when to use **deterministic evals vs LLM-as-judge vs human-in-loop**, and **evaluate your evals**. Makes progress *systematic rather than random.*
5. **Operating in production** — AI ops differs by *unpredictability, cost, latency*: observability on real usage, drift detection, fast response to failures + **prompt-injection** security incidents; **statistical** regression testing + CI/CD calibrated to mistake-risk; cost/latency optimization (model choice, distillation, fine-tuning, workflow simplification) at scale.
6. **Machine learning foundations** — *"every engineer I know that's good at building with LLMs also understands ML/DL at some depth."* Model tradeoffs (accuracy/train-speed/inference-speed), data engineering for training/eval, and the core mental frameworks — **bias/variance, error analysis, engineering your data** — for navigating uncertain-output systems.

## Why it matters

- **The wiki's ramp-up curriculum, one level deeper**: the 08-14 map gave the 4 skills; this operationalizes Skill #1 into a concrete study list. Owner-relevant (hands-on re-entry).
- **1:1 convergence with wiki threads continues**: evals/error-analysis ([[loop-engineering]]), grounding/context ([[context-engineering]], [[rag]], [[graph-engineering]]), agentic architecture ([[agentic-engineering]], [[graph-engineering]]), prod security ([[ai-vulnerability-discovery]], [[reward-hacking]]), data quality ([[training-data-quality]]).

## Pages Updated
- [[ai-engineering-skills]], [[andrew-ng]]
