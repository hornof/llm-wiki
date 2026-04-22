# llm-wiki

A personal AI Engineering knowledge base, built on [Andrej Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

Rather than re-deriving knowledge on every query, this wiki compiles sources into structured, interlinked markdown pages that compound over time. New sources update existing pages. The graph gets richer with every ingest.

Maintained by [Luke Hornof](https://github.com/hornof) — AI Engineering Leader | founder (acq.) · PhD in CS · CTO · Intel Nervana

---

## How It Works

Three operations, driven by Claude Code + the schema in `CLAUDE.md`:

| Operation | What it does |
|-----------|-------------|
| **Ingest** | Drop a source into `_raw/` (article, Twitter thread, Reddit post, podcast transcript) → Claude extracts entities and updates 10–15 wiki pages |
| **Query** | Ask a question → Claude reads relevant pages and synthesizes an answer with citations |
| **Lint** | Health check → finds orphan pages, broken links, stale content, contradictions |

Sources come primarily from Twitter/X, Reddit, podcasts, and GitHub. The Obsidian Web Clipper sends articles to `_raw/` in one click.

---

## Structure

```
_raw/          # Immutable source drops (gitignored)
sources/       # One page per ingested source
tools/         # AI tools and frameworks
models/        # Model families and providers
concepts/      # Foundational and emerging AI concepts
people/        # Key researchers and practitioners
companies/     # AI labs and startups
topics/        # Themes spanning multiple entities
tutorials/     # Hands-on guides and walkthroughs
index.md       # Content catalog
log.md         # Append-only operation history
CLAUDE.md      # Schema — entity page templates, workflows, conventions
```

---

## Current Contents

**Tools** · claude-code · claude-obsidian · claude-canvas · crewai · langchain · llama-index · mem0 · obsidian · obsidian-dataview · ollama

**People** · Andrej Karpathy · Andrew Ng · Demis Hassabis · Fei-Fei Li · Agrici Daniel · OrewaDeveloper

**Concepts** · LLM Wiki Pattern · RAG · AGI · Hot Cache

**Companies** · Google DeepMind

**Topics** · Agentic AI

---

## Setup

1. Clone the repo and open the folder as an [Obsidian](https://obsidian.md) vault for the graph view
2. Install [Claude Code](https://code.claude.com) and open the same folder
3. Drop sources into `_raw/` (or use the [Obsidian Web Clipper](https://obsidian.md/clipper))
4. Tell Claude: *"ingest new content"*

The schema in `CLAUDE.md` defines all entity page templates, source handling per medium, and the three workflows.

---

## Credits

Based on [Andrej Karpathy's LLM Wiki gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f). Tooling by [claude-obsidian](https://github.com/AgriciDaniel/claude-obsidian).
