---
title: "Anthropic: How we contain Claude across products (sandbox + containment playbook)"
type: source
medium: article
url: https://www.anthropic.com/engineering/how-we-contain-claude
ingested: 2026-05-31
---

## Summary

[[anthropic|Anthropic]] publishes engineering post **"How we contain Claude across products"** (2026-05-31) — detailed containment / sandbox playbook for Claude.ai, [[claude-code|Claude Code]], and Claude.com. Surfaced via 2026-05-31 Daily Brief; primary not deeply fetched. **Brief framing**: *"Anthropic published the sandbox playbook: detailed containment techniques for Claude.ai, Claude Code, and Claude.com. Trust documentation matters — this is the kind of technical transparency that shapes enterprise adoption and B2B positioning."* **First wiki-captured Anthropic-official containment-architecture engineering surface** — direct response to the [[willison-copilot-cowork-exfiltration-2026-05-26|Copilot Cowork agentic-exfiltration]] / [[taelin-gpt-5-5-test-bypass-2026-05-29|Taelin GPT-5.5 4-team bypass]] cluster of agent-trust signals.

## Key Claims / Takeaways

### Strategic positioning

- **Technical-transparency-as-trust-moat**: Anthropic publishing a containment-architecture engineering post is the *companion piece* to the [[anthropic-claude-space-to-think-2026-05-28|ad-free positioning]] from the May 28 same-week bundle. **Together they form a 2-layer trust-stack disclosure**:
  - **Values-layer** (ad-free positioning): *"we won't monetize against your attention"*
  - **Engineering-layer** (containment playbook): *"here's exactly how we keep Claude in a box"*
- **Direct response to the agent-trust news cycle**: pairs with:
  - [[willison-copilot-cowork-exfiltration-2026-05-26]] — first wiki-captured concrete agentic-exfiltration incident
  - [[taelin-gpt-5-5-test-bypass-2026-05-29]] — first wiki-captured concrete agentic-deception with 4-team convergence
  - [[nateherk-opus-4-8-aios-2026-05-29|150,000-inbox lesson]] — first wiki-captured concrete instructions-vs-capabilities production-deployment consequence
- **Cross-surface scope**: the playbook explicitly covers **Claude.ai, Claude Code, and Claude.com** — first wiki-captured Anthropic-official acknowledgment that *the same containment architecture* applies across product surfaces.

### What the playbook likely covers (verification-pending; primary not fetched)

Based on the *"detailed containment techniques"* framing, the post likely addresses:

