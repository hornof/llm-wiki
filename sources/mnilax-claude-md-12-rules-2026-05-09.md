---
title: "Karpathy's 4 CLAUDE.md rules cut Claude mistakes from 41% to 11%. After 30 codebases, I added 8 more"
type: source
medium: twitter-thread
url: https://x.com/Mnilax/status/2053116311132155938
ingested: 2026-05-10
---

## Summary

Long-form X post by **@Mnilax** (May 9 2026) that frames Forrest Chang's 4-rule CLAUDE.md template — the fastest-growing single-file repo of 2026 (~120,000 GitHub stars) — as the *floor* of practical CLAUDE.md design, not the ceiling. The author tested the original 4-rule template across **30 codebases over 6 weeks**, then added 8 more rules to address failure modes Karpathy's January 2026 thread didn't anticipate (multi-step agent loops, hook cascades, skill conflicts, multi-codebase consistency, tests-as-success-theater, silent-success failures). End result: a 12-rule template the author claims drops mistake rate from **41% (no CLAUDE.md) → 11% (Karpathy's 4) → 3% (full 12)**, with negligible compliance overhead (78% → 76% applied-when-applicable).

## Key Claims / Takeaways

### Origin story
- **Late January 2026**: Karpathy posts an X thread complaining about how Claude writes code. Three failure modes named: (1) silent wrong assumptions, (2) over-complication, (3) "orthogonal damage" to code that shouldn't have been touched.
- **Forrest Chang** packages the complaints into 4 behavioral rules in a single CLAUDE.md file, drops it on GitHub. Repo metrics quoted: **5,828 stars first day, 60,000 bookmarks in two weeks, 120,000 stars by May 2026** — described as the "fastest-growing single-file repo of 2026."
- Forrest's repo URL: `github.com/forrestchang/andrej-karpathy-skills` (cited in install instructions; not independently verified in this ingest).

### CLAUDE.md as advisory: the 200-line ceiling
Quoted as Anthropic-official: **"CLAUDE.md is advisory. Claude follows it about 80% of the time. Past 200 lines, compliance drops sharply because important rules get buried in the noise."** This number is presented as the constraint that makes minimal templates beat exhaustive ones. The author tested up to 18 rules and saw compliance drop from **76% → 52% past 14 rules**.

### The original 4 rules (Forrest Chang / Karpathy distillation)
1. **Think Before Coding** — no silent assumptions; surface tradeoffs; ask before guessing.
2. **Simplicity First** — minimum code that solves the problem; no speculative features.
3. **Surgical Changes** — touch only what you must; don't refactor what isn't broken; match existing style.
4. **Goal-Driven Execution** — define success criteria; loop until verified; let Claude iterate against the criteria, not a step list.

The author claims these 4 close ~40% of failure modes in unsupervised Claude Code sessions; the remaining ~60% is what the additional 8 rules target.

### The 8 added rules
5. **Use the model only for judgment calls** — classification, drafting, summarization, extraction. Do NOT use for routing, retries, deterministic transforms.
6. **Token budgets are not advisory** — per-task 4,000 / per-session 30,000; surface the breach, don't silently overrun.
7. **Surface conflicts, don't average them** — when two patterns contradict, pick one (more recent / more tested), explain why, flag the other for cleanup.
8. **Read before you write** — read exports, immediate callers, shared utilities before adding code; "looks orthogonal" is the most dangerous phrase in the codebase.
9. **Tests verify intent, not just behavior** — every test must encode WHY behavior matters. A test that can't fail when business logic changes is wrong.
10. **Checkpoint after every significant step** — summarize what was done / verified / left after each step in a multi-step task; don't continue from a state you can't describe back.
11. **Match the codebase's conventions, even if you disagree** — conformance > taste inside the codebase; surface a complaint, don't fork silently.
12. **Fail loud** — "completed" is wrong if anything was skipped silently; default to surfacing uncertainty.

### Numerical claims (50-task panel × 30 codebases × 6 weeks)
| Configuration | Mistake rate | Compliance |
|---|---|---|
| No CLAUDE.md | 41% | — |
| Karpathy's 4 rules | 11% | 78% |
| 12-rule template | 3% | 76% |

The interesting result the author highlights: **going from 4 → 12 rules added almost no compliance overhead but cut the mistake rate by another 8 points** — i.e., the new rules cover failure modes the original 4 didn't address; they don't compete for the same attention budget.

### Where Karpathy's 4 silently break
- **Long-running agent tasks** — original rules target the moment Claude is writing code; silent on multi-step pipeline drift.
- **Multi-codebase consistency** — "match existing style" assumes one style; fails on monorepo with 12 services.
- **Test quality** — Goal-Driven Execution treats "tests pass" as success; doesn't require tests to be meaningful.
- **Production vs. prototype** — Simplicity First overfires on prototypes that legitimately need 100 lines of speculative scaffolding.

### What didn't work (negative results)
- Rules from Reddit/X — mostly restatements or domain-specific (e.g., "always use Tailwind"); cut.
- More than 12 rules — compliance drops past 14; the 200-line ceiling is real.
- Tooling-dependent rules ("always use eslint") — fail silently when tool absent; replaced with capability-agnostic phrasings.
- Examples instead of rules — examples cost ~10× the context tokens of rules and Claude over-fits to them.
- Soft language ("be careful," "think hard," "really focus") — compliance ~30%; replaced with concrete imperatives.
- Identity prompts ("be a senior engineer") — Claude already thinks it's senior; the gap is between thinking and doing, and imperatives close it where identity prompts don't.

### Mental model framing
> "CLAUDE.md is not a wishlist. It's a **behavioral contract** that closes specific failure modes you've observed. Every rule should answer: what mistake does this prevent?"

The author's recommended use is *not* to copy all 12 — it's to **read the 12, keep the ones that map to mistakes you've actually made, drop the rest.** Quote: "A 6-rule CLAUDE.md tuned to your real failure modes beats a 12-rule one with 6 rules you'll never need."

## Pages Updated

- [[claude-md-pattern]] (new — concept page for CLAUDE.md as a behavioral-contract pattern; captures 200-line ceiling, advisory nature, and the Forrest Chang / 12-rule lineage)
- [[forrest-chang]] (new — author of the original 4-rule template; 120K-star single-file repo)
- [[andrej-karpathy]] (updated — January 2026 Claude-code-writing complaint thread is the proximate cause of the CLAUDE.md template ecosystem)
- [[claude-code]] (updated — CLAUDE.md compliance numbers 80%/200-line ceiling added to Key Concepts; 12-rule expansion noted as community-evolved successor to Karpathy's 4)

## Caveats

- Single practitioner's claim (n=30 codebases, 6 weeks). The 41% → 3% headline number is uncorroborated; the 50-task panel methodology is described in prose, not in a release artifact this ingest can verify.
- The "Anthropic-official" 80% / 200-line claim is quoted in the post but not independently verified against current Anthropic docs. Treat as plausible practitioner consensus rather than an Anthropic-published number until verified.
- @Mnilax's broader track record is unknown to this wiki; this is a single high-effort post, not a sustained signal stream. No `people/mnilax` page created — would be thin.
- Forrest Chang's repo and its star count are claimed but not yet verified by direct observation in this ingest. Star numbers in particular tend to be approximated when they enter X posts. The trend (top single-file repo of 2026, large enough to be widely linked) is plausible based on parallel community signals.
- The post ends with a Telegram channel CTA, suggesting some content-marketing intent. The substance is independently useful; treat the framing as enthusiastic-practitioner rather than peer-reviewed.
