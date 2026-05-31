---
name: zodchii
type: person
affiliation: independent; Telegram channel `t.me/zodchixquant`
signal_sources: [twitter, telegram]
last_updated: 2026-05-31
---

## Who They Are

@zodchii is an independent practitioner-content creator publishing substantive Opus-4.8-and-Claude-Code operational walkthroughs on X (X handle `@zodchiii`, triple-i) and the Telegram channel `t.me/zodchixquant`. **Crosses the single-source-defer threshold** with 2+ wiki sources within 48 hours (May 29 + May 30). High operational specificity — both wiki-captured posts ship **copy-paste-ready code / config** for Claude Code primitives. **Distinctive practitioner-content register**: dense concrete-numbers walkthroughs with explicit cost-allocation framing and pre-written config artifacts (vs the more discursive frameworks-and-stories of [[nate-herk|Nate Herk]] or the high-pedagogical-density of [[ruben-hassid|Hassid]]).

## Their Current Focus

- **Opus 4.8 cost-optimization discipline** — per-task model+effort routing matrix for ~50% monthly savings ([[zodchii-opus-4-8-setup-guide-2026-05-29]])
- **4-agent pipeline architecture** for autonomous feature-shipping — Planner / Coder / Tester / Reviewer with handoff-files + orchestrator slash command ([[zodchii-4-agent-pipeline-2026-05-30]])
- **Teamly product surface** — managed cloud hosting for AI agents at $29/mo for 5 agents (paid promotion / partnership context in the pipeline post)

## Notable Takes

- **2026-05-29 — *"Effort control is the highest-value feature in this release. Not dynamic workflows, not fast mode."*** ([[zodchii-opus-4-8-setup-guide-2026-05-29]]): operator-side routing-discipline that maps each task to cheapest sufficient model+effort cuts monthly bill in half. **First wiki-captured practitioner-content register routing-matrix answer to the [[ai-roi-gap]].**
- **2026-05-29 — Resolves prior verification-pending Opus 4.8 metrics**: 88.6% on SWE-bench (vs 87.6% on 4.7); 4× fewer unflagged code bugs; 0% uncritical-flawed-result honesty; fast mode 2.5× speed at 3× cheaper pricing; 1M context window unchanged.
- **2026-05-29 — `--max-budget-usd <amount>` CLI flag**: first wiki-captured operator-side hard-cap-on-spend primitive for Claude Code.
- **2026-05-29 — `CLAUDE_CODE_SUBAGENT_MODEL` env var**: route subagents to cheaper Sonnet while main on Opus — dramatic cost-profile change at 100s-of-subagents scale (especially relevant after [[nateherk-dynamic-workflows-2026-05-30|Nate Herk's 41-Haiku case study]] showed 5M tokens for one workflow run).
- **2026-05-30 — 4-agent pipeline canonical schema**: `.claude/agents/<role>.md` (name+description+tools+model frontmatter) + `.claude/commands/<name>.md` orchestrator; **first wiki-captured complete copy-paste-ready agent-and-pipeline file layout**. Pairs with [[nate-herk|Nate Herk's Ladder framework]] (zodchii's pipeline = Rung 4 instantiation).
- **2026-05-30 — Model-routing within the pipeline**: Opus for Planner + Reviewer (quality-gates); Sonnet for Coder + Tester (cost-balanced execution). Generalizes the [[zodchii-opus-4-8-setup-guide-2026-05-29|prior-day single-agent routing matrix]] to multi-agent pipelines.
- **2026-05-30 — Read-only-tools as architectural pattern**: *"Read-only tools mean the Reviewer can't paper over problems by editing, it can only judge."* Same operator-side principle as [[nate-herk|Nate Herk's instructions-vs-capabilities lesson]] — constrain by *what the agent can do*, not *what you ask it not to do*. **Two practitioner surfaces, same week, same operator-side principle.**

## Where to Follow

- X: [@zodchiii](https://x.com/zodchiii) (triple-i)
- Telegram: [`t.me/zodchixquant`](https://t.me/zodchixquant) — *"daily notes on AI, finance, and vibe coding"*

## Resources

- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — Opus 4.8 setup guide; 5-level effort menu; --max-budget-usd; env vars; settings.json template; routing matrix → ~50% monthly savings
- [[zodchii-4-agent-pipeline-2026-05-30]] — 4-agent pipeline (Planner/Coder/Tester/Reviewer) + canonical `.claude/agents/*.md` layout + Teamly product placement
- [[claude-md-pattern]] — pipeline + agent definitions added as 9th+ practitioner-validation surface
- [[ai-roi-gap]] — first wiki-captured practitioner-content routing-discipline answer to the gap
