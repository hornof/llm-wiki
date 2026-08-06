---
title: "_raw batch roundup — 2026-08-06 (Jeff Dean leaves Google for DiscoLoop AI; SKILL.md progressive-disclosure guide)"
type: source
medium: article
url:
ingested: 2026-08-06
---

## Summary

`_raw/` drops synced 2026-08-06 (no Daily Brief). Two items — one major industry signal, one practitioner guide. Two new pages + two folds.

## Elevated / created

- **Jeff Dean leaves Google (27 years) to co-found DiscoLoop AI** (@JeffDean, X) → new [[jeff-dean]], new [[discoloop-ai]]; folded into [[google-deepmind]]. With **Sanjay Ghemawat, Oriol Vinyals, and Quoc Le** — an all-star departure (MapReduce/Bigtable/TensorFlow/Google-Brain + Gemini co-lead + seq2seq/AutoML). Dean's farewell: *"Google now has thirteen products used by more than a billion people."* **No product/focus disclosed.** Reads as a top-of-org brain-drain from [[google-deepmind]] and a new entrant in the elite-team-new-lab cohort ([[thinking-machines]], [[safe-superintelligence]]).
- **"Simple Guide to SKILL.md"** (r/AskVibecoders) → [[skill-md]]. The cleanest practitioner statement of *why* skills are a separate primitive: **skills are progressive-disclosure (load only when the task matches the description), config (CLAUDE.md/AGENTS.md) is always-on (pushed to every session).** Format: `SKILL.md` (YAML `name` + trigger-carrying `description`) + optional `scripts/`/`references/`/`assets/`; the **description is the routing surface.** Ties directly to the [[handbook-md-long-docs-dont-govern-agents-2026-07-29|long-docs-don't-govern]] + [[context-engineering|selective-context]] thread.

## Cross-cutting synthesis
- **The elite-team-exodus pattern extends to the systems tier**: after Murati (Thinking Machines) and Sutskever (SSI), DiscoLoop is the **Google-infrastructure-pedigree** entry — a signal that even the field's most foundational builders are choosing new small labs over incumbent scale. Worth watching for where the systems-first-scaling school goes next.
- **Skills vs config is the same "structure over prose" theme, at the file level**: don't push everything into every session (the [[handbook-md-long-docs-dont-govern-agents-2026-07-29|HANDBOOK.md]] failure mode) — let the task pull in what it needs. The SKILL.md `description` is the selective-disclosure router.

## Pages Updated
- [[jeff-dean]] (new), [[discoloop-ai]] (new), [[google-deepmind]], [[skill-md]]
