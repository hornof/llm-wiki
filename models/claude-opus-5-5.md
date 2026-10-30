---
name: Claude Opus 5.5
type: model
provider: Anthropic
status: available
last_updated: 2026-10-29
---

## What It Is

[[anthropic|Anthropic's]] current flagship, launched **2026-09-22** — the same day as OpenAI's GPT-6 Sol and Luna, **with both labs cutting prices 40–50%** ([[dailybrief-roundup-2026-09-23]], via [[simon-willison|Willison]]).

**Paged 2026-10-08 on a second substantive surface**, per the standing instruction left on [[claude-opus-5]]. The launch note carried no specs; these arrive via a third-party course relaying Anthropic's Opus 5.5 prompting guide ([[agent-teams-opus-55-course-2026-10-07]]) — **the guide itself has not been fetched.**

## Strengths & Weaknesses

**Claimed, all relayed secondhand:**

- **66.4% on Terminal-Bench 4.0**, against **55.8% for the far larger [[claude-fable-5|Claude Fable 5.1]]**. **If that holds it is the more interesting number on this page** — a smaller model beating the larger one on an agentic-terminal benchmark is the harness/capability story the wiki tracks, measured inside one vendor's own lineup.
- **~40% cheaper than [[claude-opus-5|Opus 5]]** on typical workloads. Consistent with the 40–50% launch-day cut, and with the [[anthropic-automating-eval-design-hillclimbing-2026-09-28|hillclimbing result]] that *"input and output tokens cost 20% less than on Opus 4.8, and **cache reads cost 60% less**."*
- **Effort as a per-role dial**, and a documented **elapsed-time budget** for agent teams.
- **One early tester reportedly completed a 680,000-line code migration in under a day.** **A line count is not a result** — no language, no verification, no defect rate, and "migration" covers everything from a mechanical codemod to a rewrite.

**Not captured:** context window, pricing table, modalities, availability tiers, or any independent benchmark. **No primary fetched.**

## When to Use It

**The one documented behaviour worth building around** is the team-pacing result: *"when Anthropic gave a team of agents an elapsed-time budget, the team kept answer quality comparable to a single agent's while finishing considerably sooner"* ([[agent-teams-opus-55-course-2026-10-07]]).

**That cuts against the wiki's own cost evidence and the tension is unresolved.** Anthropic's three-agent harness cost **20× more** than the unharnessed run for a better result ([[undefinedki-how-to-design-an-agent-harness-2026-08-15]]). *Same quality, sooner* would mean coordination overhead is payable in wall-clock rather than quality — **a different trade from the one the harness record describes.** Neither claim has been checked against the other.

Practitioner use in the wild: [[garrytan-capy-harness-4x-2026-09-23|Tan running Capy on Opus 5.5 PRs]], and the [[raw-batch-roundup-2026-10-02|`/advisor` tree]] putting Opus 5.5 on the main session at high effort with Fable 5.1 as the reviewer.

## Community Sentiment
- **2026-10-29 — not enough for Spawn's autonomy** ([[willison-spawn-autonomous-game-dev-2026-10-29]]): Spawn's team says Opus 5.5 *"doesn't quite hack it"* for their fully autonomous setup, where Fable 5.1 does. The day before, Willison had found Opus 5.5 good at game design ([[willison-vibe-game-development-2026-10-28]]). Those are different jobs.

**Thin.** The launch was overshadowed by its own price cut and by GPT-6 Sol landing the same day; the wiki's 09-23 entry read the simultaneity as *"the first frontier-on-frontier price war"* and folded the pricing rather than the model. **Six weeks on there is still no independent evaluation in the record.**

**2026-10-27, Latent Space with the Claude Platform leads** ([[latent-space-opus-5-5-brain-hands-2026-10-27]]): still no independent evaluation. Two platform points are useful. Preserving thinking blocks across turns, a guard against distillation, can break existing harnesses. And Managed Agents keeps the session and harness apart from the code sandbox, so a crashed sandbox doesn't end the session and no credential sits where generated code runs. Latent Space calls Opus 5.5 the *"generally accepted #1"* LLM. That's the host's view, not a measurement.

**2026-10-28, the first independent hands-on comparison** ([[willison-vibe-game-development-2026-10-28]]). [[simon-willison]] vibe-coded four browser games with Opus 5.5 and enjoys playing them. Their claim is about game design: the model makes games that are fun. Given the same prompts, GPT-6 Pro built an RPG that *"looks great"* but doesn't play *"nearly as well"*. Their read is that GPT-6 Astra's *"sense of fun doesn’t match that of Opus 5.5"*. **One practitioner's informal test, not a benchmark**, but it's the first named, non-vendor assessment on this page. Step 5a: the line above saying there was still no independent evaluation after six weeks is now partly answered, qualitatively only.

## Resources

- [[dailybrief-roundup-2026-09-23]] — launch, alongside GPT-6 Sol/Luna and the 40–50% cuts
- [[agent-teams-opus-55-course-2026-10-07]] — the specs above, and the team-pacing result
- [[claude-opus-5]] — predecessor; [[claude-sonnet-5]] — the 5.5 point release on that line
- [[ai-margin-collapse]] — the price war this shipped into

## Verification-pending

**Anthropic's Opus 5.5 prompting guide** — the source of every number on this page. Also: the Terminal-Bench 4.0 comparison against Fable 5.1 (**the claim most worth confirming**), the pricing table, the context window, and anything at all about the 680,000-line migration beyond the line count.
