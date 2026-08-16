---
name: Graph Engineering
type: concept
maturity: emerging
last_updated: 2026-07-31
---

## Definition

**Graph Engineering** is the practitioner-content register that names the **coordination layer across many agent loops** — deciding what runs when, in what order, in parallel or conditionally, and who checks whom. Where [[loop-engineering|Loop Engineering]] designs a single autonomous cycle driving one agent toward a goal, graph engineering is what you reach for *the moment several loops must work together and coordination itself becomes the engineering problem*.

The coinage crystallized in a two-step exchange (July 2026): on **2026-07-18** [[peter-steinberger|Peter Steinberger]] (OpenClaw) posted a nine-word question — *"Are we still talking loops or did we shift to graphs yet?"* — and a few hours later **[[hamel-husain|Hamel Husain]]** published an article titled **"Loop Engineering Is Dead. Enter Graph Engineering."** Both were half-joking about the field's compulsive self-renaming, but the joke landed on something real. The clearest synthesis is [[akshay-pachaar|Akshay Pachaar]]'s **"Graph Engineering Clearly Explained"** ([[akshay-pachaar-graph-engineering-explainer-2026-07-25]]), the anchor for this page.

## Why It Matters

The load-bearing reframe: **a single agent loop is just a one-node graph with an edge pointing back to itself.** Graphs don't replace loops — they *connect and govern* them. This makes graph engineering the top of a wrapping stack the wiki already tracks, each layer containing the one below:

| Layer | What it is | Unit of work |
|---|---|---|
| **Prompt engineering** | the message | **one input** |
| **[[context-engineering]]** | the memory (curation across steps) | **what stays in the window** |
| **[[trq-dynamic-workflows-harness-2026-06-02\|Harness engineering]]** | the machine (gather → run → tools/sub-agents → verify) | **one pass through the machine** |
| **[[loop-engineering]]** | the run (decide whether to run the pass again) | **the whole run** |
| **Graph engineering** | the coordination (which loops run at all) | **the whole job** |

*"Each layer wraps the one before it… skip a lower layer and the graph just fails in a more elaborate way."* — [[akshay-pachaar-graph-engineering-explainer-2026-07-25]]. This is the same "the harness, not the model, is the expensive part" thesis extended one level up: a graph of weak loops is just *distributed* failure.

