---
name: OpenTeams
type: company
status: active
last_updated: 2026-07-27
---

## What It Is

**OpenTeams** is the company behind **Nebari** (`nebari.dev`), an open-source, modular AI-infrastructure stack, led by **[[travis-oliphant|Travis Oliphant]]** (creator of NumPy/SciPy, co-founder of Anaconda) with **Dharhas Pothina** guiding Nebari. Its thesis — laid out in the June 2026 *"Distributed AI Economy"* whitepaper ([[openteams-distributed-ai-economy-whitepaper-2026-06]]) — is that enterprises should **own** their AI as sovereign, reproducible, auditable infrastructure rather than **rent** it through black-box APIs, and that the **organizational context** which fuels AI ROI should stay a governed, org-owned asset. A direct architectural instantiation of the [[reverse-information-paradox]].

## The three-layer architecture

- **Layer 1 — Infrastructure**: **Nebari** (open-source modular stack, 15+ composable packs atop `nebari-infrastructure-core`; standardizes compute/env mgmt, model deployment+versioning, RBAC/audit/governance) + **Nebi** (packaging & reproducibility layer — *"pip/npm for AI"*, the format by which Frames/Cogs/Ops are versioned and installed) + the **Intelligence Hub** (an org's sovereign AI deployment inside its own perimeter, with **Organizational Memory** as its persistent context substrate).
- **Layer 2 — Execution**: **Frames / Cogs / Ops** —
  - **Frames**: scoped, inheritable, composable, shareable, discoverable artifacts carrying org context (rules, terminology, goals, style, norms, skills, prompts). *"A Frame is not a prompt; it is an organizational artifact governed by the organization that owns it."* Effectively the [[claude-md-pattern|CLAUDE.md]]/[[context-engineering|context]] layer promoted to a versioned, inheritable, exchangeable enterprise asset.
  - **Cogs**: governed AI workers oriented by Frames — the unit at which "what did this Cog do, under which Frames, with what inputs?" becomes auditable.
  - **Ops**: installable, versioned, supervised workflows that combine Cogs + Frames with human-in-the-loop checkpoints (*"close the books," "onboard this customer"*).
- **Layer 3 — Economy**: a marketplace where Frames/Cogs/Ops are published, discovered, installed, and exchanged across Hubs — *"the work, the workers, and the context that orients them"* (most Frames shared free, some commercial). Self-positioned as *"the Linux + App Store for enterprise AI."*

## Traction Signals

- **Founder pedigree** is the strongest signal: [[travis-oliphant|Oliphant]]'s NumPy/SciPy/Anaconda track record + Dharhas Pothina's ~6 years on Nebari. **Nebari itself is a real, pre-existing open-source project** (`nebari.dev`, JupyterHub-on-Kubernetes lineage) — not vaporware.
- The **Intelligence Hub / Frames / Cogs / Ops / marketplace** layer, however, is **vision-stage**: the whitepaper is marked *Revision 6 / Confidential* with a roadmap whose **Phase 1 is "now–6 months"** (Frame protocol v1, Desktop App *alpha*). No adoption/marketplace metrics yet — treat the architecture as positioning, not shipped scale.
- Single-source so far (the whitepaper); watch for an external launch, GitHub activity on the Frame protocol, or third-party Hub deployments before upgrading status.

## Compared To

- **[[chamath-decision-context-agents|8090 "Software Factory"]]** — the closest analogue; the whitepaper explicitly frames OpenTeams as an *"Intelligent Ops Factory"* — adjacent but *"more fundamental"* (produces owned operational intelligence, not software products).
- **Foundation-model providers / cloud AI platforms / agent frameworks ([[langchain]]) / enterprise SaaS** — the whitepaper's own competitor grid; OpenTeams' claimed differentiator is the *combination* of open standard + portable-context (Frames) + marketplace.
- Thesis-siblings on the "own your intelligence" axis: [[reverse-information-paradox|Nadella's Reverse Information Paradox]], [[ai-native-organizations]], [[company-brain]].

## Resources
- [[openteams-distributed-ai-economy-whitepaper-2026-06]] — the anchor whitepaper (June 2026)
- `nebari.dev` — the open-source stack
