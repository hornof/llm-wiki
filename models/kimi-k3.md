---
name: Kimi K3 (2.8T-A50B)
type: model
provider: Moonshot AI
status: available
last_updated: 2026-10-29
---

## What It Is

> **Successor (2026-10-23): Kimi K3.1 Pro**, plus a faster Highspeed variant. Both are live on Moonshot's API, and Pro's open weights are planned by 2026-11-04. See [[kimi-k3-1-pro-launch-2026-10-23]]. K3.1 Pro reportedly scores 55 on the Artificial Analysis index against K3's 44, and ranks #8 vs K3 Max's #17 in Code Arena WebDev. K3 is still the current *open-weights* release until the K3.1 weights ship.

**Kimi K3** is [[moonshot-ai|Moonshot AI]]'s new flagship — a **2.8-trillion-parameter Mixture-of-Experts model (≈50B active, "2.8T-A50B")**, billed as **the largest open model ever released**. Successor to the K2 line ([[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18|K2.6]]). The headline framing ([[dailybrief-roundup-2026-07-17|brief]]): *"Opus-class capability at Sonnet pricing"* — the open-model inflection where open weights compete on **capability *and* cost in the same tier**.

> ✅ **Weights released 2026-07-27** (on schedule). Per [[simon-willison|Simon Willison]] ([[dailybrief-roundup-2026-07-28]]), Moonshot published the **Kimi-K3 weights on Hugging Face** (`moonshotai/Kimi-K3`) — a **~1.56 TB artifact**. The earlier "largest open model ever released" headline (which was ahead of the drop as of 07-16) is now backed by an actual open-weight release. *(Prior caveat resolved.)*

## Strengths & Weaknesses

- **Capability (self-benchmarks, caveat)**: Moonshot's numbers show K3 *"mostly beating Claude Opus 4.8 max and GPT-5.5 high"* but **losing to [[claude-fable-5|Claude Fable 5]] and GPT-5.6 Sol** — i.e. upper-tier, not frontier-leading. Independent: **Artificial Analysis Elo 1547**; **leading model on Arena.ai's Frontend Code arena**.
- **Pricing**: **$3 / M input, $15 / M output** — matching [[claude-sonnet-5|Claude Sonnet]] tier, and a **large step up from K2.6's $0.95 / $4**. So "Sonnet pricing" is a *price increase* for Moonshot, framed against the capability jump — not a discount.
- **"3T-class" marketing tell**: they round **2.8T up to 3T** for marketing — Willison's flag that *"parameter count [no longer] signals capability."*
- **Pelican-on-a-bicycle benchmark**: generated a valid SVG for **~25¢** (95 input + 16,658 output tokens, **13,241 of them reasoning tokens**). Willison's point: even a joke benchmark still surfaces *"interesting model characteristics"* (tokenization quirks, reasoning-token efficiency, vision) — though it *"doesn't touch at all on… agentic tool calling."*

## When to Use It

- **Cost/capability-sensitive upper-tier work** where Sonnet-class pricing is acceptable and you want an open-weights option (once weights land 2026-07-27) — fine-tuning / on-prem / [[reverse-information-paradox|own-your-boundary]] deployments.
- Frontend/code generation (leads the Frontend Code arena). For the outright strongest model, Fable 5 / GPT-5.6 Sol still edge it.

## Community Sentiment

Launch (2026-07-16). Read as an **open-weight scaling inflection** feeding the [[ai-margin-collapse]] thesis — *"expect margin compression across the mid-market LLM API stack"* ([[dailybrief-roundup-2026-07-17|brief]]). Willison's grounding note: past the point where parameter count alone signals capability; benchmark *design* matters more as hype peaks.

