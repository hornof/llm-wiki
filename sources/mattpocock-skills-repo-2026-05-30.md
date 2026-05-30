---
title: "mattpocock/skills — Skills for Real Engineers (112.1K stars; cross-vendor npx-installable skill registry)"
type: source
medium: github-repo
url: https://github.com/mattpocock/skills
ingested: 2026-05-30
---

## Summary

[Matt Pocock](https://github.com/mattpocock)'s **`skills`** repository surfaces in 2026-05-30 Daily Brief Repos-Worth-Watching with **112,100 stars** (Digg AI Score 10/10). Matt Pocock is a well-known TypeScript educator (Total TypeScript course; significant X / YouTube presence). The repo is **"Skills for Real Engineers" — a curated collection of composable prompt-based skills for LLM coding agents (Claude, Codex, etc.) distributed as a shell-installable package via `npx skills@latest`.** **Highest-star wiki-captured Claude-Code/Codex-skills artifact**, structurally important as a *cross-vendor* skill-distribution model. Primary not deeply fetched — repo URL + brief framing only.

## Key Claims / Takeaways

### Repo headline characteristics (per brief framing)

- **112,100 GitHub stars** — exceeds the [[forrest-chang|forrest-chang/andrej-karpathy-skills]] ~120K-star repo (which I previously thought was the practitioner-canonical skills repo). **Among the highest-star wiki-captured Claude-adjacent OSS artifacts of 2026.**
- **Distribution mechanism**: `npx skills@latest` — installable via npm package manager. Significantly more frictionless than the *clone-the-repo-and-copy-files* pattern of the [[forrest-chang|forrest-chang]] / [[hassid-cowork-setup-2026-04-07|hassid-cowork-setup]] / [[stahlberg-team-os-aakash-2026-05|Stulberg Team OS]] cohort.
- **Cross-vendor scope**: *"for LLM coding agents (Claude, Codex, etc.)"* — explicitly **not Claude-only**. Pairs with [[sqlite-agents-md-2026-05-27|SQLite AGENTS.md]] and [[nate-herk|Nate Herk's]] tool-agnostic root structure as the **vendor-neutral practitioner-content trajectory** that's been compounding through May 2026.
- **Content scope**: "grilling sessions…" (brief truncates) — substantive content surface not fully captured. **Primary fetch needed** to enumerate the skill catalog.

### Strategic significance

1. **Highest-star practitioner-content artifact in the Claude-Code/Codex-skill ecosystem.** 112K stars > forrest-chang's ~120K star [[forrest-chang|original 4-rule template]] — though Pocock's repo may have been measured later. Either way, the *npm-distributable* form factor is structurally important.
2. **`npx`-installable skill distribution is a meaningful UX shift.** Compare:
   - Pre-Pocock pattern: clone repo → copy files → adapt → commit ([[forrest-chang|Chang]] / [[hassid-cowork-setup-2026-04-07|Hassid]] / [[stahlberg-team-os-aakash-2026-05|Stulberg]] / [[heeki-spec-driven-development-2026-02-28|Park]])
   - Pocock pattern: `npx skills@latest` → installed-and-ready (similar to how `eslint-config-*` packages distribute lint configs)
   - **Implication**: skill-distribution UX is converging toward the npm-package model. Worth tracking whether [[dac|bruin-data/dac]]'s SKILL.md model and [[anthropic-founders-playbook-2026-05|Anthropic-canonical product matrix]] similarly adopt npm-installable forms.
3. **Cross-vendor by default**: *"Claude, Codex, etc."* — Pocock's framing predates [[sqlite-agents-md-2026-05-27|SQLite's AGENTS.md]] adoption as a structural sibling-pattern signal. Pocock's repo is the **practitioner-content register evidence** for the same standardization-over-stratification path. Pairs with the AGENTS.md namespace-divergence question in the [[claude-md-pattern#AGENTS.md: vendor-neutral sibling pattern (SQLite adoption, 2026-05-27)|CLAUDE.md pattern page]].

### Pocock as practitioner

- **TypeScript educator** with major content presence (Total TypeScript course; YouTube; X). High-signal voice in the developer-tooling-and-education category.
- **Wiki entity page status**: not yet created. Worth fast-tracking if a second wiki-tracked Pocock signal lands (e.g., specific skill content from this repo gets cited by another practitioner-content source). For now, defer per single-source-defer pattern.
- **Brief framing's catalog hint**: *"covering grilling sessions…"* — implies content categories beyond just code-quality skills (the *grilling* term suggests interview-prep / code-review / debugging adversarial-prompting). Primary fetch would resolve.

### Adjacent same-day repo signals

The 2026-05-30 brief lists 4 other repos worth watching alongside Pocock's:
- **EvolvingLMMs-Lab/NEO** (796★) — Python repo for *native encoder-free vision-language models that unify pixel-word encoding, alignment and reasoning inside a single monolithic dense* model. Adjacent to [[spatial-intelligence|spatial-intelligence research]] / [[world-labs|World Labs]] cluster.
- **arjunrajlaboratory/mycelium** (2★) — Claude Code plugin with `.living/` memory layer + structured manifests + convention packs + slash-command skills. **First wiki-captured `.living/`-memory-layer convention** — pairs with [[mem0]] and [[company-brain]] as emerging agent-memory infrastructure patterns. Despite the tiny star count, the convention is wiki-worth-tracking.
- **google-gemma/gemma-skills** (1★) — Gemma LLM skills installed via Vercel skills installer. First wiki-captured Google-side skills-distribution analog of Pocock's npm pattern. **Tracking signal**: does the Vercel-installable form factor compete with Pocock's npm-installable form factor as Anthropic / OpenAI / Google all converge on skill-distribution UX?
- **mims-harvard/AutoScientists** (193★) — decentralized AI agent teams using Claude Code subagents coordinated via local ClawInstitute server for long-running scientific tasks (nanoGPT optimization!). Adjacent to the [[deepmind-llm-lean-erdos-oeis-2026-05-25|DeepMind LLM-Lean]] and [[vibe-physics]] cluster on AI-for-science.

**Cross-cut pattern**: 4 out of 5 brief-flagged repos for the day are **Claude-Code-adjacent skill / agent / extension** repos. **Skill-distribution UX is converging on multiple form factors at once** (npm-installable per Pocock; Vercel-installable per gemma-skills; Claude Code plugin per mycelium; local-server coordinator per AutoScientists). Worth watching which form factor becomes the dominant pattern over the next 60-90 days.

### What's notably absent from the brief

- **Specific skills cataloged** in the Pocock repo (the *"grilling sessions…"* fragment is incomplete)
- **License / open-source posture** for Pocock's repo
- **Whether the 112K stars are recent (May-2026-launch-spike) or accumulated** (Pocock has been on GitHub for years)
- **Pocock's own framing of the project** — any blog post or X thread explaining design intent?
- **Comparison to Anthropic-official skills surface** — does Anthropic Founder's Playbook product matrix engage with Pocock's repo?

## Pages Updated

- [[claude-md-pattern]] — Pocock's npm-installable skills repo added as the **highest-star practitioner-content artifact** in the cohort; cross-vendor framing adds another stratification-side data point alongside Nate Herk's tool-agnostic root and SQLite's AGENTS.md
- [[claude-code]] — Pocock skills repo added under Resources as *highest-star cross-vendor skill-distribution mechanism*
- [[mem0]] / [[company-brain]] — arjunrajlaboratory/mycelium's `.living/`-memory-layer convention noted as emerging agent-memory pattern

Verification-pending: Pocock's skill catalog (primary fetch); license; star-count accumulation timeline; Pocock's own design-intent framing; whether Anthropic engages with the repo as canonical or competitive.

## Adjacent sources

- [[dailybrief-roundup-2026-05-30]] — same-day brief covering the other repo signals + Willison tooling + Sottiaux GPT-5.5 roadmap
- [[forrest-chang]] — prior practitioner-canonical skills repo (Karpathy-skills lineage)
- [[hassid-cowork-setup-2026-04-07]] / [[stahlberg-team-os-aakash-2026-05]] / [[heeki-spec-driven-development-2026-02-28]] — adjacent practitioner-content register surfaces using non-npm distribution
- [[sqlite-agents-md-2026-05-27]] — structural sibling-pattern for the vendor-neutral standardization path
- [[anthropic-founders-playbook-2026-05]] — Anthropic-canonical product matrix; pairs as the *frontier-lab-published* form factor adjacent to Pocock's *practitioner-published* form factor
