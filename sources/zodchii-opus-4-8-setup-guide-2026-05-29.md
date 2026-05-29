---
title: "zodchii: The Claude Opus 4.8 Setup Guide — Maximum Quality for Minimum Cost"
type: source
medium: twitter-thread
url: https://x.com/zodchiii/status/2060293472091771114
ingested: 2026-05-29
---

## Summary

@zodchii (X / Telegram-channel `t.me/zodchixquant`) publishes a **comprehensive Opus 4.8 setup guide** (2026-05-29) with concrete numbers, env-var configuration, settings.json template, effort-control routing matrix, fast-mode pricing comparison, and cost-savings projection (~50% reduction with proper routing). **First wiki-captured practitioner-content register Opus 4.8 walkthrough with operator-level operational specifics** (effort menu, env vars, hooks). **Resolves several verification-pending items** from yesterday's launch capture and **adds new concrete numbers** that didn't appear in either the [[claude-opus-4-8-dynamic-workflows-2026-05-28|Digg secondary]] or the [[anthropic-dynamic-workflows-primary-2026-05-28|Anthropic primary]].

## Key Claims / Takeaways

### Concrete numbers that resolve / extend prior captures

**Resolves prior verification-pending items**:

| Field | Prior wiki state | zodchii datum |
|---|---|---|
| Context window | "not anchored" | **1,000,000 tokens** (unchanged from 4.7) |
| Max output | not captured | **128,000 tokens** |
| SWE-bench | "69.2% on SWE-bench Pro" (Anthropic claim, Digg) | **88.6% on SWE-bench** (up from 87.6%) |
| Pricing | "same as 4.7" | **$5 / $25 per million tokens** (in/out) |
| Honesty improvement | "improve model honesty" (qualitative) | **0% uncritically reporting flawed results** + **4× fewer unflagged code bugs vs 4.7** |
| Fast mode | not captured | **2.5× speed, $10 / $50 per million tokens** |
| Fast mode price drop | not captured | **3× cheaper than prior fast mode** ($30 / $150 → $10 / $50) |
| Dynamic Workflows scale | "tens to hundreds of parallel subagents" (Anthropic primary) | **Up to 1,000 agents per run** (zodchii framing) |
| Workflow cost | "substantially more tokens" (Anthropic primary) | **100 subagents ≈ $50-200** (zodchii operational range) |

