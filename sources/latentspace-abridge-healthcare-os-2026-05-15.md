---
title: 'Abridge: clinical intelligence layer at 100M doctor visits'
type: source
medium: podcast-episode
url: https://www.latent.space/p/abridge
ingested: 2026-05-15
---

## Summary

Latent Space interview with Abridge co-founder/CEO Janie Lee and clinical-decision-support lead Chai Asawa, published 2026-05-14. **Abridge has supported 100M+ doctor visits**, projects 80M+ conversations in 2026, deployed across **250+ large US health systems** in **28+ languages and 50+ specialties**. Founded 2018 (pre-ChatGPT). Original product is ambient clinical-documentation: records the patient-clinician conversation, generates clinical notes automatically. The company now positions itself as a **"clinical intelligence layer"** expanding into real-time clinical decision support, **prior-authorization guidance during visits** (decisions in minutes vs. weeks), and multi-stakeholder workflows (payers, pharma, patients). **$300M Series E in June 2025 at $5.3B valuation**, on top of a $250M Series D earlier in 2025. Clinicians report **saving 10-20 hours per week** on documentation. First wiki source on the vertical-healthcare-AI thread that has been gestating since the [[forbes-ai-50-2026]] mention (Abridge at $830M total funding, AI notetaker for doctors) and the [[brianlamanna-paraform-talent-density-2026-05|Paraform Talent Density]] #37 ranking.

## Key Claims / Takeaways

### Scale and traction

- **100M+ doctor visits processed cumulative**, projected **80M+ conversations in 2026 alone**.
- **250+ large US health systems** as customers; **28+ languages**; **50+ specialties**.
- $300M Series E (June 2025) at **$5.3B valuation**; $250M Series D earlier in 2025. Total funding stack puts Abridge ahead of the [[forbes-ai-50-2026]] $830M snapshot — list lagged actual round.
- **10-20 hours per week** of documentation time saved per clinician (interview claim, not independently audited).
- **Prior authorization** decisions in **minutes vs. weeks** is the headline non-documentation use case.

### Product positioning — "clinical intelligence layer"

The thesis shift is the load-bearing part of this source: Abridge is no longer pitching itself as ambient documentation. The framing is now an *intelligence layer* — documentation + real-time decision support + prior-auth + payer/pharma/patient workflows — sitting between the conversation and every downstream healthcare workflow that currently breaks. The brief-author lens: "conversation as OS means: patient tells doctor what's wrong, doctor writes it down naturally, and three downstream problems (note structure, auth, billing) solve themselves. Most healthcare AI is retrofitting onto EMRs; this is OS-level."

### Architecture and model strategy

- **"Almost every agent is a coding agent underneath the hood... the EHR effectively like a file system."** — Chai Asawa. The architectural claim that EHRs-as-filesystem + agentic-coding-loop is the right abstraction is the cleanest cross-domain restatement of the [[code-mode]] pattern surfaced for healthcare workflows.
- **"AI slop is AI without context."** — Chai Asawa. Personalization and clinician-preference modeling are first-class concerns, not retrofit.
- **"80/20 doesn't work here"** — Janie Lee. Healthcare's accuracy floor is unforgiving; the engineering posture differs structurally from consumer-AI tolerance.
- **"We want our product to feel like air conditioning... in the background just making things better."** — Janie Lee, on alert fatigue. Anti-engagement-maximization framing, parallel to Anthropic's [[anthropic-claude-space-to-think-2026-05|Claude space-to-think]] stance on consumer AI.

### Customer references

- Generic references to **Johns Hopkins, Kaiser Permanente, Mayo** as part of the "250 large and complex US health systems" base; no exclusivity disclosed.
- One unnamed clinician: *"Abridge has helped us... finally able to go home and eat dinner with our kids for the first time."*

### People

- **Janie Lee** — co-founder / CEO. Prior: pricing models at Opendoor; Loom.
- **Chai Asawa** — clinical-decision-support lead. Prior: early engineer at Glean (enterprise search).
- **Shiv Rao** — CEO (note: Latent Space lists both Janie Lee and Shiv Rao as CEO; likely co-CEO or transitional structure; verify before external citation). Practicing cardiologist who still rounds monthly.

## Why It Matters

- **Concrete proof point for vertical-healthcare AI at scale.** Abridge is the first vertical-AI company on this wiki with both (a) cumulative-volume numbers in the hundreds of millions, (b) production deployment across 250+ health systems, and (c) a stated thesis-shift from single-feature (documentation) to vertical-OS (clinical intelligence). Pairs with [[anthropic-finance-agents-2026-05-05]] as the second public-vertical product line at this maturity tier — different lab (vertical specialist, not horizontal frontier lab), different vertical (healthcare not finance), same overall thesis (verticalize the agentic workflow).
- **Prior-auth as the wedge** is structurally interesting: it's a high-frustration, high-frequency workflow with measurable outcomes. The brief-author's lens — *"prior auth was the wedge because it's broken enough that any real improvement gets adopted fast; once that muscle is built, the same system handles referrals, compliance, billing"* — is the cleanest articulation of how vertical-AI compounds within a domain.
- **"Almost every agent is a coding agent underneath" + "EHR as file system"** is a Claude-Code-pattern cross-domain confirmation. The same abstraction (filesystem + agentic loop) that powers [[claude-code]] in software engineering powers Abridge in clinical decision support. Useful citation for the [[code-mode]] universality argument.
- **80/20-doesn't-work** is a calibration anchor — healthcare's accuracy floor is the *opposite* of consumer-AI tolerance and is more useful as a design constraint than as a barrier-to-entry framing.
- **Paired with [[theregister-ontario-clinical-ai-audit-2026-05-14|Ontario auditors finding clinical AI errors]]** the wiki now has both sides: vertical-AI deployment at scale (Abridge), and audit-side evidence that approval pipelines may be selecting for the wrong vendors (Ontario weighted accuracy at only 4% of vendor-selection criteria). The pair is the right shape for any VPE-evaluation conversation in the healthcare-AI vertical.

## Cross-references

- [[theregister-ontario-clinical-ai-audit-2026-05-14]] — Ontario Auditor General's audit of 20 AI scribe vendors; **9 of 20 fabricated treatments**, 12 inserted wrong drugs, 17 missed mental-health details. Counterweight to the Abridge volume narrative; reminder that volume ≠ accuracy.
- [[anthropic-finance-agents-2026-05-05]] — same-week vertical-AI thread from a horizontal lab; useful comparison surface.
- [[forbes-ai-50-2026]] — earlier Abridge mention ($830M funding snapshot); now superseded.
- [[brianlamanna-paraform-talent-density-2026-05]] — Abridge #37 on talent-density top-50.
- [[code-mode]] — "EHR as file system + agentic coding loop" is the cleanest cross-domain confirmation.
- [[ai-labor-market-impacts]] — Customer Service Reps and downstream-documentation roles are #2 on the Anthropic exposure ranking; Abridge is the deployed product side of that signal.

## Pages Updated

- [[companies/abridge]] (new — first dedicated wiki page on Abridge; healthcare vertical-AI; documentation → clinical intelligence layer; 100M visits, 250+ health systems, $5.3B valuation)
