---
name: AI Engineering Skills
type: concept
maturity: emerging
last_updated: 2026-08-14
---

## Definition

**AI Engineering Skills** are the capabilities every developer now needs to build software in the post-2022 way — codified most authoritatively by **[[andrew-ng|Andrew Ng]]'s "AI Engineering Skills Map"** ([[andrew-ng-ai-engineering-skills-map-2026-08-14]], 2026-08-14), synthesized from **10,000+ job postings**, dozens of structured hiring-manager/expert interviews, and surveys. Ng frames these as *skills*, not the *"AI Engineer" role* — the way "cloud skills" are needed by all developers though few hold a "Cloud Engineer" title: *"all developers — full-stack, data, DevOps, ML, and yes AI engineers — will need AI engineering skills."*

## Why It Matters

This is the wiki's mission stated as a curriculum: the **hands-on ramp-up** map for a practitioner (re-)entering AI engineering. It cuts through the *"noisy, hype-filled information environment"* to name what's actually worth learning — and, usefully, each of Ng's four skills maps onto a thread the wiki already tracks in depth, so the map doubles as an index into the rest of the wiki.

## The Four Skills (Andrew Ng, 2026-08)

1. **Building & deploying AI applications** — the defining difference is **unpredictable outputs**; the skill is using statistical technique to *measure, steer, and govern* AI so it behaves predictably. Building blocks: LLMs, [[context-engineering|context engineering]], RAG, [[agentic-ai|agentic workflows]], ML/DL. **Core sub-skill: disciplined evals + error-analysis loops** — the [[loop-engineering|verifier-discipline]] the wiki keeps returning to.
2. **Software-engineering fundamentals** — deep understanding of cost/scalability/reliability/speed/security tradeoffs is what lets you *steer a coding agent in the precise language of software engineering.* Ng's sharp line: an inexperienced dev who *"vibe-codes without knowing the tradeoffs their agent is making… will often get poor ones, because they don't know what context to give"* — the fundamentals are what make [[agentic-engineering]] work (vs [[vibe-coding]]).
3. **Using coding agents** — a good mental model of agent limits + when to intervene vs leave alone; **managing the agent's context**, the plan-vs-execute tradeoff, **providing verifiers/evals to let the agent close loops** ([[loop-engineering]]), working with a spec (*and when not to bother* — cf. [[agentic-engineering|Matt Pocock's disposable-spec]]), **orchestrating multiple agents** ([[graph-engineering]]), and avoiding pitfalls (*"an agent messing up your production database"* — the [[reward-hacking|deployment-hygiene]] lesson). Requires *routines to keep trying new tools* as best practices churn.
4. **Shaping the build** — as agents get better at delivering *to a spec*, the human work shifts to **deciding what's in the spec**: product sense, business context, customer goals; *"engineers should no longer expect a pixel-perfect design to implement."* Plus **ownership/agency** — identify opportunities and drive them (MVP-fast vs build-carefully judgment). This is the same judgment the [[forward-deployed-engineer|FDE]] role and the [[engineering-leadership-ai-era|experienced-founder]] wave price at a premium.

**Underlying mindset**: *continuous learning* — the field churns, so the meta-skill is evolving your own workflow.

## Current State

- **Anchored on a canonical, data-backed source**: [[andrew-ng]] (DeepLearning.AI) + team; *"akin to running clustering on a massive dataset of jobs and expert interviews."* Ng promises per-skill deep-dives + a more detailed map in follow-up posts — **track for the fuller version.**
- **Convergence check**: the map independently ratifies the wiki's spine — evals/verifiers ([[loop-engineering]]), context management ([[context-engineering]]), multi-agent orchestration ([[graph-engineering]]), spec-shaping + product sense ([[forward-deployed-engineer]] / [[engineering-leadership-ai-era]]). A rare case where a mainstream-authority taxonomy and the wiki's accreted threads line up 1:1.

## Related Concepts
- [[agentic-engineering]] — "using coding agents" + "SWE fundamentals" are its skill substrate
- [[loop-engineering]] — the evals/verifiers/close-the-loop discipline inside skills 1 & 3
- [[context-engineering]] — the "manage the agent's context" sub-skill
- [[forward-deployed-engineer]] / [[engineering-leadership-ai-era]] — "shaping the build" (product sense + agency) priced as a role/founder edge
