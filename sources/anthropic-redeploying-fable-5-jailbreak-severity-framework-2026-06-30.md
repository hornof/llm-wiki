---
title: "Redeploying Fable 5"
type: source
medium: article
url: https://www.anthropic.com/news/redeploying-fable-5
ingested: 2026-07-06
---

## Summary

Anthropic's announcement that [[claude-fable-5|Claude Fable 5]] and [[claude-mythos|Mythos 5]] returned globally after the June 2026 US export-control suspension was lifted, plus — more structurally important — a **multi-vendor jailbreak severity scoring framework** developed with Amazon, Microsoft, Google, and other Project Glasswing participants. Surfaced in the [[dailybrief-roundup-2026-07-06|2026-07-06 Daily Brief]]; resolves the open thread on the earlier [[claude-fable-5|export-control saga]].

## Key Claims / Takeaways

### Redeployment
- Fable 5 was suspended **June 12, 2026** under US export controls; controls lifted **June 30**; Fable 5 returned globally **July 1** across Claude Platform, Claude.ai, [[claude-code|Claude Code]], and [[claude-cowork|Claude Cowork]].
- **Access window**: Pro/Max/Team/select Enterprise got Fable 5 at up to **50% of weekly usage limits through July 7**, after which it moves to usage credits (pay-per-use). Matches [[dailybrief-roundup-2026-07-03|Greg Isenberg's pricing PSA]].
- Cloud re-enablement (AWS, Google Cloud, Microsoft Foundry) rolled out separately.
- **New safety classifier** targets the specific bypass technique from the Amazon research report — blocks it in "over 99% of cases," at the cost of **more false positives on routine coding** (a deliberate tradeoff). This is the concrete resolution of the [[claude-fable-5|Amazon/Jassy jailbreak dispute]].

### Jailbreak severity framework (the structural signal)
Consensus scoring standard so vendors can rank findings the same way. Four criteria:
1. **Capability Gain** — does the jailbreak exceed what existing tools already enable?
2. **Breadth of Capability Gain** — how many offensive tasks does it unlock?
3. **Ease of Weaponization** — human effort to deploy operationally.
4. **Discoverability** — how publicly accessible the technique is.

Rationale: "developers have no agreed-upon standard for which findings to focus on most urgently." A shared severity scale lets vendors and government partners triage consistently and respond faster to critical vulnerabilities.

## Owner's angle (from brief)

> "The framework matters more than the redeployment — once you can *measure* adversarial robustness the same way across vendors, you can actually compare models instead of guessing." Structural governance shift relevant to how you'd run safety evals at a startup.

## Pages Updated

- [[jailbreak-severity-framework]] (new)
- [[claude-fable-5]] (updated — redeployment resolves the export-control section)
- [[anthropic]] (updated)
- [[dailybrief-roundup-2026-07-06]]
