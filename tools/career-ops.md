---
name: career-ops
type: tool
category: cli
status: gaining-traction
last_updated: 2026-07-06
---

## What It Is

**career-ops** is an open-source AI job-search system built entirely on Claude Code, authored by [@santifer](https://github.com/santifer). It evaluates job postings, generates ATS-optimized PDFs, researches salaries, prepares interview answers, and tracks pipeline state — all from a single slash command pointed at a job URL. MIT licensed; **8.2k GitHub stars** at announcement (April 30 2026) — [[heygurisingh-career-ops]].

The author built it during a layoff to evaluate 740+ job offers, landed a Head of Applied AI role, and then open-sourced the system. As such, career-ops doubles as both a working tool and a **portfolio piece for the Claude Code skill-stack pattern**.

## Traction Signals

- **8.2k GitHub stars** at announcement, April 30 2026 — independent of X virality, suggests real adopter interest — [[heygurisingh-career-ops]]
- **Open source under MIT** — no paywall or DM-gate; reproducible by other practitioners
- **Author shipped it after using it on themselves**: 740+ offers evaluated, real job landed (Head of Applied AI). Self-validation before public release is unusual and adds credibility
- Cross-mention: appears in same-week practitioner output as [[alfiejcarter-linkedin-claude-stack]]; both stacks use Playwright MCP — converging convention for real Claude Code tool stacks
- **2026-06-27 to 2026-07-02 canonical-5-voice canonical-AI-native-roles-and-architecture-evolution canonical-cluster canonical-adjacent-positioning**: career-ops canonical-positioning canonical-directly-in-the-space canonical-articulated by canonical-Greg-Isenberg canonical-3-pillar canonical-AI-native-company + canonical-Boris-Cherny canonical-5-archetype canonical-future-roles + canonical-Andrew-Ng canonical-3-loop canonical-Loop-Engineering + canonical-Khairallah canonical-6-phase canonical-roadmap-to-AI-engineer + canonical-Anatoli-Kopadze canonical-agent-spectrum. **career-ops as canonical-existence-proof of canonical-portfolio-over-credentials canonical-Khairallah-thesis + canonical-agent-leveraged-professional-software canonical-Cherny-tandem-human-AI-tier**.

## How to Use It

Repo: https://github.com/santifer/career-ops

Single-command entry point: paste a job URL, get back a structured A-F evaluation, ATS-optimized PDF, salary research, interview prep, and tracker entry. The 14 skill modes (named in [[heygurisingh-career-ops]]) decompose the pipeline:

- `evaluate` — A-F fit score with reasoning
- `scan` — portal scanner across pre-loaded companies
- `pdf` — ATS-optimized PDF generation via Playwright (Space Grotesk + DM Sans)
- `batch` — evaluates 10+ offers in parallel using Claude sub-agents
- `apply`, `deep research`, `negotiation scripts`, `LinkedIn outreach` — additional named modes
- 6 further unnamed modes (per the announcement)

Plus a **Go terminal dashboard built with Bubble Tea** to browse the pipeline outside Claude Code.

## Key Concepts

- **Skill modes** — each major pipeline stage is its own Claude Code skill file. This is the [[writing-claude-code-skills]] decomposition pattern at production scale (14 skills).
- **Portal scanner** — pre-loaded with 45+ companies (Anthropic, OpenAI, ElevenLabs, Mistral, Cohere, Stripe, Retool, Vercel, Decagon, etc.) and 19 search queries across Ashby, Greenhouse, Lever, Wellfound, Workable.
- **Story Bank** — accumulates **STAR + Reflection** interview stories across evaluations, building toward 5-10 master answers covering any behavioral question. **Continuous learning across sessions**, not one-shot generation.
- **Filter, not firehose** — the system literally refuses to recommend applying to roles scoring below 4.0/5. Inversion of typical "auto-apply to 1000 jobs" growth-hack tools.
- **Self-modifiable** — because career-ops *is* a Claude Code skill stack reading its own files, the user can ask Claude to rewrite the system itself ("change the archetypes to backend roles," "add these 10 companies," "translate the modes to English"). The [[llm-wiki-pattern]] applied to a tool's own configuration.

## Architecture Notes

career-ops is interesting structurally because it combines layers most Claude Code projects keep separate:

1. **Skill layer** — 14 markdown skill files orchestrating Claude.
2. **Tool integration layer** — [[playwright-mcp]] for ATS PDF generation; CV/JD reasoning for fit evaluation.
3. **Sub-agent parallelism** — `batch` mode uses real Claude Code sub-agents (separate context windows) to evaluate 10+ offers in parallel. Real parallel execution, not prompt-time persona simulation.
4. **Native UI on top** — a Go TUI built with [Bubble Tea](https://github.com/charmbracelet/bubbletea) for browsing pipeline state. **A Claude Code skill stack with a separate Go TUI on top of it** crosses from "pure prompt scaffolding" into "real software product."

## Compared To

- **Spray-and-pray auto-apply tools** (Sonara, LazyApply, etc.): career-ops is the explicit inversion — refuses low-fit recommendations rather than maximizing application volume.
- **LinkedIn-native AI features** (Easy Apply with AI suggestions): scoped to one platform, not configurable, no batch evaluation, no Story Bank persistence.
- **JobScan / Resume Worded** (ATS scoring SaaS): single-purpose; no pipeline integration, no continuous-learning loop, requires manual upload per job.
- **Custom GPTs / Claude Projects**: closest analog — a configured AI for a single domain. career-ops differs in being a *file-based, version-controllable, self-modifiable* skill stack rather than a vendor-locked configuration.

## Why Track It

For this wiki specifically, career-ops is worth tracking as **a flagship existence proof** for several patterns the wiki cares about:

- [[writing-claude-code-skills]] — 14-skill decomposition at production scale
- [[agentic-engineering]] — agent-leveraged professional software with real sub-agent parallelism
- [[llm-wiki-pattern]] — applied recursively (the tool's own config is its knowledge base)
- "Filter not firehose" as a counter-narrative to mass-automation AI tools

## Resources

- GitHub: https://github.com/santifer/career-ops
- [[heygurisingh-career-ops]] — announcement post; 8.2k stars datapoint
- Author: santifer (GitHub handle; no separate person page warranted from a single mention)
- Related: [[claude-code]], [[playwright-mcp]], [[writing-claude-code-skills]]
