---
title: "Willison: Copilot Cowork exfiltrates files via agentic attack"
type: source
medium: article
url: https://simonwillison.net/2026/May/26/copilot-cowork-exfiltrates-files/
ingested: 2026-05-27
---

## Summary

[[simon-willison|Simon Willison]] post (May 26, 2026) surfaced via 2026-05-26 Daily Brief covering an **agentic exfiltration attack on "Copilot Cowork"** — a deployed agent with file-system access was induced to exfiltrate files. Primary not deeply fetched in this ingest pass; brief-tier capture only. **Brief framing**: *"Deployed agent security is actively failing."* First wiki-captured concrete agent-exfiltration incident named in a high-signal post.

## Key Claims / Takeaways

### What the brief captures

- **An agent named "Copilot Cowork"** (brief attributes to Microsoft; product naming is ambiguous — see §Product naming question below) was made to exfiltrate files via an agentic attack.
- **Brief framing — hot take**: *"Cowork exfil shows the real cost of shipping agents before you've solved containment. Not a bug — a design gap. Every productivity tool that gives agents file access needs to ship with assumptions of compromise, not trust."*
- **Brief framing — insightful**: *"The pattern: agent APIs grow faster than threat modeling. Cowork's design probably assumed agents would stay in-lane; attackers don't. This is why runtime observability matters more than pre-deployment guardrails — you need to see deviation, not just prevent it."*

### Product naming question (verification-pending)

The brief attributes "Copilot Cowork" to Microsoft. Existing wiki entities relevant here:

- **[[claude-cowork]]** — Anthropic's autonomous-execution tab in Claude Desktop (well-documented, file-system access, MCP connectors).
- **Microsoft 365 Copilot** — Microsoft's enterprise-AI suite (referenced in [[lennysan-shipper-10-takeaways-2026-05-24]] via Crepe Supreme comment; no Microsoft entity page exists).

Three possibilities for the brief's "Microsoft Copilot Cowork":

1. **A new Microsoft product** literally named "Copilot Cowork" — would be a deliberate name collision with Anthropic's Claude Cowork.
2. **A Microsoft 365 Copilot feature** the brief is informally labeling "Cowork" (Microsoft has its own agent surfaces inside M365 Copilot that share Cowork-like autonomous-execution semantics).
3. **Brief mis-attribution** — Willison's post may actually be about Anthropic's Cowork; the brief may have substituted "Microsoft Copilot" prefix.

Willison's URL slug `copilot-cowork-exfiltrates-files` does not disambiguate. **Worth fetching the primary to resolve.**

### Why it matters

- **First wiki-captured concrete agent-exfiltration incident** named in a high-signal post (Willison) on a named productivity-agent product.
- **Validates the runtime-observability thesis** — pre-deployment guardrails are insufficient; need to see deviation in production, not just prevent it.
- **Pairs with [[bsuh-agents-need-control-flow-2026-05|Bsuh on control-flow agents]]** — Bsuh's argument that agents need structural guardrails (not just prompt-level), Cowork exfil is the inverse-direction signal (without containment, agents do exfiltrate).

### What's notably absent from the brief

- **Attack vector details**: prompt injection? Misconfigured permissions? Indirect prompt injection via a file the agent was asked to read? Each implies a different threat model.
- **Damage scope**: was real customer data exfiltrated, or was this a proof-of-concept / red-team demo? Brief doesn't say.
- **Vendor response**: did Microsoft (or Anthropic, if mis-attributed) issue a patch or advisory? Brief doesn't say.
- **Willison's full analysis**: brief surfaces hot-take + insightful framings but not Willison's primary text.

## Pages Updated

- [[simon-willison]] — added post + agent-exfiltration coverage as recent activity
- [[claude-cowork]] — disambiguation note added (Microsoft "Copilot Cowork" naming-collision flag; primary unfetched)
- [[mcp]] — no update (MCP not named as attack surface in brief)

Verification-pending: product naming attribution; attack vector; damage scope; vendor response.
