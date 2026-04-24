# llm-wiki

A personal AI Engineering knowledge base, built on [Andrej Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

Rather than re-deriving knowledge on every query, this wiki compiles sources into structured, interlinked markdown pages that compound over time. New sources update existing pages. The graph gets richer with every ingest.

Maintained by [Luke Hornof](https://github.com/hornof) — AI Engineering Leader | founder (acq.) · PhD in CS · CTO · Intel Nervana

---

## How It Works

Three operations, driven by Claude Code + the schema in `CLAUDE.md`:

| Operation | What it does |
|-----------|-------------|
| **Ingest** | Drop a source into `_raw/` → Claude extracts entities and updates 10–15 wiki pages |
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

**Tools** · claude-code · crewai · langchain · llama-index · mem0 · obsidian · obsidian-dataview · ollama · stitch

**People** · Andrej Karpathy · Andrew Ng · Demis Hassabis · Fei-Fei Li · Yann LeCun · OrewaDeveloper

**Concepts** · LLM Wiki Pattern · RAG · AGI · MCP · Spatial Intelligence · World Models · Agentic AI

**Companies** · Google DeepMind · OpenAI · AMI Labs

---

## Build Your Own

Start your own LLM Wiki in about 10 minutes.

**Prerequisites**
- [Claude Code](https://claude.ai/code) — requires a paid Claude subscription
- [Obsidian](https://obsidian.md) — free

**Steps**
1. Create a folder with a `_raw/` subdirectory
2. Open Claude Code in that folder
3. Paste [Karpathy's gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) and tell Claude to help you set up an LLM Wiki — it will ask what your wiki is about, then write a `CLAUDE.md` schema tailored to your use case
4. Drop sources into `_raw/` and tell Claude: *"ingest new content"*
5. Open the folder as an Obsidian vault for the graph view

For a detailed walkthrough, see [OrewaDeveloper's Medium article](https://medium.com/@urvvil08/andrej-karpathys-llm-wiki-create-your-own-knowledge-base-8779014accd5).

---

## Credits

Based on [Andrej Karpathy's LLM Wiki gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f). Explained well by [OrewaDeveloper's Medium article](https://medium.com/@urvvil08/andrej-karpathys-llm-wiki-create-your-own-knowledge-base-8779014accd5).
