---
name: Obsidian
type: tool
category: platform
status: mainstream
last_updated: 2026-04-21
---

## What It Is
A local-first markdown note-taking app built around a personal knowledge graph. Notes are plain `.md` files stored on disk; Obsidian adds graph visualization, backlinks, and a plugin ecosystem on top. Made by Obsidian (the company).

## Traction Signals
- Large, active community of knowledge management practitioners ("PKM" space)
- Frequently recommended as the visualization layer for the [[llm-wiki-pattern]]
- Karpathy quote: "Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase." — [[karpathy-llm-wiki-overview]]

## How to Use It
Point Obsidian at the wiki directory as a vault. The graph view then visualizes all `[[wikilink]]` cross-references between pages. No special setup needed beyond opening the folder.

## Key Concepts
- **Vault**: a folder that Obsidian treats as a workspace
- **Wikilinks**: `[[Page Name]]` syntax for cross-references — creates graph edges
- **Graph view**: visual map of all linked pages in the vault
- **Backlinks**: shows all pages that link to the current page

## Compared To
- Notion: cloud-based, more structured, less suited for LLM-maintained markdown
- Roam Research: similar graph approach, subscription-based, less local-first
- Plain markdown + git: works fine for the wiki itself; Obsidian adds visualization

## Resources
- [[karpathy-llm-wiki-overview]] — recommends Obsidian as the visualization tool for LLM wikis
