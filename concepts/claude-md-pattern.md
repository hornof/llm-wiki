---
name: CLAUDE.md Pattern
type: concept
maturity: emerging
last_updated: 2026-05-10
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

## Key Papers / Posts

- [[mnilax-claude-md-12-rules-2026-05-09]] — May 9 2026; 12-rule expansion, mistake-rate numbers, "what didn't work" negative results, mental-model framing.
- [[karpathy-vibe-coding-agentic-engineering]] — Karpathy's broader [[agentic-engineering]] framing; CLAUDE.md is one of the per-project levers in the discipline.
- [[forrest-chang]] — original 4-rule template author.

## Related Concepts

- [[agentic-engineering]] — CLAUDE.md is a primary tool of the discipline.
- [[llm-wiki-pattern]] — sibling pattern at the knowledge-corpus level.
- [[claude-code]] — the host tool the file configures.
- [[claude-md-pattern]] vs. CLAUDE.md *file*: the file is the artifact; the pattern is the *behavioral-contract* discipline applied to writing the file.
