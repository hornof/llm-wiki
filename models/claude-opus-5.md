---
name: Claude Opus 5
type: model
provider: Anthropic
status: available
last_updated: 2026-08-09
---

## What It Is

**Claude Opus 5** (Anthropic, launched **2026-07-24**, `claude-opus-5`) is the new Opus generation — positioned as *"the frontier intelligence of [[claude-fable-5|Claude Fable 5]] at half the price,"* i.e. *"greatly improved performance for the same cost as its predecessor, [[claude-opus-4-8|Opus 4.8]]."* Its headline behavioral gain: it's much stronger at **verifying its own work and iterating carefully until it succeeds** — the verifier-discipline the [[loop-engineering]] / [[reward-hacking]] threads keep pointing at. Now the **default model on Claude Max, strongest model on Claude Pro**, available across API + Claude.ai + Claude Code + Cowork.

> ⚠️ **"Half the price" = cost per *task*, not per token.** Per-token pricing is **$5/M input, $25/M output — identical to Opus 4.8.** The savings come from efficiency (fewer tokens per task): customers report *"half the cost per task"* vs Fable 5. Don't read it as a per-token cut.

## Strengths & Weaknesses

**Benchmarks (Anthropic-published):**
- **Frontier-Bench v0.1**: surpasses all other models; **>2× Opus 4.8**.
- **CursorBench 3.2 (max effort)**: within **0.5% of Fable 5's peak** — the "Fable-level" claim.
- **ARC-AGI 3**: **3× the next-best model**. **Zapier AutomationBench**: ~**1.5× next-best** (Zapier CEO: *"Opus 5 hit 100%"* where previous models didn't pass).
- **OSWorld 2.0 (computer use)**: surpasses Fable 5's best at **~⅓ the cost**.
- **Life sciences / organic chemistry (+10.2pp) / protein (+7.7pp)** over Opus 4.8.
- Customer voices: Devin — *"approaches Fable-level performance at half the cost"*; Cursor — *"near Fable 5 intelligence at Opus speed and cost."*

**Safety (a direct counter to the deception/reward-hacking thread):**
- *"Most aligned model to date"* — adheres to Claude's Constitution better than Opus 4.8 / [[claude-sonnet-5|Sonnet 5]] / Fable 5; **lowest rates of deceptive behavior**; behavioral-audit score **2.3** (lowest).
- **Cyber safeguards**: substantially behind [[claude-mythos|Mythos 5]] on exploit development; cyber classifiers intervene ~**85% less often** than Fable 5; blocks binary vuln-scanning / pentest / exploit-gen.
- **Prompt-injection**: [[boris-cherny|Boris Cherny]] flags Opus 5 as the **hardest-to-prompt-inject model yet** per the system card ([Willison, 2026-07-25](https://simonwillison.net/2026/Jul/25/boris-cherny/)) — a [[prompt-injection]] mitigation datapoint. *(Not stated in the main announcement; per Cherny/system card.)*

**Not stated**: context window.

## When to Use It

- **Default agentic-coding + computer-use model** — the verify-and-iterate gains + OSWorld/CursorBench results make it the new Opus workhorse at the same per-token cost as 4.8 (so a strict upgrade for existing Opus-4.8 workloads).
- **Fable-adjacent quality at lower cost-per-task** — when you wanted Fable 5 but not its price/latency.
- **Fast Mode**: ~2.5× default speed at 2× base price.

## Community Sentiment

Launch (2026-07-24). Framed by the [[dailybrief-roundup-2026-07-25|brief]] as a cost/capability-curve shift ("Fable-level at half the price"). The alignment + prompt-injection-resistance emphasis reads as Anthropic leaning into safety-as-differentiation amid the [[reward-hacking|ExploitGym]] / agentic-misalignment discourse.

- **Community capability receipt** (r/ClaudeAI, 2026-07-26, [[graph-engineering-cluster-2026-07-26]]): a "procedural desert explorer" browser graphics tech demo built *entirely with Claude Code on Opus 5* — GPU-clipmap procedural dunes (no meshes/textures/downloaded assets), permanent sand deformation, GPU-cloth robe, per-pixel physically-based sky, all in shader code. A concrete practitioner signal for Opus 5 on graphics/shader-heavy work. **Follow-ups (2026-07-28, [[dailybrief-roundup-2026-07-29]])**: the same developer shipped a **waterbending demo** and a **real-time procedural snow WebGPU** render — a short cadence of increasingly complex Opus-5-built graphics demos, reinforcing the shader/WebGPU capability signal.

## Resources
- [[anthropic-claude-opus-5-launch-2026-07-24]] — launch source (fetched primary)
- [anthropic.com/news/claude-opus-5](https://www.anthropic.com/news/claude-opus-5)
- **System prompt published** (Willison, 2026-08-09, [[dailybrief-roundup-2026-08-09]]): the Opus 5 system prompt surfaced publicly, alongside a note on the DoC export-control suspension history (controls on Claude lifted 2026-06-30) — a model-behavior + governance transparency datapoint. [simonwillison.net](https://simonwillison.net/2026/Aug/9/claude-opus-5-system-prompt/)
- [[claude-opus-4-8]] — predecessor (same per-token price); [[claude-fable-5]] — the top-tier it approaches