The crisp **"unit of work" per layer** framing above comes from **Avi Chawla** ([[raw-batch-roundup-2026-07-30-pt2]], a 2nd independent voice restating Pachaar's ladder): *"prompt and context both live inside the harness gather step. The harness is one pass, the loop decides whether to run that pass again, and the graph decides which loops run at all."* Corroborates the wrapping-stack model from a distinct practitioner. A **3rd voice** ([[beamnxw-harness-loop-graph-engineering-2026-07-25|@beamnxw's explainer]]) supplies the sharpest three-way distinction and mnemonic: **harness = the machinery around the model (environment); loop = the repeated work-and-feedback cycle (feedback); graph = the explicit workflow topology — nodes/branches/joins/state/controlled-cycles (flow)** → **"environment → feedback → flow."** The distinctions become load-bearing *"the moment an agent leaves a demo notebook and starts touching files, APIs, customers, or production code."* *(Correction: an earlier note here cited a "ETCLOVG seven-layer paper" — that was tweet-hype; the actual source is @beamnxw's practitioner explainer, not a peer-reviewed paper.)*

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

### Depth: the "loops → graphs" synthesis (Karpathy → AgentHub → Anthropic infra)
A rigorous independent synthesis paper ([[graph-engineering-loops-to-graphs-synthesis-2026-07-24]], 11pp; *not* an Anthropic/Karpathy primary) grounds the meme in real systems and supplies the depth the explainer-tier sources lack:

- **The three-step progression**: **vibe coding** (human intends, model writes) → **agentic engineering** (human specifies / orchestrates / verifies, stays responsible) → **graph engineering** (agents share durable state through typed, queryable graphs of work and knowledge). This is the same [[loop-engineering|prompts→harness→loops]] ladder, extended to where *state* lives.
- **The atom is Karpathy's autoresearch ratchet-loop**: an agent in an executable harness (`prepare.py` fixed / `train.py` mutable / `program.md` = natural-language control spec) proposes one change → commits → evals ~5 min → keeps if the metric improves, else `git reset`. *"program.md is programming the program."* Four conditions make a loop agent-friendly: **verifiable output, reversible action, short horizon, bounded environment.**
- **AgentHub = "GitHub for agents"** (Karpathy's sketch): the **commit DAG *is* the graph** (commits = nodes, parent links = edges); removes convergence abstractions (no main branch, no PRs, no merge queue) because the primary op is *"traverse the search graph,"* not *"merge to main."*
- **Two graphs, not one — and don't collapse them**: the **commit DAG** tracks *work lineage* (what changed, which experiment is the parent); the **knowledge graph** tracks *domain knowledge* (which entities exist, how related, which sources support). Together they *"prevent agents from rebuilding the world from scratch in every context window."*
- **The knowledge graph as shared memory** — the concrete technique ([[knowledge-graph-4-prompts-synthesis-2026-07-24]]): **four Claude prompts with structured outputs replace four trained models** — Extraction (Haiku) for typed entities + S-P-O triples, Resolution (Sonnet) clustering surface forms (*"Edwin Aldrin" → "Buzz Aldrin"*), Summarization (Sonnet) for hub-node profiles, Querying (Sonnet) over a serialized **k=2-hop** subgraph with edge-level citations. *The Pydantic schema is the only training data.* Workers write findings back as graph updates; the orchestrator's context stays small regardless of worker count — *"the agent forgets, the graph does not."* Precision-favoring by design (a wrong entity spawns wrong relations that propagate through multi-hop reasoning).
- **Five-plane production architecture**: control / execution / artifact / graph / evaluation — *"prevents one chat transcript from becoming the database, workflow engine, and audit log."*
- **Staged build path**: Day 1 reflective loop → Day 2 tools → Week 1 planning → Week 2 multi-agent (artifact-contract handoffs, worktree isolation) → Month 1 wire into a graph → Month 2 swarm (define the reducer *before* fan-out).
- **The load-bearing thesis**: *"the bottleneck is often not the next model call — it is the placement of memory and evaluation."* The path from loops to graphs is *"from implicit state to explicit state, volatile to durable memory, estimation to evidence."*
- **Caveats it is honest about**: metrics can be gamed (a ratchet optimizes what it can see — the [[reward-hacking]] failure); dynamic workflows are expensive (1,000-sub-agent runs cost tens of dollars + correlated errors); coherent-context tasks (architecture, narrative, tightly-coupled refactors) *degrade* when fragmented; *"do not introduce a graph merely because the system has agents."*

## Key Papers / Posts
- [[akshay-pachaar-graph-engineering-explainer-2026-07-25]] — the anchor explainer: 3 primitives, 4 hard problems, decision rule (this page's spine)
- [[graph-engineering-loops-to-graphs-synthesis-2026-07-24]] — **the depth source** (11pp independent synthesis): Karpathy autoresearch → AgentHub commit-DAG → Anthropic Dynamic Workflows/KG-cookbook; vibe→agentic→graph progression; five-plane architecture; "place memory outside the context window"
- [[knowledge-graph-4-prompts-synthesis-2026-07-24]] — **the KG-as-shared-memory technique** (7pp independent synthesis): 4 structured-output prompts (Haiku extract / Sonnet resolve+summarize+query) replace 4 trained models; the Pydantic schema is the only training data
- **Anthropic — "Patterns and problems in emerging multi-agent systems"** (research, 2026-08, [[dailybrief-roundup-2026-08-16]]) — a **first-party failure-mode taxonomy** for multi-agent setups: the coordination/observability-debt side of the [[#The four hard problems|four hard problems]] above. The brief's read — *"Anthropic's framing of patterns + failure modes here is the inverse of what most orgs are doing — shipping coordination without understanding it"* — is the same *"don't add a graph merely because the system has agents"* discipline this page argues. *(Primary not fetched; publication noted.)*
- **Hamel Husain — "Loop Engineering Is Dead. Enter Graph Engineering."** (2026-07-18) — the coinage article (referenced via the explainer; primary not fetched)
- **Peter Steinberger** (2026-07-18): *"Are we still talking loops or did we shift to graphs yet?"* — the nine-word prompt that started it
- **LangGraph** (Jan 2024), **AutoGen GraphFlow**, **Google ADK 2.0** — the pre-existing implementations the name retroactively describes

### Adjacent trend — ontologies "are so back" (2026-07-30)
A Latent Space piece (*"Ontologies Are So Back: Why AI Agents Are Reviving the Semantic Web,"* [[dailybrief-roundup-2026-07-30]]) argues agentic systems are pulling **formal ontologies + rules** back into fashion as **deterministic boundaries** — *"once you let a model make decisions, you stop tolerating probabilistic fuzz at the boundary."* This is the same move as graph engineering's **typed knowledge graph as shared memory** ([[knowledge-graph-4-prompts-synthesis-2026-07-24]]) and its **"deterministic code controls predictable routing"** rule: the reliability comes from *structure the model must respect*, not from more model. Framed as a bottom-up revival (enforced by agent error) rather than the semantic web's failed top-down encoding of human meaning — the ground-truth substrate the "many agents agreeing" failure mode needs.

## Related Concepts
- [[loop-engineering]] — the layer directly below; a loop is a one-node self-edged graph, graphs coordinate many loops
- [[context-engineering]] — two layers down; every node call is a context problem
- [[reward-hacking]] — the "agents agree with each other / grade their own homework" failure that reviewer-node discipline exists to prevent
- [[cognition]] — "many readers, one writer" production pattern from running Devin
