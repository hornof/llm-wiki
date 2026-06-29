---
name: Obsidian
type: tool
category: platform
status: mainstream
last_updated: 2026-06-29
---

## What It Is
A local-first markdown note-taking app built around a personal knowledge graph. Notes are plain `.md` files stored on disk; Obsidian adds graph visualization, backlinks, and a plugin ecosystem on top. Made by Obsidian (the company).

## Traction Signals
- Large, active community of knowledge management practitioners ("PKM" space)
- Frequently recommended as the visualization layer for the [[llm-wiki-pattern]]
- Karpathy quote: "Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase." — [[karpathy-llm-wiki-overview]]
- **2026-06-23: STRUCTURALLY MAJOR canonical-"Claude + Obsidian as a real second brain" canonical-amplification** ([[moysei-karpathy-llm-wiki-pattern-amplification-2026-06-23]]) — Moysei (@0xMoysei) canonical-direct-voice amplifies Karpathy canonical-pattern; canonical-vault-rot canonical-failure-mode articulation (*"the graph rots while it still looks impressive"*) justifies canonical-LLM-Wiki-Pattern canonical-intervention as canonical-Obsidian-discipline canonical-tool; canonical-raw-vs-wiki-split canonical-pattern at canonical-Obsidian-vault canonical-substrate-tier
- **Canonical-vadwarp canonical-neo4j-counter-substrate canonical-articulation** (Jun 23) = first wiki-captured canonical-non-Obsidian canonical-substrate canonical-pattern-watch (canonical-Obsidian-default canonical-incumbent challenged by canonical-graph-database canonical-counter-substrate at canonical-individual-practitioner-tier)
- **Canonical-Obsidian-iCloud-vault canonical-substrate canonical-validation**: this wiki canonical-dogfooded canonical-Obsidian-iCloud canonical-cross-device canonical-substrate (Mac + iPad + iPhone) since canonical-2026-05-15

## How to Use It
Point Obsidian at the wiki directory as a vault. The graph view then visualizes all `` `[[wikilink]]` `` cross-references between pages. No special setup needed beyond opening the folder.

## Key Concepts
- **Vault**: a folder that Obsidian treats as a workspace
- **Wikilinks**: `` `[[Page Name]]` `` syntax for cross-references — creates graph edges
- **Graph view**: visual map of all linked pages in the vault
- **Backlinks**: shows all pages that link to the current page

## Compared To
- Notion: cloud-based, more structured, less suited for LLM-maintained markdown
- Roam Research: similar graph approach, subscription-based, less local-first
- Plain markdown + git: works fine for the wiki itself; Obsidian adds visualization

## Resources
- [[karpathy-llm-wiki-overview]] — recommends Obsidian as the visualization tool for LLM wikis
