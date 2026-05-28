---
title: "SQLite adds AGENTS.md: directing AI agents how to contribute"
type: source
medium: article
url: https://simonwillison.net/2026/May/27/sqlite-agents/
ingested: 2026-05-28
---

## Summary

[[simon-willison|Simon Willison]] post (2026-05-27) surfacing the **SQLite project adopting AGENTS.md** as a guardrail document for AI-agent contributors. Surfaced via 2026-05-28 Daily Brief; primary not deep-fetched. **First wiki-captured AGENTS.md adoption by a Tier-1 OSS project.** The brief frames it as *"open-source norms shifting to accommodate AI-assisted code. Practical pattern (guardrails for agent PRs) worth replicating. Structural insight into how maintainers are adapting."* AGENTS.md is the *sibling-or-competitor* pattern to [[claude-md-pattern|CLAUDE.md]] — same idea (a contract document the agent reads before acting), different namespace, and notably **vendor-neutral** (not Claude-specific).

## Key Claims / Takeaways

### Why SQLite is the load-bearing adoption signal

- SQLite is one of the most widely-deployed pieces of software on Earth (every Android phone, every Apple device, every Python install, most browsers). Maintainer rigor is extremely high; the project is famously *not* on GitHub, runs its own version control (Fossil), and Hipp's bar for accepting contributions is famously stringent.
- **If SQLite adopts a convention, the gravitational pull on practitioner-norms is large.** Adoption by SQLite is a stronger signal of *practitioner-normalization* than adoption by any single fast-moving startup.
- **First wiki-captured AGENTS.md adoption by a tier-1 OSS project.** Pattern-watch is whether the next ~10 high-rigor OSS projects (curl, ffmpeg, GNU coreutils, Python stdlib, etc.) follow.

### AGENTS.md vs CLAUDE.md (the namespace divergence)

- [[claude-md-pattern|CLAUDE.md]] is the **vendor-specific** pattern surfaced by [[forrest-chang]] (the original 4-rule template), validated across [[hannah-stulberg|Stulberg]] / [[zephyr]] / [[capone]] / ShilpaMitra / [[hassid-cowork-setup-2026-04-07|Hassid]] / arps18 — **6+ independent practitioner-validation surfaces** as of [[dailybrief-roundup-2026-05-27]].
- **AGENTS.md is the vendor-neutral cousin**: same shape (a steering document the agent reads on startup), no Claude-specific framing.
- **The namespace divergence question**: does the community standardize on AGENTS.md (vendor-neutral) or stratify (CLAUDE.md for Claude-specific behavioral contracts, AGENTS.md for cross-vendor guardrails)? SQLite's adoption is evidence for the vendor-neutral path, but [[dac]]'s SKILL.md (ships for both Claude Code *and* Codex) is evidence for the stratification path. **Open question worth tracking.**
- **The PolyArch/humanize RLCR plugin** (Claude implements + Codex reviews, per [[dailybrief-roundup-2026-05-27]]) is also vendor-neutral in pattern but uses Claude-specific tooling — adds nuance to the same question.

### Practical pattern implications

- **Guardrails for agent PRs** is the named use case: directing agents *how* to contribute, not just *that* they can contribute. The implication is that OSS-maintainer-side practitioner work is shifting from *receiving AI-generated PRs and rejecting bad ones* to *preempting bad PRs via behavioral-contract documents.*
- **Pairs structurally with [[cyb3rops-four-stages-ai-coding-hype-2026-05-26|Crickett's "ensure the context is clear, ensure the requirements are clear"]] counter-prescription** to the stage-3 grind phase — AGENTS.md is the OSS-side mechanism for context-and-requirements clarity, applied as a permanent project artifact rather than a per-session prompt.
- **Pairs with [[ai-vulnerability-discovery]] / [[concepts/ai-vulnerability-discovery|the curl maintainer-burden surface]]**: AI-assisted-fuzz reports are flooding maintainers (curl: 4-5x YoY per the brief). AGENTS.md is a *write-side* mechanism (prevent bad AI contributions); the curl situation is the *read-side* mechanism (handle bad AI submissions). Both are AI-flood-coping patterns at the OSS-maintenance layer.

### What's notably absent from the brief

- **Specific content of SQLite's AGENTS.md**: not surfaced.
- **Whether Hipp authored it personally** (Hipp's personal involvement would be the strongest signal): not specified.
- **Whether SQLite considered CLAUDE.md and rejected it** (or whether AGENTS.md was the default they encountered): unclear.
- **Adoption-rate data for AGENTS.md across other major OSS projects**: not surfaced.

## Pages Updated

- [[claude-md-pattern]] — AGENTS.md added as the vendor-neutral sibling pattern; SQLite adoption noted as first tier-1 OSS adoption signal; namespace-divergence open question flagged
- [[ai-vulnerability-discovery]] — AGENTS.md as the write-side complement to AI-flood maintainer-burden (curl YoY) — *(updated if curl entry exists; otherwise referenced cross-link)*

Verification-pending: SQLite AGENTS.md verbatim content; Hipp's personal involvement; adoption-rate across other tier-1 OSS projects (curl, ffmpeg, Python stdlib, etc.); whether AGENTS.md and CLAUDE.md coexist in mixed-vendor projects.

## Adjacent sources

- [[dailybrief-roundup-2026-05-28]] — full roundup including curl-pressure (sibling AI-flood OSS-maintainer signal)
- [[hassid-cowork-setup-2026-04-07]] — Hassid's CLAUDE.md folder architecture (one of the 6+ validation surfaces for the vendor-specific pattern)
- [[heeki-spec-driven-development-2026-02-28]] — Heeki Park's *"frequently took learnings from the project and integrated them into my CLAUDE.md steering document"* — 7th+ practitioner-validation surface
