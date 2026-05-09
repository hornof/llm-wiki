---
name: LLM Wiki Pattern
type: concept
maturity: emerging
last_updated: 2026-05-08

---

## Definition
A pattern for building persistent personal knowledge bases where an LLM incrementally maintains a structured markdown wiki, rather than re-discovering information on every query. Raw sources are "compiled" into synthesized, interlinked pages once — then queried efficiently from the compiled result.

## Why It Matters
Solves the re-discovery problem: every conversation with an LLM starts cold. A wiki externalizes accumulated knowledge so it compounds across sessions. Shifts human effort from filing/organizing to thinking and curation.

> "The tedious part of maintaining a knowledge base is not the reading or the thinking — it's the bookkeeping. Humans abandon wikis because the maintenance burden grows faster than the value. LLMs don't get bored, don't forget to update a cross-reference, and can touch 15 files in one pass." — Karpathy

## Current State
Proposed by Andrej Karpathy. Not a product — it's a workflow pattern you implement yourself (typically with Claude Code + Obsidian or similar). Sweet spot is ~100 curated sources / hundreds of wiki pages; index.md overflows context windows at 100-500 pages, requiring secondary retrieval infrastructure beyond that.

## Three-Layer Architecture
- **Raw sources** (immutable): articles, transcripts, papers you curate
- **The wiki** (LLM-maintained): markdown entity pages, cross-references, summaries
- **The schema** (configuration): `CLAUDE.md` (Claude Code) or `AGENTS.md` (OpenAI Codex / other agents) — defines page structure, ingestion workflows, and answer formatting

## Three Core Operations
- **Ingest**: process a new source, LLM reads and updates 10-15 related wiki pages per source
- **Query**: search compiled wiki, synthesize answers with citations; high-value answers become new wiki pages
- **Lint**: health-check for contradictions, stale claims, orphan pages, missing cross-references

## The Compounding Property
Each ingest doesn't just add new pages — it updates existing ones. When a second source on a related topic is ingested, the LLM reads the existing wiki first, recognizes conceptual connections, and strengthens cross-links that no human added. The wiki gets denser, not just bigger. This is the core value proposition over RAG.

## Key Risks
- **Error propagation**: a wrong summary on ingest gets cross-referenced into 10-15 pages as "fact." Lint is non-negotiable.
- **Knowledge drift**: LLM summaries are lossy; without verification mechanisms summaries drift from originals over time — flagged by community
- **Index overflow**: index.md breaks at 100-500 pages when it exceeds context window; requires secondary retrieval at that scale
- **Contradiction accumulation**: should be detected at ingest time with confidence scoring, not left to accumulate until lint

## Schema Evolution
The schema (CLAUDE.md) is designed to be co-evolved by you and the LLM over time — not defined once and frozen. Adjust it as you learn what works for your specific sources and queries.

## Optional Tool Stack
- **[[obsidian]]**: graph visualization and image handling
- **[[obsidian-dataview]]**: query frontmatter across pages (e.g., all tools with status: gaining-traction)
- **Marp**: generate slide decks from wiki content
- **qmd**: search engine for navigating at scale
- **git**: version history for the entire wiki

## Alternative Implementations (from community)
- **Headkey**: belief graphs with confidence scores
- **NEBULA**: human-defined entity types + LLM-enriched connections
- **CodeDNA**: opt-in wiki pointers (lighter-weight integration)

## When to Use It
- Personal research projects with <200 curated sources
- Reading a book and building a reference wiki as you go
- Tracking a specific evolving topic over months
- Internal team wikis fed by meeting transcripts

## Organizational-Scale Boundary

[[ashwingop]] (May 2026, [[ashwingop-managed-agents-company-brain-2026-05-08]]) names the LLM Wiki as **"directionally right"** alongside Garry Tan's GBrain — markdown is a great medium for personal/small-team brain systems because humans inspect, agents write, Git tracks, the whole thing stays portable. But the pattern hits a scaling boundary when the brain becomes organizational:

- Personal brain: one owner, one trust boundary, one tolerance for messiness, one final arbiter. Bad summary? Fix it. Two pages contradict? Decide.
- Companies don't get that simplicity: multiple writers, multiple readers, inherited permissions, regulated data, stale sources, conflicting teams, and **agents that may act on what they read**.
- "A markdown file can hold information. It does not, by itself, decide who can see it, which ontology applies, whether it is stale, whether it is fact or interpretation, or what happens when two agents update related state at the same time."

This is not a contradiction of the LLM Wiki Pattern — it's a scope marker. Files can be the source. The wiki pattern handles personal/small-team knowledge compounding well. At organizational scale, additional substrate is needed (concurrency, provenance, permission propagation, ontology binding, action traces, evals, deletion, conflict handling) — see [[company-brain]].

## When to Use RAG Instead
- Customer support over constantly-updated docs
- Legal/medical contexts where citation traceability is critical
- Anything with >1000 sources or high source churn

## Optimization Tips (from practitioners)
- Maintain both a global index and folder-specific index files — improves token efficiency for ingestion and retrieval
- Customize front-matter per folder while keeping a consistent base schema
- Log LLM decisions as `.md` files with their own index — aids transparency and owner review
- Two-tier memory (long-term + short-term) via tools like [[mem0]] can extend the pattern

## Hybrid Approach
Combining LLM Wiki with RAG is being explored and considered promising — wiki handles synthesis and compounding; RAG handles high-volume retrieval. [unsourced beyond community discussion]

## Historical Roots
Karpathy's pattern resurrects Vannevar Bush's 1945 **Memex** vision — a personal, curated knowledge store where the connections between documents are as valuable as the documents themselves. The Memex was never practically built because nobody wanted to do the bookkeeping. LLMs finally solve that.

## Compared To
- [[rag]]: better for large dynamic corpora; LLM Wiki better when synthesis and compounding matter more than retrieval scale
- Obsidian alone: requires human to do all the filing; LLM Wiki automates the maintenance burden

## Extensions to the Base Pattern
- **Hot cache**: session memory layer (`wiki/hot.md`) — update at session end so next session starts with full recent context; solves the cold-start problem
- **Contradiction flagging at ingest**: write `[!contradiction]` callouts immediately rather than deferring to lint
- **Batch ingestion via parallel agents**: process multiple sources simultaneously
- **/autoresearch**: autonomous research loop with configurable objectives

## Karpathy's Ongoing Use (Confirmed 2026)
At AI Ascent 2026, Karpathy confirmed he still actively uses a personal LLM Wiki: "Anytime I see a different projection onto information, I always feel like I gain insight. So it's really just a lot of prompts for me to do synthetic data generation over some fixed data... I love asking questions about things." He frames it as a tool to enhance human *understanding* specifically — the bottleneck he identifies is not access to information but the ability to understand and direct. — [[karpathy-vibe-coding-agentic-engineering]]

## Resources
- [[karpathy-llm-wiki-gist]] — PRIMARY SOURCE: Karpathy's original gist
- [[karpathy-llm-wiki-overview]] — Medium article overview of the pattern
- [[reddit-llm-wiki-weekend-build]] — first-hand build experience, practical use-case guidance
- [[karpathy-vibe-coding-agentic-engineering]] — Karpathy confirms active personal use (2026); frames wiki as tool for enhancing understanding, not just information access
