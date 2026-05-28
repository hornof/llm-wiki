---
name: CLAUDE.md Pattern
type: concept
maturity: emerging
last_updated: 2026-05-28
---

## Definition

**CLAUDE.md** is a per-project configuration file at a repository root that gives [[claude-code]] persistent context and behavioral instructions across sessions — equivalent to a system prompt for a codebase. The "CLAUDE.md pattern" is the practitioner-evolved discipline of treating this file not as a configuration dump but as a **behavioral contract**: each rule should answer the question *"what specific mistake does this prevent?"*

Distinct from [[llm-wiki-pattern]], which is about source-curation across a knowledge base. CLAUDE.md is local to a single coding project; the wiki pattern is global to a knowledge corpus. Both share the convention that the file is co-evolved between human and LLM over time.

## Why It Matters

CLAUDE.md sits between zero-shot prompting (high token cost, no consistency) and exhaustive style guides (compliance falls off as length grows). When tuned, it materially reduces classes of recurring Claude failures — silent wrong assumptions, over-engineering, "orthogonal damage" to nearby code, silent successes hiding silent failures — without per-task re-prompting.

A community-quoted claim ([[mnilax-claude-md-12-rules-2026-05-09]], citing Anthropic docs as source) is that **CLAUDE.md is advisory: Claude follows it ~80% of the time, and compliance drops sharply past 200 lines** as important rules get buried. This makes the CLAUDE.md pattern a constraint-driven design exercise, not a policy-document one.

## Current State

