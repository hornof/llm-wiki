---
title: "Chewa (@chewadot) — \"The Self-Writing Vault: 8 Rules for Pointing Claude at Obsidian and Letting It Run Without You\""
type: source
medium: twitter-thread
url: https://x.com/chewadot/status/2071564521735684253
ingested: 2026-07-13
---

## Summary

@chewadot publishes (2026-06-29) an **8-rule practitioner playbook** for pointing Claude (via [[mcp|MCP]]) at an [[obsidian|Obsidian]] vault and letting it maintain itself autonomously — a concrete operationalization of the [[llm-wiki-pattern|LLM Wiki Pattern]]. Framing anecdote: a science-journal editor with 2,400 markdown files he hadn't opened in a year connects Claude on a Monday and by Sunday ships a piece abandoned in 2019. *"One you hold together with willpower; the other holds itself together."* Directly relevant to this wiki, which is itself an instance of the pattern.

## Key Claims / Takeaways — the 8 rules

1. **Voice beats keyboard** — dictate into `inbox/`; notes that require typing don't get made. Claude sorts the rest.
2. **One inlet, many outlets** — exactly one dump folder (`inbox/`); Claude builds `topics/`, `projects/`, `people/` out of it. (The wiki's own single-`_raw/`-drop-zone discipline.)
3. **Morning belongs to Claude, night belongs to you** — a **6:30–8:00 cron job** reads everything new in `inbox/`, files it, drops `[[backlinks]]` into the graph, and writes a digest into the daily note. A **time-based [[loop-engineering|loop]]**: scheduling replaces the human kickoff.
4. **The `raw/` folder is sacred** — nothing in `inbox/raw/` is ever edited (by you *or* Claude); cleaned versions go to `processed/`. Raw stays as *"a geological layer"* — the wiki's immutable-raw-sources principle.
5. **The backlink matters more than the note** — encode in the system prompt: *"every new note gets at least three backlinks to existing notes, and one to a note that's 2+ years old."* Forces graph density, not just accumulation.
6. **The Sunday synthesis is the only thing you'll reread** — weekly, Claude reads the last 7 days and writes `weekly-synthesis/2026-Www.md`: recurring themes, contradictions in your own thinking, half-made promises. (An outer-loop synthesis step.)
7. **Context into every session** — each chat auto-loads vault state (what you're working on, open hypotheses, last decisions) instead of "hi, I'm Ivan." The [[context-engineering|context-engineering]] / hot-cache discipline for a personal vault.
8. **The graph is the vault's pulse** — rising link density = alive; files accumulating without connections = *"a warehouse, not a second brain."* Graph-density as the one health metric (the wiki's [[llm-wiki-pattern|lint]] concern).

## Why it matters

- **Fresh practitioner surface for [[llm-wiki-pattern]]** — operationalizes the pattern's abstract three-layer architecture into a concrete daily-autonomy playbook (cron auto-filing + backlink quotas + weekly synthesis + immutable raw). Complements the Karpathy origin and the [[moysei-karpathy-llm-wiki-pattern-amplification-2026-06-23|Moysei amplification]].
- **Bridges three wiki concepts**: [[llm-wiki-pattern]] (the vault), [[loop-engineering]] (rules 3 & 6 are scheduled/synthesis loops), and [[context-engineering]] (rule 7 is per-session context loading).
- **Register**: practitioner content-creator (ends with repost/follow CTA); the anecdote is illustrative, not a verified case study.

## Pages Updated
- [[llm-wiki-pattern]]