> [!note] SWE-bench vs SWE-bench Pro disambiguation
> The "69.2% on SWE-bench Pro" figure (from yesterday's Digg-derived capture) and "88.6% on SWE-bench" (this source) are **two different benchmarks**, not contradictory:
> - **SWE-bench**: standard benchmark; Opus 4.8 scores 88.6% (up from 4.7's 87.6%)
> - **SWE-bench Pro**: harder variant; Opus 4.8 scores 69.2% per the Anthropic-side bundle
> 
> Both are valid; track separately.

### Effort control: 5 levels + slash commands

New effort-menu primitive shipped with Opus 4.8:

| Level | Description | Slash command |
|---|---|---|
| **Low** | Fast, simple tasks, lowest token usage | `/effort low` |
| **Medium** | Everyday coding, balanced | `/effort medium` |
| **High** (default) | Solid reasoning — equivalent to what Opus 4.7 always used | `/effort high` |
| **Max** | Deepest reasoning, highest token usage | `/effort max` |
| **Ultracode** | Max reasoning + automatic Dynamic Workflows orchestration | `/effort ultracode` |

**`ultracode` resolves the [[anthropic-dynamic-workflows-primary-2026-05-28|Anthropic primary]] description** of the setting as *"effort menu → xhigh + let Claude decide when to fan out to a workflow."* The naming convention is `low → medium → high → max → ultracode` — `xhigh` from yesterday's capture appears to have been an interim Anthropic-side name; the shipped name is `max` for the standalone level and `ultracode` for the *max + workflow-orchestration* mode.

**UI variant**: claude.ai now has a **slider** in the UI (Low at one end, Max at the other).

### Cost savings claim (routing matrix)

zodchii's projection for monthly Claude spend:

| State | Monthly spend (heavy usage) |
|---|---|
| Before (everything on Opus High, standard) | **$400-600/mo** |
| After (correctly routed by task type) | **~$205/mo** |
| **Savings** | **~50%** |

Routing breakdown for the ~$205/mo state:

| Tier | Task type | Monthly spend |
|---|---|---|
| Haiku Low | Quick questions | $5/mo |
| Sonnet Medium | Daily tasks / tests / formatting | $40/mo |
| Opus High | Daily coding / code review / complex work | $80/mo |
| Opus Fast | Large refactors (speed > depth) | $30/mo |
| Dynamic | Big audits / migrations / occasional | $50/mo |

**Cross-cut with [[ai-roi-gap]]**: this is **the first wiki-captured practitioner-content routing-discipline answer to the ROI gap** — *not* a vendor-side architectural change, but an operator-side cost-allocation discipline that maps each task to the cheapest sufficient model+effort. **The discipline is the hidden capability.** Pairs with [[claude-md-pattern|CLAUDE.md pattern]] as the *file-based behavioral-contract* discipline; effort-routing is the *per-task model-allocation* discipline.

### Environment variables (new)

```bash
export CLAUDE_CODE_DEFAULT_EFFORT=high
export CLAUDE_CODE_DISABLE_ADAPTIVE_THINKING=1
export CLAUDE_CODE_SUBAGENT_MODEL="claude-sonnet-4-5-20250929"
export ANTHROPIC_MODEL="claude-opus-4-8"
```

**`CLAUDE_CODE_SUBAGENT_MODEL`** is the load-bearing new env var — lets the operator set Sonnet (cheaper) as the subagent model while the main agent runs on Opus 4.8. Under Dynamic Workflows with up to 1,000 subagents, this changes the cost profile dramatically. **Not yet captured in Anthropic primary or Anthropic Founder's Playbook.**

### Settings.json template

zodchii ships a full `settings.json` with:
- **Permissions allowlist**: Read / Glob / Grep / LS / Edit / MultiEdit / Write-scoped-to-subdirs / Bash-scoped-to-npm-prettier-eslint-tsc-git
- **Permissions denylist**: `.env*`, `.ssh/**`, `.aws/**`, `rm -rf *`, `sudo *`, `git push *`
- **`defaultMode: "acceptEdits"`**
- **PostToolUse hooks**: auto-`prettier --write` + `tsc --noEmit` on `.ts` file writes
- **Stop hooks**: `npm test 2>&1 | tail -10`

**Pairs with [[claude-md-pattern]] discipline**: settings.json + hooks operationalize the same behavioral-contract discipline at the *runtime* layer that CLAUDE.md operates at the *instruction* layer.

### Budget-cap CLI flag (new operator-side primitive)

```bash
claude -p "audit the entire codebase" --max-budget-usd 50.00
```

**First wiki-captured `--max-budget-usd` CLI flag for Claude Code.** Operator-side cost-forecasting now has a per-invocation hard cap. **Direct answer to the ROI-gap exposure point** — pairs with the [[anthropic-dynamic-workflows-primary-2026-05-28|Anthropic primary's]] *"substantially more tokens"* warning. Anthropic flags the cost; this flag lets the operator cap it.

### The load-bearing insight (zodchii's framing)

> *"Effort control is the highest-value feature in this release. Not dynamic workflows, not fast mode. Effort control. Running Low effort on 60% of your prompts and Max on the 10% that actually need deep reasoning is the discipline that cuts your monthly bill in half without touching output quality on what matters. Most people will leave everything on High and never touch the slider. The ones who learn to route effort per task will get the same results at half the cost."*

**This is the practitioner-content register version of the [[ai-roi-gap]] thesis**: capability is necessary-but-not-sufficient; *routing discipline* is the load-bearing operator-side answer.

### What's notably absent

- **Where the 88.6% SWE-bench number comes from** — Anthropic-published? zodchii-tested? Not specified
- **Whether the $5-$50 routing breakdown is zodchii's own usage data** or a hypothetical
- **`/insights` command** — referenced by [[nateherk-opus-4-8-aios-2026-05-29|nateherk]] but not by zodchii (different commands surfaced by different practitioners)
- **Whether `ultracode` is Pro-tier accessible** (Anthropic primary scoped Dynamic Workflows to Max/Team/Enterprise)

## Pages Updated

- [[claude-opus-4-8]] — concrete numbers (88.6% SWE-bench, 4× fewer code bugs, 0% honesty, context window, max output, fast mode pricing) + effort levels + cost-warning quantification
- [[claude-code]] — effort menu + `/effort` slash commands + `--max-budget-usd` CLI flag + env vars added
- [[claude-md-pattern]] — settings.json + hooks operationalization noted as runtime-layer complement to file-layer CLAUDE.md
- [[ai-roi-gap]] — first wiki-captured practitioner-content routing-discipline answer to the gap; ~50% savings claim
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — "up to 1,000 agents per run" + "100 subagents ≈ $50-200" added as practitioner-extension of "tens to hundreds" Anthropic framing

Verification-pending: source of 88.6% SWE-bench number; whether routing-breakdown is zodchii's own data; whether `ultracode` is Pro-accessible; whether the 4× / 0% honesty numbers are Anthropic-published or zodchii's own evaluation.

## Adjacent sources

- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — Digg-derived launch bundle (pt1 ingest)
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — Anthropic primary on Dynamic Workflows (pt2 ingest)
- [[nateherk-opus-4-8-aios-2026-05-29]] — same-day practitioner-content companion (Four C's framework + AI OS framing)
- [[claude-md-pattern]] — file-layer behavioral-contract discipline that settings.json + hooks operationalize at runtime