- **2026-07-25 — UK AISI / CAISI preliminary cyber-capability assessment** ([[dailybrief-roundup-2026-07-25]], NIST): a safety-body pre-deployment evaluation of K3's *cyber* attack surface — the kind of independent held-out testing [[frontier-ai-governance|Hassabis's SRO]] proposed, now happening ad hoc on a specific open model. Also the model named in [[us-treasury-china-ai-sanctions-threat-2026-07-21|Bessent's sanctions-threat]] framing → K3 sits at the center of the open-weights governance/geopolitics debate.

## A cabinet secretary alleges distillation (2026-10-03)

**Update 2026-10-28:** The Information reports that Kimi K3.1 Pro relied heavily on GPT-6 Astra outputs ([[deepseek-moonshot-astra-distillation-2026-10-28]], via Reuters). This is a report from unnamed sources, not a finding. Moonshot didn't respond.

**Refreshed at the 2026-10-15 lint, which flagged this page as behind.**

**Treasury Secretary Bessent calls *"industrial distillation"* "a nice word for stealing" and claims *"Kimi says it is Claude"*** ([[dailybrief-roundup-2026-10-03]], Axios via Digg).

**The wiki's position, and it is deliberately unflattering to the claim: the quotable line is the least probative part.** A model self-identifying as another model is **weak evidence of distillation and strong evidence of training-data contamination** — the open web is full of Claude transcripts, and any model that ingested them will claim to be Claude without anyone having distilled anything. **It is a self-report from a system with no privileged access to its own provenance.**

**What the allegation does establish is where this page sits in a four-stage escalation** the wiki has tracked on [[ai-margin-collapse]]: mechanism (reasoning-trace replay, 2026-08-13) → **named actors** ([[anthropic|Anthropic]] accusing [[alibaba|Alibaba]], [[moonshot-ai|Moonshot]] and [[deepseek|DeepSeek]], 2026-09-10) → countermeasure ([[openai|OpenAI]] disrupting a campaign, 2026-10-01) → **trade policy.** **Moonshot AI is named at stage two and Kimi at stage four**, which makes this model a specific instance of a US trade-policy argument rather than only a capability datapoint.

**No technical substantiation was offered or captured** — no weight analysis, no output comparison, no methodology. **A political statement naming a model is a fact about the politics.** → [[frontier-ai-governance]]

## What it takes to serve it fast (2026-10-16)

An [[nvidia|NVIDIA]] engineer's vLLM post ([[vllm-kimi-k3-decode-gb300-2026-10-16]]) fuses most of K3's per-layer decode into custom kernels: **13 kernels and about 69 µs per layer, down from 23 and 130 µs.** Reported speedups over stock vLLM are **1.62–1.88× on 16 GB300 GPUs and 1.31–1.58× on 8**, with batch-1 decode at 256 and 193 tok/s. With speculative decoding, batch 1 reaches 842 tok/s against 488, but that uses a synthetic acceptance length.

**The useful fact for a buyer is the hardware line, not the speedup.** The tuned path targets **8 or 16 GB300s in one NVLink domain.** "Open weights" makes K3 possible to self-host; it does not make it cheap, and the [[#When to Use It|on-prem case above]] has to be costed against a rack, not a server. *(Vendor-engineer benchmark; NVIDIA sells the GPUs. Not yet independently reproduced. The code is in vLLM PR #61867; whether it is on by default is not stated.)*

## K3.1 Pro — the successor, and a doubled active count (2026-10-23)

[[kimi-k3-1-pro-launch-2026-10-23]]: Moonshot's own and press figures put K3.1 Pro at 2.8T total, **104B active**, with a 1M context. That's about twice K3's ~50B active, if both numbers are right. Neither has been checked against a model card. **Moonshot says it removed cybersecurity data from post-training,** and SiliconANGLE reports its cyber benchmark scores trail Astra and Opus 5.5, which may be by design. The reported $2/$10 price and the claimed wins over Opus 5.5 come from social posts. VentureBeat reports allegations of paid creator promotion around the launch.

## Resources
- [[vllm-kimi-k3-decode-gb300-2026-10-16]] — NVIDIA/vLLM decode optimisation on GB300
- [[kimi-k3-largest-open-model-2026-07-16]] — launch + Willison analysis (fetched primary)
- [Willison — "Kimi K3, and what we can still learn from the pelican benchmark"](https://simonwillison.net/2026/Jul/16/kimi-k3/)
- [[moonshot-ai]] — maker; [[ai-margin-collapse]] — the open-weights-cost thesis
