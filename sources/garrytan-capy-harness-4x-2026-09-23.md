---
title: "Garry Tan — 4× faster with Capy, and 'a coding harness done right is syntactic sugar'"
type: source
medium: twitter-thread
url: https://x.com/garrytan/status/2102834280980459694
published: 2026-09-23
ingested: 2026-09-25
---

## Summary

[[garry-tan|Garry Tan]] (YC CEO) reports **daily first-person use of Capy** (`@capydotai`) on his own GStack/GBrain pull requests, claiming **at least 4× faster than raw Codex/Claude Code via Conductor** — and then, in a separate post, argues with himself about whether that means anything.

This is the **first named-tool, first-person harness receipt from a principal** the wiki holds. Every other position on [[domain-specific-harness]] is an argument about harnesses; this is someone using one and reporting a multiple.

## Key Claims / Takeaways

### The receipt

> *"I've been using @capydotai daily on all my GStack/GBrain PRs and I'm going **at least 4x faster** than I was when just using raw Codex/Claude Code via Conductor."*

What he attributes it to:

> *"Capy out of box does far far better **parallelization, workflow, and automatic coordination** than almost anything I've seen so far."*

And the outcome shape: *"Bigger fixes, better test coverage, more issues resolved and faster."*

**Note what that list contains.** Not just speed — *better test coverage* and *bigger fixes*. The September agentic-coding claims this wiki has catalogued supply throughput and nothing else ([[developer-productivity-measurement]]); this one gestures at a quality dimension, though without a number.

### The self-skeptical half — the more valuable post

> *"On the one hand you can say a coding harness done right is **syntactic sugar**. On the other hand, I have seen a real speedup in being able to fix issues and land features much faster **with no increase in time in-editor**."*

Two things worth extracting:

**"Syntactic sugar" is the strongest formulation yet of the deflationary case**, and it comes from a harness enthusiast rather than a critic. It is the serious version of *"is harness the new word for wrapper?"* — the question [[goodhartproof-yc-demo-day-domain-specific-harness-2026-09-11|nobody in the original YC thread answered]]. Tan poses it against himself and declines to resolve it.

**"With no increase in time in-editor" is the measurement claim**, and it is the part worth testing. He is asserting the speedup is not paid for with attention — which is precisely what the [[agentic-engineering|six-voice cognitive-load convergence]] disputes (*"we work in five threads to keep the AI busy… more mentally exhausted than I can remember in years"*). **Same question, opposite answer, both first-person.**

## Pages Updated

- [[domain-specific-harness]]
- [[garry-tan]]
- [[agentic-engineering]]

## Notes

- **YC's CEO endorsing a tool by name.** Tan's institutional position makes a public 4× claim about a named product a market event as well as a datapoint; no disclosure of any YC relationship to Capy appears in the thread, and the wiki has not checked for one.
- **"At least 4×" is unmeasured** — no methodology, baseline period, or task set. The comparison baseline (*raw Codex/Claude Code via Conductor*) is at least specific, which is more than most such claims offer.
- **Capy (`capy.ai`) and Conductor have no wiki pages** — create-candidates. Capy on a second independent surface.
