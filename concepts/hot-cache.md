---
name: Hot Cache
type: concept
maturity: emerging
last_updated: 2026-04-21
---

## Definition
A file (`wiki/hot.md`) that stores a summary of recent wiki context, updated automatically at the end of every session. The next session loads this file first, giving the LLM full awareness of recent ingests and queries without the user needing to recap.

## Why It Matters
Solves the cold-start problem in LLM wikis: each new conversation starts with no memory of prior sessions. Without a hot cache, the LLM must either re-read the entire wiki or start blind. The hot cache is a lightweight "working memory" layer — recent enough to be relevant, compact enough to fit in context.

## How It Works
1. At session end, LLM writes a summary of what was ingested, queried, and changed
2. `hot.md` is stored in the wiki (typically `wiki/hot.md`)
3. At session start, LLM reads `hot.md` before anything else
4. Over time, older context rolls off as newer context replaces it

## Relationship to Other Layers
- **hot.md**: recent context (session-level)
- **index.md**: full content catalog (wiki-level)
- **log.md**: append-only operation history (permanent)

Hot cache fills the gap between ephemeral conversation memory and the full wiki index.

## Origin
Introduced in [[claude-obsidian]] as an extension to Karpathy's original LLM Wiki pattern. Not part of the base [[llm-wiki-pattern]].

## Resources
- [[github-claude-obsidian]] — source; hot cache described as core feature
