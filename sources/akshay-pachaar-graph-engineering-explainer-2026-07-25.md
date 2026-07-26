---
title: "Akshay Pachaar — 'Graph Engineering Clearly Explained'"
type: source
medium: twitter-thread
url: https://x.com/akshay_pachaar/status/2081089131808243999
ingested: 2026-07-26
---

## Summary

[[akshay-pachaar|Akshay Pachaar]]'s long-form X explainer (2026-07-25) separating the substance of **graph engineering** from the meme. Triggered by [[peter-steinberger|Peter Steinberger]]'s 2026-07-18 nine-word question (*"Are we still talking loops or did we shift to graphs yet?"*) and [[hamel-husain|Hamel Husain]]'s same-day article *"Loop Engineering Is Dead. Enter Graph Engineering."* The anchor source for [[graph-engineering]]. *(Primary fetched — full thread text.)*

## Key Claims / Takeaways

- **A graph is three primitives**: **nodes** (units of work — agent / model call / deterministic function / tool / human), **edges** (what runs next: sequential, parallel, or conditional), **state** (a shared typed object flowing along edges; every node reads + writes it).
- **A single loop is a one-node graph with a self-edge.** Graphs don't replace loops — they connect and govern them.
- **The wrapping stack**: prompt → context → harness → loop → **graph**, each layer wrapping the one before. *"Skip a lower layer and the graph just fails in a more elaborate way."*
- **Not new tech**: LangGraph shipped nodes+edges-over-shared-state in **Jan 2024**; AutoGen has GraphFlow; Google ADK 2.0's runtime is built on it. Top reply to Hamel: *"welcome back, langchain."*
- **Four hard problems**: (1) node justification — napkin test, *"if collapsing two nodes loses nothing, they were never two nodes"*; (2) shared-state hygiene — typed schema + write-permissions + checkpoints, idempotent side-effect nodes; (3) trustworthy routing — Google ADK 2.0 rule: deterministic code routes, models only judge; (4) agents agreeing with each other — reviewer node with teeth (different model, fresh context, evidence-anchored), [[cognition|Cognition]]/Devin's "many readers, one writer."
- **Usually overkill**: single agent ~4× chat tokens, multi-agent ~15× (Anthropic figures); but Anthropic's multi-agent research system beat single-Opus by **90.2%** on their research eval where the task fans out naturally.
- **Decision rule**: reach for a graph on genuine specialties / parallel fan-out+join / different models per step / failure isolation+auditable routing — otherwise stay in the loop.

## Why it matters

- **Names the coordination layer above [[loop-engineering]]** — the next rung on the wiki's "center of gravity keeps drifting from the model" ladder ([[trq-dynamic-workflows-harness-2026-06-02|harness]] → loop → graph).
- Honest about the hype-cycle: *"the word may not survive the year; the design question will."*

## Pages Updated
- [[graph-engineering]] (new), [[loop-engineering]], [[akshay-pachaar]], [[peter-steinberger]], [[hamel-husain]] (new)
