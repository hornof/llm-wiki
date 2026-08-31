---
title: "Femke Plantinga (Slite) — teardown of 9+ 'company brains': the four functions every one shares (2026-08-27)"
type: source
medium: twitter-thread
url: https://x.com/femke_plantinga/status/2092918452423983363
ingested: 2026-08-31
---

## Summary

Femke Plantinga (Slite) publishes a **comparative teardown of 9+ "company brain" implementations** — the AI-memory/knowledge-substrate systems orgs are suddenly building — and extracts a **shared four-function anatomy**: *getting signals · remembering · dreaming & pruning · speaking & searching*. A rare cross-implementation field-map for the [[company-brain]] concept, spanning open-source personal brains, memory libraries, temporal knowledge graphs, and DIY-markdown-in-git. Promotional (Slite is a vendor; ties to a free ebook drawn from "149 teams"), but the taxonomy and the named systems are the trackable part. *(X thread; vendor-authored; "9+" self-selected sample.)*

## The four functions every company brain shares

1. **Getting signals** — ingestion from tools/email/calendar/docs
2. **Remembering** — storage of facts/decisions/context
3. **Dreaming & pruning** — consolidation *and forgetting* (the neglected one — see the pull-quote below)
4. **Speaking & searching** — retrieval/answering

Maps onto the wiki's existing [[company-brain]] three-layer model (factual memory / context-graph / action-coordination) but **adds "pruning/forgetting" as a first-class function** — the exact gap the page already flags as *"memory-curation problem named and unsolved"* ([[milesdeutscher-claude-personal-cfo-2026-05-14]]).

## The 9 systems

1. **GBrain** — [[garry-tan|Garry Tan]]'s open-source *personal* brain: email + calendar → a **git repo**; a **nightly job re-links everything and flags what's gone stale**.
2. **[[mem0]]** — a memory *library* called from your own code; stores only what you explicitly tell it to; **ranks fresh facts above idle ones** at search time.
3. **Letta** — cross-session *agent* memory (MemGPT lineage); the agent decides what's worth keeping, and a **second agent tidies memory in the background** (the pruning function as a dedicated agent).
4. **Zep / Graphiti** — a **temporal knowledge graph** ("a knowledge graph with a clock in it"): when a fact changes, the old one gets an **end-date instead of being overwritten**, so you can ask *"what was true last March"* — bi-temporal provenance; the [[graph-engineering|knowledge-graph-as-memory]] pattern with time.
5. **Sylph** — a *content* brain living entirely in a **git repo**: agents draft, humans publish, and **the agent reads your edits afterward to learn what it got wrong** (edit-as-feedback / [[loop-engineering|outer-loop]] learning).
6. **DIY (Claude Code + git)** — *"what most engineering teams actually do"*: **markdown in the repo, grep instead of search, pull requests as the only thing keeping it honest.** This is literally the wiki's own [[llm-wiki-pattern]] / [[claude-md-pattern]].
7. **Pletor** — a *brand* brain for marketing: campaigns/assets/performance in one tree; **brand rules only move when a human signs off**.
8. **Gorgias Cortex** — built in-house by an 8-person AI team: **12,000 markdown nodes in GitHub; every night the questions it got wrong become PRs that fix it** — the [[loop-engineering|compound-engineering / self-improving outer loop]] at org scale.
9. **Slite Agent** (the vendor's own) — watches **~20 connected tools** (Slack, Drive, GitHub, Jira…) for **what's gone stale** and sends the diff to whoever owns the page; **nothing changes without human approval**.

## Notable takeaway

- **Pull-quote (comment thread)**: *"everyone builds the remembering part, nobody wants to own the forgetting part"* — Femke: *"so true!"* The **forgetting/pruning function is the neglected one** across implementations, which is exactly the unsolved memory-curation boundary the [[company-brain]] page already names.
- **Convergent patterns**: git-repo-as-substrate (GBrain, Sylph, DIY, Gorgias) + markdown-nodes + **human-approval gates** on writes (Pletor, Slite, Gorgias PRs) + **background pruning agents** (Letta) + **temporal/bi-temporal state** (Zep/Graphiti). The [[garry-tan|Tan]] *"systems of record become harnesses"* and [[ai-native-organizations|AI-native-org]] threads meet the memory-substrate layer here.

## Pages Updated

- [[company-brain]] — "In the Wild" comparative teardown (4-function anatomy + 9-system field-map); the forgetting/pruning function elevated to first-class
