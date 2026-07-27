---
title: "From Loops to Graphs — independent synthesis (Karpathy autoresearch → AgentHub → Anthropic workflows)"
type: source
medium: paper
url:
ingested: 2026-07-27
---

## Summary

An **independent, study-oriented synthesis paper** (PDF, 11pp, dated ~2026-07-24; `_raw/Graph-Engineering-Athropic-Karpathy-Loop.pdf`) that maps a technical progression from a single agent loop to a graph-grounded agent swarm. It explicitly disclaims affiliation with Karpathy, Anthropic, Sequoia, or Bun — a compiled reference, not a vendor or research primary. It is the most rigorous graph-engineering artifact the wiki has captured and the substantive counterpart to [[akshay-pachaar-graph-engineering-explainer-2026-07-25|Akshay Pachaar's explainer]]. *(Primary fetched — full text.)*

## Key Claims / Takeaways

- **Three-step progression**: (1) **vibe coding** — human expresses intent, model writes; (2) **agentic engineering** — human specifies / orchestrates / verifies and stays responsible for quality; (3) **graph engineering** — agents share durable state through typed, queryable graphs of work and knowledge.
- **Karpathy's autoresearch loop** as the atom: an agent inside an executable research harness (`prepare.py` fixed / `train.py` mutable / `program.md` = the natural-language control spec) runs a **ratchet loop** — propose one change → commit → eval ~5 min → keep if metric improves, else `git reset`. *"program.md is programming the program."* ~700 experiments in two days, ~20 retained optimizations; repo ~86K stars.
- **Four conditions that make a loop agent-friendly**: output is verifiable, action is reversible, horizon is short, environment is bounded.
- **AgentHub** (Karpathy's sketch): *"GitHub is for humans, AgentHub is for agents"* — bare Git repo + SQLite + message board; **the commit DAG *is* the graph** (commits = nodes, parent links = edges). Removes convergence abstractions (no main branch, no PRs, no merge queue); the primary op is *"traverse the search graph,"* not *"merge to main."*
- **Anthropic infra as the production vocabulary**: 5 workflow patterns (chaining / routing / parallelization / orchestrator-workers / evaluator-optimizer) → **Dynamic Workflows** (Claude writes a JS orchestration program; up to 16 concurrent / 1,000-cap sub-agents, fresh context each) → **Knowledge Graph Construction Cookbook** (typed entities/relations with provenance).
- **Commit DAG ≠ knowledge graph** (complementary, must not be collapsed): the DAG answers *what changed / which experiment is the parent*; the KG answers *which entities exist / how related / which sources support*.
- **Graph as shared memory**: workers write findings as structured graph updates; a synthesizer traverses to combine them without any worker seeing all documents — *"the agent forgets, the graph does not."* Each worker gets a **task-specific subgraph** (resolve entities → expand 1–2 hops → serialize within a token budget → attach edge IDs for citation), NOT a context dump.
- **Five-plane production architecture**: control / execution / artifact / graph / evaluation — *"prevents one chat transcript from becoming the database, workflow engine, and audit log."*
- **Staged build path**: Day 1 reflective loop → Day 2 tools → Week 1 planning → Week 2 multi-agent (generator+critic; artifact-contract handoffs; worktree isolation) → Month 1 wire into a graph → Month 2 scale to a swarm (define the reducer before fan-out).
- **The thesis**: *"the bottleneck is often not the next model call — it is the placement of memory and evaluation."* The path from loops to graphs is *"from implicit state to explicit state, volatile to durable memory, estimation to evidence."*
- **Honest caveats**: metrics can be gamed (a ratchet optimizes what it can see); dynamic workflows are expensive (1,000-sub-agent runs cost tens of dollars, correlated errors); fragmentation degrades coherent-context tasks; false entity merges are catastrophic; *"do not introduce a graph merely because the system has agents."*

## Pages Updated
- [[graph-engineering]], [[andrej-karpathy]]
