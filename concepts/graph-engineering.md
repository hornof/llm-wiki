---
name: Graph Engineering
type: concept
maturity: emerging
last_updated: 2026-07-26
---

## Definition

**Graph Engineering** is the practitioner-content register that names the **coordination layer across many agent loops** — deciding what runs when, in what order, in parallel or conditionally, and who checks whom. Where [[loop-engineering|Loop Engineering]] designs a single autonomous cycle driving one agent toward a goal, graph engineering is what you reach for *the moment several loops must work together and coordination itself becomes the engineering problem*.

The coinage crystallized in a two-step exchange (July 2026): on **2026-07-18** [[peter-steinberger|Peter Steinberger]] (OpenClaw) posted a nine-word question — *"Are we still talking loops or did we shift to graphs yet?"* — and a few hours later **[[hamel-husain|Hamel Husain]]** published an article titled **"Loop Engineering Is Dead. Enter Graph Engineering."** Both were half-joking about the field's compulsive self-renaming, but the joke landed on something real. The clearest synthesis is [[akshay-pachaar|Akshay Pachaar]]'s **"Graph Engineering Clearly Explained"** ([[akshay-pachaar-graph-engineering-explainer-2026-07-25]]), the anchor for this page.

## Why It Matters

The load-bearing reframe: **a single agent loop is just a one-node graph with an edge pointing back to itself.** Graphs don't replace loops — they *connect and govern* them. This makes graph engineering the top of a wrapping stack the wiki already tracks, each layer containing the one below:

| Layer | Unit of work |
|---|---|
| **Prompt engineering** | the words you send |
| **[[context-engineering]]** | everything the model sees, not just instructions |
| **[[trq-dynamic-workflows-harness-2026-06-02\|Harness engineering]]** | the code around the model (tools, state, errors) |
| **[[loop-engineering]]** | the autonomous cycle driving one agent |
| **Graph engineering** | coordination across many loops |

*"Each layer wraps the one before it… skip a lower layer and the graph just fails in a more elaborate way."* — [[akshay-pachaar-graph-engineering-explainer-2026-07-25]]. This is the same "the harness, not the model, is the expensive part" thesis extended one level up: a graph of weak loops is just *distributed* failure.

## Current State

### The graph itself — three primitives
- **Nodes** — units of work: an agent, a plain model call, a deterministic function, a tool, or a human approving something.
- **Edges** — decide what runs next: in sequence, in parallel, or **conditionally** based on the last node's output (a conditional edge back to an earlier node *is* a loop).
- **State** — a shared, typed object that flows along the edges; every node reads from and writes to it.

The canonical starter graph: `research → write → review`, with a conditional edge sending a failed review back to `write`. Three nodes, four edges, one of which is a loop.

### Not new technology — new name
*"None of this is new."* LangGraph shipped exactly this model (nodes + edges over shared state) in **January 2024**; Microsoft AutoGen has **GraphFlow**; Google's **ADK 2.0** built its entire workflow runtime on the idea. A top reply to Hamel's post: *"welcome back, langchain."* The discipline isn't inventing graphs — it's **knowing when to use one and how to keep it from rotting.**

### The four hard problems
1. **When a node deserves to exist** — a node earns its place only if it's a *real specialty* (different model, different toolset, or a genuinely separate role like a read-only reviewer). Napkin test: *"if you can't draw the graph on a napkin, it's too complex; if collapsing two nodes loses nothing, they were never two nodes."* The common failure is turning "summarize this PDF" into a five-node graph.
2. **Keeping shared state clean** — in a loop the failure mode is context rot; in a graph the same disease moves into shared state (a sloppy write in node 2 becomes confident input for node 5). Fixes are *"simple and boring"*: typed schema, explicit per-field write permissions, checkpoints between nodes. Caveat: replay re-executes post-checkpoint nodes, so any node with **external side effects** (send email, create record) must be **idempotent**.
3. **Routing you can trust** — an edge is a decision; who makes it matters. Model-decided routes buy flexibility *and* instability (same state, different paths, miserable debugging). **Google's ADK 2.0 rule** — *"deterministic code should control predictable routing; models should only handle steps that need actual judgment."* Route with code wherever the condition is checkable.
4. **Agents agreeing with each other** — loop engineering's sharpest rule (*never let an agent grade its own homework*) gets worse at scale: 20 agents on the same base model reading the same flawed context happily agree, and models measurably prefer their own outputs — *"organized nonsense at industrial scale."* Fix: a **reviewer node with teeth** — different model, fresh context (not the full conversation), verdict anchored to evidence the graph can't fabricate (tests that ran, code that compiled). **[[cognition|Cognition]]** landed here after a year running Devin: many agents may *read* in parallel, but **only one agent is ever allowed to write** — reads are safe to parallelize, writes are where the damage happens.

### Where a graph is overkill — "most of the time"
Anthropic's published token costs make it concrete: a single agent burns ~**4×** the tokens of a chat interaction; multi-agent systems ~**15×**; every node multiplies that. The upside is real *when the task genuinely parallelizes* — Anthropic's multi-agent research system beat a single Opus agent by **90.2%** on their internal research eval because research fans out into independent searches naturally. But *Building Effective Agents*' standing advice is unchanged: **find the simplest solution; add complexity only when the task demands it.** Even LangGraph's own guidance: *"if your agent is a straightforward loop with tools, LangGraph is overkill."*

### The decision rule
Reach for a graph when the work **splits into genuine specialties**, needs **parallel fan-out and join**, needs **different models per step**, or needs **failure isolation + auditable routing**. Otherwise stay in the loop. Practitioner corroboration of the parallel-fan-out case: [[greg-isenberg|Greg Isenberg]] argues a single local Claude Code instance *"leaves 10x on the table"* vs. cloud VMs each running an isolated agent in its own worktree ([[graph-engineering-cluster-2026-07-26]]).

## Key Papers / Posts
- [[akshay-pachaar-graph-engineering-explainer-2026-07-25]] — the anchor explainer: 3 primitives, 4 hard problems, decision rule (this page's spine)
- **Hamel Husain — "Loop Engineering Is Dead. Enter Graph Engineering."** (2026-07-18) — the coinage article (referenced via the explainer; primary not fetched)
- **Peter Steinberger** (2026-07-18): *"Are we still talking loops or did we shift to graphs yet?"* — the nine-word prompt that started it
- **LangGraph** (Jan 2024), **AutoGen GraphFlow**, **Google ADK 2.0** — the pre-existing implementations the name retroactively describes

## Related Concepts
- [[loop-engineering]] — the layer directly below; a loop is a one-node self-edged graph, graphs coordinate many loops
- [[context-engineering]] — two layers down; every node call is a context problem
- [[reward-hacking]] — the "agents agree with each other / grade their own homework" failure that reviewer-node discipline exists to prevent
- [[cognition]] — "many readers, one writer" production pattern from running Devin
