---
name: Abridge
type: company
status: active
last_updated: 2026-05-15
---

## What It Is

Abridge is a vertical-AI company building a **clinical intelligence layer** for healthcare. Founded 2018 (pre-ChatGPT). Original product: **ambient clinical documentation** — records the patient-clinician conversation, generates clinical notes automatically. As of May 2026 Abridge has expanded the thesis to *clinical intelligence layer* — documentation + real-time clinical decision support + **prior-authorization guidance during visits** + multi-stakeholder workflows (payers, pharma, patients). First wiki source via [[latentspace-abridge-healthcare-os-2026-05-15|Latent Space podcast, May 14 2026]].

## Traction Signals

- **100M+ doctor visits cumulative** as of May 2026; projected **80M+ conversations in 2026 alone** — [[latentspace-abridge-healthcare-os-2026-05-15]]
- **250+ large US health systems** as customers — [[latentspace-abridge-healthcare-os-2026-05-15]]
- **28+ languages, 50+ specialties** — [[latentspace-abridge-healthcare-os-2026-05-15]]
- **Clinicians save 10-20 hours per week** on documentation (interview claim, not independently audited) — [[latentspace-abridge-healthcare-os-2026-05-15]]
- **Prior-authorization decisions in minutes vs. weeks** — the headline non-documentation use case
- **$300M Series E in June 2025** at **$5.3B valuation**; $250M Series D earlier in 2025; **$830M+ total funding** ([[forbes-ai-50-2026|Forbes 2026 AI 50]] snapshot, since superseded)
- **Paraform Talent Density top-50 (#37)** as of May 2026 — [[brianlamanna-paraform-talent-density-2026-05]]
- Generic customer references: **Johns Hopkins, Kaiser Permanente, Mayo**
- Vertical-AI category alongside **Harvey** (legal), **Decagon** (customer support), **Glean** (search), **Hebbia** (research), **Rogo** (financial research) per the [[brianlamanna-paraform-talent-density-2026-05|Paraform list]]

## Product & Architecture

- **Ambient clinical documentation** — voice recording during visits → automatic clinical note generation
- **Real-time clinical decision support** — alerts and prompts during the visit, not retrospective
- **Prior-authorization guidance** during the visit (decisions in minutes vs. weeks)
- **Patient visit summaries** — patient-facing artifact

Architectural framing from Chai Asawa (clinical-decision-support lead): *"Almost every agent is a coding agent underneath the hood... the EHR effectively like a file system."* The EHR-as-filesystem + agentic-coding-loop framing is the cleanest cross-domain restatement of the [[code-mode]] pattern surfaced for healthcare workflows.

## Key People

- **Janie Lee** — co-founder / CEO. Prior: pricing models at Opendoor; Loom.
- **Chai Asawa** — clinical-decision-support lead. Prior: early engineer at Glean.
- **Shiv Rao** — practicing cardiologist (rounds monthly); listed as CEO in Latent Space; possible co-CEO or transitional structure — *verify before external citation*.

## Why The Wiki Tracks Abridge

- **First vertical-AI company on this wiki with cumulative-volume numbers in the hundreds of millions and production deployment across 250+ health systems.** Pairs with [[anthropic-finance-agents-2026-05-05|Anthropic's finance agents]] as the second public-vertical product line at this maturity tier — different lab (vertical specialist), different vertical (healthcare not finance), same overall thesis (verticalize the agentic workflow).
- **The thesis shift from "ambient documentation" to "clinical intelligence layer"** is the load-bearing tracking surface. If the shift completes — Abridge becomes the documentation-plus-decision-support-plus-prior-auth-plus-payer-workflow substrate across 250+ health systems — it sets the template for how vertical-AI companies move from single-feature to vertical-OS.
- **Paired with [[theregister-ontario-clinical-ai-audit-2026-05-14|Ontario Auditor General audit]] as the calibration anchor**: vertical-AI deployment-at-scale ≠ vertical-AI at acceptable accuracy. Both signals are real; need to be held simultaneously.

## Stated Quotes (founder / leadership)

- *"We want our product to feel like air conditioning... in the background just making things better."* — Janie Lee (anti-engagement-maximization framing)
- *"80/20 doesn't work here."* — Janie Lee (healthcare accuracy floor)
- *"Almost every agent is a coding agent underneath the hood... the EHR effectively like a file system."* — Chai Asawa
- *"AI slop is AI without context."* — Chai Asawa

## Resources

- [[latentspace-abridge-healthcare-os-2026-05-15]] — Latent Space interview; primary source page
- [[forbes-ai-50-2026]] — funding snapshot context
- [[brianlamanna-paraform-talent-density-2026-05]] — talent-density ranking
- [[theregister-ontario-clinical-ai-audit-2026-05-14]] — paired counterweight; healthcare-AI accuracy audit
