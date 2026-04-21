---
name: LLM Wiki Pattern
type: concept
maturity: emerging
last_updated: 2026-04-21

---

## Definition
A pattern for building persistent personal knowledge bases where an LLM incrementally maintains a structured markdown wiki, rather than re-discovering information on every query. Raw sources are "compiled" into synthesized, interlinked pages once — then queried efficiently from the compiled result.

## Why It Matters
Solves the re-discovery problem: every conversation with an LLM starts cold. A wiki externalizes accumulated knowledge so it compounds across sessions. Shifts human effort from filing/organizing to thinking and curation.

## Current State
Proposed by Andrej Karpathy. Pattern is early-stage and gaining attention among AI practitioners. Not a product — it's a workflow pattern you implement yourself (typically with Claude Code + Obsidian or similar). Sweet spot is ~100 curated sources / hundreds of wiki pages; index.md overflows context windows at 100-500 pages, requiring secondary retrieval infrastructure beyond that.

## Three-Layer Architecture
- **Raw sources** (immutable): articles, transcripts, papers you curate
- **The wiki** (LLM-maintained): markdown entity pages, cross-references, summaries
- **The schema** (configuration): CLAUDE.md or equivalent file defining structure and workflows

## Three Core Operations
- **Ingest**: process a new source, LLM reads and updates 10-15 related wiki pages per source
- **Query**: search compiled wiki, synthesize answers with citations; high-value answers become new wiki pages
- **Lint**: health-check for contradictions, stale claims, orphan pages, missing cross-references

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

## Compared To
- [[rag]]: better for large dynamic corpora; LLM Wiki better when synthesis and compounding matter more than retrieval scale
- Obsidian alone: requires human to do all the filing; LLM Wiki automates the maintenance burden

## Resources
- [[karpathy-llm-wiki-gist]] — PRIMARY SOURCE: Karpathy's original gist
- [[karpathy-llm-wiki-overview]] — Medium article overview of the pattern
- [[reddit-llm-wiki-weekend-build]] — first-hand build experience, practical use-case guidance
