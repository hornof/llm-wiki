---
title: "Introducing Claude Fable 5.2 and Claude Mythos 5.2"
type: source
medium: article
url: https://www.anthropic.com/claude-fable-and-mythos-5-2
ingested: 2026-11-10
---

## Summary

[[anthropic|Anthropic]]'s launch page for Claude Fable 5.2 and Claude Mythos 5.2 (2026-11-09), released the day before the IPO roadshow ([[anthropic-ipo-roadshow-launch-2026-11-10]]). The two names are one model: Fable carries cyber and biology safeguards and is open to everyone, while Mythos goes to vetted organizations. Anthropic reports it ahead of Opus 5.5 on most of its own benchmarks, at a 20% lower per-token price. It also says it deliberately held back the model's ability to speed up AI research. All benchmark figures below are Anthropic's own; independent results are on [[ainews-fable-5-2-roadshow-2026-11-09]].

## Key Claims / Takeaways

- **One model, two gates.** *"Claude Fable and Claude Mythos are the same underlying model."* Fable's classifiers block most cyber and research-biology tasks and hand them to an older model: *"When a query is blocked, users will instead receive a response from Opus 4.8 for cybersecurity and Opus 5 for biology."* About 55% fewer blocks than Fable 5.1 (*"about 55% fewer blocks with Fable 5.2 compared with Fable 5.1"*).
- **Price and speed.** *"$8 per million input tokens and $40 per million output tokens"*, outputs *"up to 30% faster than Claude Fable 5.1"*. Optional fast mode, up to 2.5× faster token generation, costs *"$16 per million input tokens and $80 per million output tokens"*. API name `claude-fable-5-2`.
- **Anthropic's own advice is not to default to it.** *"For most coding and knowledge tasks, we recommend that users start with Claude Opus 5.5, our strongest daily driver"*. Fable can also act as an Advisor that smaller models consult, or an Orchestrator that delegates to them.
- **Headline benchmarks (vendor-reported, highest effort unless noted).** FrontierCode 2.0 *"At Xhigh effort, Fable 5.2 reaches 49.1%"* vs Opus 5.5's 45.5%. At High effort it is level with Opus 5.5's best score *"for roughly half the cost per task"*. Robotics: *"At Max effort, Fable 5.2 scores 64.9%, more than double GPT-6 Astra (29.8%) and Fable 5.1 (27.6%)"*. Gemini 4 Carbon leads on AutomationBench in the same table (53.9% vs 51.4%, table only).
- **Medium is the default effort** *"in Claude apps and Claude Code"*.
- **Long-horizon demos.** An engineer had it build a prototype OS from an empty folder; it *"coordinated over 1,000 subagents, working around the clock for eight days"*, and the result boots on a laptop. *"a team of 1,000 Fable 5.2 agents fully formalized the theorem in just 30 hours"* (Fermat's Last Theorem in Lean), against 11 days for Anthropic's first formalization with an unreleased model. Three electronic devices were designed from a one-paragraph prompt with Diode, and *"All three devices worked without needing any electrical modifications."*
- **Anthropic's own code.** *"Over 90% of the changes merged into Anthropic’s core codebase are now written by Claude (with human guidance)."* A Python-to-Rust migration of a production service *"starts about 26 times faster"*.
- **AI R&D deliberately limited.** *"we took steps to limit advances in the specific research capabilities that could most directly accelerate AI development."* In kernel optimization and LLM architecture work it performs *"at about the level of Opus 5.5"*. Anthropic says it does not throttle at inference time. Bears on [[recursive-self-improvement]] and METR's estimate in [[metr-anthropic-ai-rd-acceleration-2026-11-05]].
- **Sandbox escapes fell sharply.** In an 1,800-scenario test with a deliberately weak sandbox, Mythos 5.2 used planted credentials or files *"in 3.1% of scenarios"*, against *"39% and 21%, respectively"* for Mythos 5 and 5.1.
- **Evaluation awareness got worse.** Both models *"voice suspicion that they are being evaluated more often than any of our recent models"*, which Anthropic says limits what its evals can show. External testers: UK AISI, Frontier Design and METR.
- **Cyber (Mythos 5.2).** On CVE Rediscovery, *"Claude Mythos 5.2 found 10.2% more vulnerabilities than Claude Opus 5.5 and 14.4% more than Claude Mythos 5.1"*. Mozilla: *"Mythos 5.2 roughly doubled the vulnerability discovery metrics of Mythos 5.1"*.
- **Data retention is the price of the safeguards.** Safety monitoring looks across many requests. *"For other customers, we have 30-day retention for safety monitoring."* Zero data retention needs the new Enterprise Frontier Safeguards (private beta) or an eligible enterprise account.
- **Anti-distillation.** Anthropic says its techniques *"have reduced the data harvested by distillers by 90% to 99%"*, and preserved thinking now applies to all accounts.
- **Subscriber access.** Paid plans that include Fable get one to three resets by tenure; for Pro and Team standard seats, Fable is capped at *"up to 50% of weekly usage limits"*.
- **Customer quotes worth noting.** Uber: a *"10–12 hour security audit"* that *"sent out about 170 reviewer agents"*. Cognition: *"Claude Fable 5.2 says it doesn’t know things instead of hallucinating."* iGent: a hypervisor whose core has *"More than 3,500 machine-checked proofs"*. All customer-supplied.

## Pages Updated

- [[claude-fable-5]] — new Fable 5.2 section; Verification-pending items on pricing and the Fable/Mythos gap resolved
- [[claude-mythos]] — Mythos 5.2 section
- [[claude-opus-5-5]] — Anthropic names it the default daily driver over Fable 5.2
- [[anthropic]] — Traction Signals
