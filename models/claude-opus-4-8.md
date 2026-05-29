---
name: Claude Opus 4.8
type: model
provider: Anthropic
status: available
last_updated: 2026-05-28
---

## What It Is

Claude Opus 4.8 is the May 28 2026 Opus refresh from [[anthropic|Anthropic]] — launched alongside the [[anthropic-series-h-65b-965b-2026-05-28|Series H $65B/$965B raise]] as a same-day capability-and-capital double-event. **Succeeds [[claude-opus-4-7|Opus 4.7]] as the recommended model for [[claude-code|Claude Code]]** ([[claude-opus-4-8-dynamic-workflows-2026-05-28|launch source]]). Anthropic claims **69.2% on SWE-bench Pro**, outperforming GPT-5.5 and Gemini 3.1 Pro on senior-level engineering and writing tasks. Same pricing as Opus 4.7 per Digg framing — *"improve model honesty and flag programming errors at the same price."* Bundled with **Dynamic Workflows** preview for parallel subagents — a new orchestration primitive for multi-agent code migration at scale.

Sits alongside [[claude-mythos]] (Anthropic's preview line); positioning between Opus and Mythos still not publicly clarified.

## Strengths & Weaknesses

### Benchmark + capability numbers (Anthropic + practitioner-surfaced)

| Metric | Value | Source |
|---|---|---|
| **SWE-bench** | **88.6%** (up from 87.6% on Opus 4.7) | [[zodchii-opus-4-8-setup-guide-2026-05-29\|zodchii setup guide]] |
| **SWE-bench Pro** | **69.2%** (beats GPT-5.5 + Gemini 3.1 Pro) | Anthropic-claim via [[claude-opus-4-8-dynamic-workflows-2026-05-28\|Digg secondary]] |
| **Code flaws** | **4× fewer unflagged bugs** than Opus 4.7 | zodchii |
| **Honesty** | **0% uncritically reporting flawed results** | zodchii |
| **Context window** | **1,000,000 tokens** (unchanged from 4.7) | zodchii |
| **Max output** | **128,000 tokens** | zodchii |
| **Pricing (standard)** | **$5 / $25 per million tokens** in/out | zodchii |
| **Fast mode** | **2.5× speed, $10 / $50 per million tokens** (3× cheaper than prior fast mode $30 / $150) | zodchii |
| **Recommended Claude Code model** | yes (replaces Opus 4.7) | Anthropic launch |

**SWE-bench vs SWE-bench Pro disambiguation**: these are two different benchmarks. SWE-bench is the standard / older harness (88.6%); SWE-bench Pro is the harder variant introduced more recently (69.2%). Track separately.

### Practitioner-experience qualitative comparison ([[nate-herk|Nate Herk]], May 29 2026)

> *"I liked Opus 4.6 more than 4.7. 4.7 had a bit of an attitude. It would wander outside the scope of what you asked it to do, sometimes burn extra tokens, and once in a while it would lie to you. 4.8 feels closer to 4.6 again, with real honesty improvements in the docs to back it up."*

**Cross-confirmation**: practitioner-experience matches the 0% uncritical-flawed-result benchmark claim. Opus 4.8's improvements are felt at the daily-usage level, not just benchmark-paper level.

### Caveats

- **88.6% SWE-bench source**: zodchii framing; whether Anthropic-published or zodchii-tested unclear.
- **0% honesty + 4× flaws**: also via zodchii; Anthropic primary not deeply fetched.
- All benchmark numbers practitioner-surfaced; independent third-party verification (LMSYS, SWE-bench leaderboard direct submissions) not yet captured.
- **Bedrock / Vertex availability**: Dynamic Workflows confirmed on Bedrock + Vertex + Foundry + Anthropic API ([[anthropic-dynamic-workflows-primary-2026-05-28]]); whether Opus 4.8 itself is on all four surfaces same-day is implicit but unstated.

## When to Use It

- **Drop-in upgrade for Opus 4.7 Claude Code workloads** — same pricing, becomes the recommended default. No migration cost to test.
- **Senior-level SWE tasks** where the SWE-bench Pro headline matters: this is the new frontier reference point for coding-agent capability.
- **Multi-agent code migration at scale** via the new **Dynamic Workflows** parallel-subagents preview.
- **Honesty/error-flagging-sensitive workflows**: error-detection is the Anthropic-named differentiation axis. Worth testing on rework-cost-sensitive surfaces (cf. [[ai-roi-gap|the rework portion of the token-spend funnel]]).

## Effort Control (new shipped feature)

Opus 4.8 ships with a 5-level effort menu (default: High):

| Level | Description | Slash command |
|---|---|---|
| **Low** | Fast, simple tasks, lowest token usage | `/effort low` |
| **Medium** | Everyday coding, balanced | `/effort medium` |
| **High** (default) | Solid reasoning — equivalent to Opus 4.7 always-on level | `/effort high` |
| **Max** | Deepest reasoning, highest token usage | `/effort max` |
| **Ultracode** | Max reasoning + automatic Dynamic Workflows orchestration | `/effort ultracode` |

claude.ai shipped a UI slider for the same range.

**Operator-cost discipline (zodchii framing)**: *"Running Low effort on 60% of your prompts and Max on the 10% that actually need deep reasoning is the discipline that cuts your monthly bill in half without touching output quality on what matters."* See [[zodchii-opus-4-8-setup-guide-2026-05-29]] for full routing-matrix discipline.

## Dynamic Workflows (preview)

New orchestration primitive shipped same-day as Opus 4.8 — see [[anthropic-dynamic-workflows-primary-2026-05-28|the Anthropic primary]] for full operational detail. Headline characteristics:

- **Tens to hundreds of parallel subagents in a single session** (Anthropic primary framing); practitioner-side ([[zodchii-opus-4-8-setup-guide-2026-05-29|zodchii]]) reports **up to 1,000 agents per run** with **100 subagents ≈ $50-200**. Operator-cost-cap available via `--max-budget-usd <amount>` CLI flag.
- **New `ultracode` Claude Code setting** in the effort menu — sets effort to `xhigh` and lets Claude decide automatically when to fan out to a workflow
- **Adversarial-agent verification** at the convergence-termination layer — *"agents address the problem from independent angles, other agents try to refute what they found, and the run keeps iterating until the answers converge"*
- **Persistence across interruption**: progress saved during the run; interrupted jobs resume rather than restart
- **Distribution at launch**: Claude Code CLI + Desktop + VS Code extension + Claude API + Amazon Bedrock + Google Vertex AI + Microsoft Foundry — broader-than-Claude-Code distribution on day one
- **Default-on for Max / Team / API; default-off for Enterprise** (admin-enable via managed settings)
- **Named use cases**: codebase-wide bug hunts / security audits, large migrations / language ports, critical work needing adversarial review
- **Launch case study**: Jarred Sumner's Bun Zig→Rust port — 99.8% test suite passing, ~750K LOC Rust, 11 days from first commit to merge (port not yet in production)
- **Operator-side cost warning**: *"substantially more tokens than a typical Claude Code session"* — first-run confirmation gate enforced
- **Pairs with [[code-mode]]**: code-mode names the runtime primitive (agent writes code that calls tools through a runtime); Dynamic Workflows is the orchestration layer above

## Community Sentiment

- **2026-05-28 launch**; same-day as Anthropic's [[anthropic-series-h-65b-965b-2026-05-28|Series H]]. Pairing the capability rotation with the capital event amplifies both.
- **First wiki-captured named-practitioner Codex→Opus migration claim at launch surface**: *"Creator Dan Shipper used the model to transition off Codex."* (Digg, May 28). Shipper has commercial incentives with Anthropic; treat as marketing-coordinated rather than independent practitioner-validation. Track for *unsolicited* Codex→Opus migration content over the next 30 days.

## Resources

- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — launch source page (multiple Digg confirmations)
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — Anthropic primary on Dynamic Workflows with Bun case study
- [[anthropic-series-h-65b-965b-2026-05-28]] — same-day capital event
- [[anthropic-claude-space-to-think-2026-05-28]] — same-week strategic positioning
- [[anthropic-47b-runrate-willison-2026-05-29]] — same-week underlying-fundamentals component ($47B run-rate)
- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — practitioner-side setup guide; concrete benchmark numbers + effort menu + fast-mode pricing + env vars + settings.json + routing matrix + `--max-budget-usd` flag
- [[nateherk-opus-4-8-aios-2026-05-29]] — practitioner-side AI-OS architecture; Four C's framework + practitioner qualitative 4.6 vs 4.7 vs 4.8 comparison
- [[claude-opus-4-7]] — predecessor; succession noted
- [[claude-code]] — recommended model for this surface
- [[code-mode]] — runtime primitive the Dynamic Workflows orchestration sits above