### Lineage (January–May 2026)
- **Late January 2026**: [[andrej-karpathy]] posts an X thread complaining about Claude code-writing failure modes (silent assumptions, over-complication, orthogonal damage).
- **Within days**: [[forrest-chang]] packages the complaints into 4 behavioral rules in a single CLAUDE.md, opens a GitHub repo. Repo grows to **~120,000 stars by May 2026** (claim from [[mnilax-claude-md-12-rules-2026-05-09]]) — described as the fastest-growing single-file repo of 2026.
- **April–May 2026**: practitioners testing the 4-rule template across many codebases find it covers ~40% of failure modes but leaves multi-step / multi-codebase / test-quality / silent-failure gaps unaddressed. @Mnilax publishes a 12-rule expansion (May 9 2026) tested across 30 codebases over 6 weeks, claiming a drop from 41% (no CLAUDE.md) → 11% (Karpathy's 4) → 3% (full 12) on a 50-task evaluation panel. — [[mnilax-claude-md-12-rules-2026-05-09]]

### The 4-rule baseline (Karpathy / Forrest Chang)
1. **Think Before Coding** — state assumptions, ask before guessing.
2. **Simplicity First** — minimum code, no speculative features.
3. **Surgical Changes** — touch only what you must, match existing style.
4. **Goal-Driven Execution** — define success criteria, loop until verified.

### The 8-rule expansion (@Mnilax, May 2026)
5. Use the model only for judgment calls (not for deterministic transforms / retries / routing).
6. Token budgets are not advisory (per-task / per-session caps; surface breaches).
7. Surface conflicts, don't average them.
8. Read before you write.
9. Tests verify intent, not just behavior.
10. Checkpoint after every significant step.
11. Match the codebase's conventions, even if you disagree.
12. Fail loud.

### Design principles practitioners converge on
- **Imperative over conversational** — concrete actions ("state assumptions explicitly"), not soft language ("be careful").
- **Testable over aspirational** — every rule should map to a mistake the rule prevents.
- **Capability-agnostic** — avoid tooling-dependent rules ("always use eslint") that fail silently when the tool is absent.
- **Rules over examples** — examples cost ~10× the context of rules and Claude over-fits to them.
- **No identity prompts** — "be a senior engineer" doesn't move behavior; Claude already thinks it's senior. Imperatives close the thinking-vs-doing gap; identity prompts don't.
- **Customize, don't copy** — keep the rules that map to mistakes you've actually made; drop the rest.

### Connection to other Claude Code patterns
- **Skill writing** ([[claude-code]] §Skill Writing) — same imperative-over-conversational logic; descriptions = WHEN-not-just-WHAT, directive verbs, explicit output format.
- **`profile.md` + `hooks.md`** voice scaffolding ([[alfiejcarter-linkedin-claude-stack]]) — same per-project behavioral-contract pattern, applied to writing voice instead of coding behavior.
- **Tom Crawshaw's Blueprint** ([[tomcrawshaw-claude-code-blueprint]]) — frames CLAUDE.md as "the trick that makes Claude predictable, not chaotic." Independent practitioner echo.
- **Zephyr 7-setups taxonomy ([[zephyr-7-claude-setups-2026-05-15]], May 2026)** — names CLAUDE.md as setup #1 of seven Claude-fluency primitives; *"the single file that tells Claude how to behave for everything inside that project. Voice. Audience. Constraints. Output rules. What to never do. The highest-return 30 minutes you'll spend in Claude this year."* Practitioner-side validation in onboarding-pedagogy register.
- **Deutscher Investor Strategy Architect ([[milesdeutscher-claude-personal-cfo-2026-05-14]], May 2026)** — domain-specific extension beyond code-task contexts. `instructions.md` paired with `memory.md` (running change log) + `investor-one-pager.md` (canonical mindset doc) + `/financials/` reference folder. The structured 7-phase discovery interview prompt operationalizes the *behavioral-contract* discipline for behavioral-discovery agents: explicit phase-gating ("never produce the final document until all seven phases are genuinely complete"), explicit refuse-conditions ("refuse generic answers, name contradictions directly"), explicit output specification. First wiki capture of the pattern applied to personal-finance / personal-OS rather than code generation.
- **sairahul1's "job description not vibe" ([[sairahul1-solo-founder-13-agent-playbook-2026-05-15]], May 2026)** — the same anti-pattern at the agent-design level: *"Every agent has a job description, not a vibe. 'Pulls 10 trending posts from X every morning at 8am, drafts 3 replies in my voice, posts the highest-scoring one if I approve.' That is a job description. 'Help with content' is a vibe. Vibes don't survive the weekend."* Cross-level confirmation: CLAUDE.md addresses under-specification at the file level; sairahul1's framing addresses it at the agent level.
- **CLAUDE.md as prerequisite for unattended-execution ([[claude-code-goal-command-2026-05]], Luca Capone, May 2026)** — *"/goal only works well when your CLAUDE.md is solid. Without project context, it wanders. With it, feels like a junior dev who actually read the docs."* This is the **inverse-direction reinforcement** of the pattern: until now, CLAUDE.md has been framed as a per-session quality improvement; Luca's comment makes it a **prerequisite for unattended-execution capability**. As Claude Code's long-running primitives ([[claude-code-goal-command-2026-05|`/goal` / `/loop` / `/schedule` / stop hooks / auto mode]]) move from optional to default, the dependency relationship flips: CLAUDE.md is not what improves Claude's behavior in a single session, it's **what makes longer-horizon operation tractable at all**.
- **Stulberg Team OS ([[stahlberg-team-os-aakash-2026-05]], May 2026)** — independent **1,500-hour practitioner validation** of the minimal-CLAUDE.md + progressive-sub-loading framing.
- **Hassid anti-style-instruction framing ([[hassid-cowork-setup-2026-04-07]], 2026-04-07 surfaced May 25)** — *"80% of your file should be what you're NOT."* First wiki-captured formalization of **anti-style-instruction as the load-bearing CLAUDE.md / about-me content discipline**. Extends Mnilax's "fail loud" rule from output-behavior to file-content design: name what Claude must avoid, not just what it must do. Karolis Balsiukevicius comment cross-confirms: *"Telling Claude who I am matters less than telling it who I'm not. My about-me file is mostly rules about what to avoid. Works way better."* Pairs with Hassid's *"Say 'Does NOT sound like' to kill the AI voice"* in-prompt anti-style move. Fifth+ independent practitioner-validation surface for the file-based behavioral-contract discipline (Stulberg + Zephyr + Capone + ShilpaMitra + Hassid). **The CLAUDE.md behavioral-contract pattern is now community-canonical across at least 5 independent practitioner surfaces.** Stulberg's deliberately lean CLAUDE.md contains a doc-index, team-roster + Slack handles, and key Slack-channel purposes — nothing else. Sub-CLAUDE.mds in function-specific folders load progressively as natural-language queries reference them. *"You don't want very much in your CLAUDE.md file. Claude MD should be very, very, very lean, especially in a team repository."* Confirms the [[mnilax-claude-md-12-rules-2026-05-09|200-line ceiling]] discipline from a team-repo angle independent of the Karpathy → Forrest Chang → Mnilax single-developer lineage.
- **arps18 "Claude Code as a daily driver" (2026-05-27)** — practitioner integration guide covering CLAUDE.md, skills, subagents, plugins, MCPs in a real dev workflow. **Sixth+ independent practitioner-validation surface** for the CLAUDE.md pattern (Stulberg + Zephyr + Capone + ShilpaMitra + Hassid + arps18). The pattern continues compounding — each new practitioner-source treats CLAUDE.md as the *foundation* on which skills / subagents / plugins / MCPs are layered, not as a coequal primitive. — [[dailybrief-roundup-2026-05-27]]
- **Heeki Park spec-driven development (2026-02-28, captured 2026-05-28)** — AWS solutions architect's substantive walkthrough of a real Bedrock AgentCore build (MCP server + Gateway + interceptor). **Seventh+ independent practitioner-validation surface** (Stulberg + Zephyr + Capone + ShilpaMitra + Hassid + arps18 + Park). New framing: **CLAUDE.md as a continuously-evolved-during-project artifact, not authored once at startup** — *"I frequently took learnings from the project and integrated them into my `CLAUDE.md` steering document and even ended up creating a `SKILL.md` at the end of the project."* Pairs structurally with Park's own *spec-first vs spec-once* anti-pattern observation: **the equivalent CLAUDE.md anti-pattern is "CLAUDE.md-once"** (write it at project start and forget it). Adds **SKILL.md as project-emergent artifact** to the pattern surface. — [[heeki-spec-driven-development-2026-02-28]]

### AGENTS.md: vendor-neutral sibling pattern (SQLite adoption, 2026-05-27)

A namespace-divergent sibling pattern has emerged: **AGENTS.md** is the vendor-neutral version of CLAUDE.md — same shape (a steering document the agent reads on startup), no Claude-specific framing.

- **[[sqlite-agents-md-2026-05-27|SQLite adopts AGENTS.md]] (2026-05-27, Willison surfacing)** — **first wiki-captured AGENTS.md adoption by a tier-1 OSS project.** SQLite is one of the most widely-deployed pieces of software on Earth and its maintainer rigor is famously high; an adoption here is a stronger signal of *practitioner-normalization* than adoption by any single fast-moving startup.
- **The namespace-divergence open question**: does the community standardize on AGENTS.md (vendor-neutral) or stratify (CLAUDE.md for Claude-specific behavioral contracts, AGENTS.md for cross-vendor guardrails)?
  - **Evidence for vendor-neutral path**: SQLite AGENTS.md adoption; the [[dailybrief-roundup-2026-05-27|PolyArch/humanize RLCR plugin]] (Claude implements + Codex reviews) operates cross-vendor.
  - **Evidence for stratification path**: [[dac|bruin-data/dac]]'s SKILL.md ships for **both** Claude Code and Codex (one project supports multiple steering files); Heeki Park uses both CLAUDE.md *and* a project-emergent SKILL.md in the same project.
- **Practitioner-content implication**: AGENTS.md is the *write-side* mechanism (prevent bad AI contributions before they happen); the [[dailybrief-roundup-2026-05-28|curl 4-5× YoY security-report flood]] is the *read-side* mechanism (cope with bad AI submissions). Both are AI-flood-coping patterns at the OSS-maintenance layer.

The CLAUDE.md pattern is now part of a two-pattern family (CLAUDE.md + AGENTS.md). Pattern-watch: do the next ~10 tier-1 OSS projects (curl, ffmpeg, Python stdlib, OpenSSL) adopt AGENTS.md? Do mixed-vendor projects ship both files? Does Anthropic adopt or comment on AGENTS.md as a sibling pattern?

## Key Papers / Posts

- [[mnilax-claude-md-12-rules-2026-05-09]] — May 9 2026; 12-rule expansion, mistake-rate numbers, "what didn't work" negative results, mental-model framing.
- [[karpathy-vibe-coding-agentic-engineering]] — Karpathy's broader [[agentic-engineering]] framing; CLAUDE.md is one of the per-project levers in the discipline.
- [[forrest-chang]] — original 4-rule template author.

## Related Concepts

- [[agentic-engineering]] — CLAUDE.md is a primary tool of the discipline.
- [[llm-wiki-pattern]] — sibling pattern at the knowledge-corpus level.
- [[claude-code]] — the host tool the file configures.
- [[claude-md-pattern]] vs. CLAUDE.md *file*: the file is the artifact; the pattern is the *behavioral-contract* discipline applied to writing the file.