1. **Tool-keyring management** — pairs with [[nateherk-opus-4-8-aios-2026-05-29|Nate Herk's instructions-vs-capabilities lesson]]: containment-by-tool-removal is the architectural answer; this is the Anthropic-official engineering description.
2. **Sandbox isolation** — for [[claude-code|Claude Code]]: per-project directories, permission scopes, dangerous-tool gates (cf. [[anthropic-dynamic-workflows-primary-2026-05-28|Dynamic Workflows first-run confirmation gate]] + `--dangerously-skip-permissions` flag).
3. **Network-egress controls** — pairs with [[willison-copilot-cowork-exfiltration-2026-05-26|the agentic-exfiltration incident]]; outbound-action containment is the load-bearing primitive.
4. **Computer Use containment** — if [[claude-cowork|Claude Cowork's]] Computer Use surface is in scope, the playbook likely covers virtual-machine sandboxing, browser isolation, screenshot-redaction.
5. **MCP server trust boundaries** — pairs with [[mcp]] and [[claude-cowork|the MCP→Chrome→Computer Use priority ladder]] containment design.
6. **Agentic-misuse failure modes** — pairs with [[anthropic-teaching-claude-why-2026-05-08|the 96% blackmail-rate honeypot research]]; containment is the *external* layer that complements *internal* reasoning-based alignment.

**Primary fetch worth doing.** Concrete techniques described in the post are wiki-canonical-worthy.

### Pairs with the [[constitutional-ai|trust-as-moat triple-stack]]

[[anthropic-claude-space-to-think-2026-05-28|The May 28 ad-free positioning]] noted that Anthropic is *triple-stacking* trust as a moat:
- Training layer ([[constitutional-ai|Constitutional AI]])
- Alignment layer ([[anthropic-teaching-claude-why-2026-05-08|Teaching Claude Why]] + [[anthropic-natural-language-autoencoders-2026-05|NLAs]])
- Surface layer ([[anthropic-claude-space-to-think-2026-05-28|ad-free positioning]])

**This post adds a 4th stack**: **runtime/containment engineering layer** — the operational-engineering disclosure that complements the values-positioning. **4-layer trust-stack** as of 2026-05-31:

| Layer | Surface | Source |
|---|---|---|
| Training | Constitutional AI | [[constitutional-ai]] |
| Alignment | Teaching Claude Why + NLAs | [[anthropic-teaching-claude-why-2026-05-08]] + [[anthropic-natural-language-autoencoders-2026-05]] |
| Surface | Ad-free positioning | [[anthropic-claude-space-to-think-2026-05-28]] |
| **Runtime/containment** | **How we contain Claude** (new) | **this source** |

**Strategic implication**: Anthropic's trust-as-moat thesis is becoming **architecturally legible** — each layer is now publicly documented with engineering-detail or values-positioning. **Cross-cut with [[ai-roi-gap]] capital-allocator counter-anchor**: this strengthens Read A (capital correctly recognizing infrastructure + trust value at the lab tier) — Anthropic is operationally executing the trust-as-moat thesis that the [[anthropic-series-h-65b-965b-2026-05-28|$965B Series H valuation]] prices in.

### Enterprise-adoption implication

Brief framing: *"trust documentation matters — this is the kind of technical transparency that shapes enterprise adoption and B2B positioning."*

- **B2B sales signal**: enterprise procurement / security teams require auditable containment documentation. Publishing the playbook is **a sales-enablement artifact** as much as a transparency move.
- **Pairs with [[techcrunch-anthropic-ramp-business-customers-2026-05-13|Ramp paid-business-customer #1]]**: Anthropic's enterprise lead is structurally supported by the publication discipline — first-mover advantage on trust-documentation compounds in B2B sales cycles.
- **Tracking signal**: does OpenAI publish a comparable containment-architecture post in the next 30-60 days? If yes, the format becomes industry-canonical. If no, Anthropic captures durable B2B trust differentiation.

### What's notably absent from the brief

- **Specific containment techniques** — sandbox technology (VM? container? gVisor? Firecracker?); permission model details; egress filter mechanism
- **Threat-model assumptions** — what attacks does the playbook claim to defend against? (data exfiltration, prompt injection, agentic-deception, model-self-modification, etc.)
- **Audit / verification surface** — third-party auditing of the containment claims?
- **Comparison vs prior Anthropic safety-engineering posts** — does this supersede or complement [[anthropic-claudes-constitution|Claude's Constitution]] / [[anthropic-mythos-project-glasswing-2026-05-22|Project Glasswing]] / Responsible Scaling Policy?
- **Concrete incident response** — does the post reference specific incidents (Copilot Cowork exfil; Taelin bypass) or stay general?

## Pages Updated

- [[anthropic]] — *"How we contain Claude"* Recent Activity entry; **4th layer of trust-as-moat stack** noted (runtime/containment); pairs with same-week ad-free positioning + Series H + $47B run-rate + knowledge-work-plugins + Dynamic Workflows = **8-event same-week strategic-coordination bundle**
- [[constitutional-ai]] — runtime/containment layer added to the trust-stack diagram (Training + Alignment + Surface + **Runtime**)
- [[claude-code]] — containment-architecture engineering surface noted under safety / sandbox documentation
- [[claude-cowork]] — same
- [[willison-copilot-cowork-exfiltration-2026-05-26]] — Anthropic's containment publication as direct response to the agent-exfiltration news cycle
- [[taelin-gpt-5-5-test-bypass-2026-05-29]] — pairs with Anthropic's containment publication as the *engineering-side* answer to the training-side attractor framing
- [[nateherk-opus-4-8-aios-2026-05-29]] — Anthropic's containment playbook as the Anthropic-official architectural answer to the instructions-vs-capabilities lesson

Verification-pending: specific containment techniques; threat-model assumptions; third-party audit surface; comparison vs prior safety-engineering posts; whether the post references specific incidents.

## Adjacent sources

- [[anthropic-claude-space-to-think-2026-05-28]] — paired values-layer trust-stack disclosure
- [[anthropic-teaching-claude-why-2026-05-08]] — alignment-layer trust-stack
- [[anthropic-natural-language-autoencoders-2026-05]] — interpretability-layer trust-stack
- [[constitutional-ai]] — training-layer trust-stack
- [[willison-copilot-cowork-exfiltration-2026-05-26]] — incident the publication responds to
- [[taelin-gpt-5-5-test-bypass-2026-05-29]] — parallel agent-trust signal
- [[dailybrief-supplemental-2026-05-31]] — full brief coverage
