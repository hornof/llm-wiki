---
title: "@0xWast3 on X — a graph is not an execution order, it's a memory of why (7-node assumption-tracking agent graph)"
type: source
medium: twitter-thread
url: https://x.com/0xWast3/status/2091831417432936836
ingested: 2026-08-25
---

## Summary

@0xWast3 relays an "Anthropic ex-engineer's" published agent-graph schema (posted 2026-07-22; clipped 2026-08-24) built on an inversion of the usual framing: **a graph is not an execution order — it's a memory of *why***. Every edge carries the reason it exists, and every step carries the assumption that made it correct, so a broken assumption re-runs only the steps that stood on it (bounded blast radius) rather than forcing the pipeline to redo-all or trust-all. Marketed with a **$6/month** cost claim against a *"$300,000 eval suite"* and a replayed-month receipt. Folds into [[graph-engineering]] as a concrete provenance/assumption-tracking instantiation of the "the agent forgets, the graph does not" thesis. *(Second-hand relay of a third party's schema; the "Anthropic ex-engineer" attribution and the cost figures are self-asserted and unverified; promotional "save this" register.)*

## Key Claims / Takeaways

- **Core reframe**: *"A graph is not an execution order. It's a memory of why."* Six nodes act; one node remembers why they acted. The reason travels with the result — *"Everyone else builds graphs where output moves forward and the reasoning evaporates."*
- **Seven nodes** (each edge carries the reason it exists):
  - **INTENT** — states what the task is for. *Never how.*
  - **DECOMPOSE** — splits into steps, each with a **stated assumption**.
  - **WORKER** — executes one step. Sees nothing else (context-isolation, echoes graph-engineering's "one node, one specialty").
  - **AUDIT** — checks output against the **assumption**, not the goal.
  - **DRIFT** — compares the current step to INTENT and flags divergence (the [[trq-dynamic-workflows-harness-2026-06-02|goal-drift]] failure mode as an explicit node).
  - **LEDGER** — stores every decision with the assumption that justified it (provenance store).
  - **ROOT** — holds the graph; when an assumption breaks, **re-runs every step built on it** (assumption-scoped invalidation).
- **Replayed-month receipt**: 4,100 agent steps over a month; **380 built on an assumption that was wrong by day three**. The old pipeline shipped all 380 and *linked none of them* — no way to find the downstream blast radius. The assumption-graph reruns exactly those 380.
- **Cost claim**: *"$6 a month… catches what a $300,000 eval suite misses. No retrieval layer."* (Unverified; promotional.)
- **Design thesis**: *"A pipeline that forgets its reasons has to redo all of it or trust all of it."* The assumption-per-step is the third option — selective, evidence-anchored re-execution.

## Notable responses

- **@shmidtqq**: *"the most elegant thing i've read about agent design in months"* (unattributed enthusiasm).
- **@0x_fokki**: *"memory matters"* — the one-line restatement.
- (One reply was a Starlink ad injection; ignored.)

## Pages Updated

- [[graph-engineering]] — new subsection: assumption-tracking / "memory of why" as a concrete provenance-graph instantiation of shared-state discipline (checkpoints + idempotency + knowledge-graph-as-memory)
