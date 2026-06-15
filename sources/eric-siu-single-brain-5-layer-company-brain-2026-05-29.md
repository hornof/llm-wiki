---
title: "Eric Siu (Single Grain CEO) — Single Brain 5-layer Company Brain architecture (Capture + Retrieval + Source Truth + Permissions + Feedback) + Single Grain implementation metrics (2026-05-29)"
type: source
medium: twitter-thread
url: https://x.com/ericosiu/status/2060415100603781497
ingested: 2026-06-15
---

## Summary

**Eric Siu** (Single Grain CEO; Single Brain founder) publishes (2026-05-29; saved as `_raw/How we built a Single Company Brain (and how you can too).md`) **"How we built a Single Company Brain (and how you can too)"** — **canonical 5-layer Company Brain architecture** (Capture + Retrieval + Source Truth + Permissions + Feedback) + concrete Single Grain implementation metrics (**500K+ tokens persistent memory + 90+ daily crons + 2,862 Gong call transcripts + 15-calls-→-390-insights-470-facts-125-frameworks daily-ingestion proof-point**). **First wiki-captured Eric Siu + Single Brain entity surfaces**. **2nd substantive vendor surface in the Company Brain space** (extends [[ashwingop-company-brain-year-lessons-2026-05|Sentra/Ashwingop year-of-design-partner-work]]). **First wiki-captured "memory is raw material; retrieval is the operating layer" canonical Company-Brain architectural-principle articulation**. **First wiki-captured 5-layer canonical Company-Brain stack** (Capture + Retrieval + Source Truth + Permissions + Feedback) — pairs structurally with [[concepts/company-brain|Sentra 3-layer canonical-architecture]] (Factual Memory + Context Graph + Action Coordination) at the **2-vendor canonical-Company-Brain-architecture cluster** layer.

## Key Claims / Takeaways

### The author + product

- **Author**: Eric Siu (Single Grain CEO; Leveling Up newsletter ~14,000+ subscribers; Single Brain founder)
- **Company**: **Single Grain** (marketing agency; Single Brain product spin-off)
- **Product**: **Single Brain** ([singlebrain.com](https://www.singlebrain.com/)) — Company Brain-as-a-Service for businesses
- **Original post date**: 2026-05-29
- **Wiki-captured ingestion date**: 2026-06-15 (3 weeks after publication; surfaces via cross-device clipping)

### The 5-layer canonical Single Brain architecture

| Layer | Function | What it captures |
|---|---|---|
| **1. Capture** | Raw material ingestion | Calls + CRM activity + content decisions + internal SOPs + agent outputs + daily logs + corrections from humans |
| **2. Retrieval** | Right-context-at-right-time | Agent gets **6 pieces of context that matter for the task in front of it** (not entire history) |
| **3. Source Truth** | Which-source-wins discipline | Live truth + historical context + inspiration + never-public + pattern-only categorization |
| **4. Permissions** | Workflow-level access boundaries | Per-workflow access: marketing-agent ≠ private-HR-details; content-agent ≠ client-financials |
| **5. Feedback Loops** | Corrections → rules | Every human correction becomes future agent behavior (voice rule + source rule + pipeline rule + workflow rule) |

**First wiki-captured 5-layer canonical Single-Brain stack**. **First wiki-captured "right-context-now layer" vs "raw material layer" canonical Company-Brain architectural-distinction**.

### Why this is structurally MAJOR

- **First wiki-captured Eric Siu + Single Brain entity surfaces**
- **2nd substantive vendor surface in the Company Brain space** (extends [[ashwingop-company-brain-year-lessons-2026-05|Sentra/Ashwingop year-of-design-partner-work]] + [[ashwingop-company-brain-part-1]] + [[ashwingop-company-brain-part-2]]) — validates Company Brain as **multi-vendor canonical-category**, not single-vendor positioning
- **First wiki-captured "memory is raw material; retrieval is the operating layer" canonical Company-Brain architectural-principle articulation** — pairs structurally with [[ashwingop-semantics-ontology-2026-05-07|Sentra substrate-vs-lens framing]] at the **2-vendor architectural-principle convergence** layer
- **First wiki-captured 5-layer canonical Company-Brain stack** — adds **Source Truth** + **Permissions** + **Feedback** as explicit-layer architectural-categories beyond [[concepts/company-brain|Sentra 3-layer]] (Factual Memory + Context Graph + Action Coordination)
- **First wiki-captured concrete Company-Brain implementation-metrics** at agency-scale: 500K+ tokens persistent memory + 90+ daily crons + 2,862 Gong call transcripts processed + 15-calls-→-390-insights-470-facts-125-frameworks single-day proof-point
- **First wiki-captured "memory-as-bottleneck failure-mode" canonical articulation**: *"persistent memory files started eating about 40% of the context window. Agents had more information, but they weren't always pulling the right information at the right time. The system was technically smarter, but operationally much messier."* — concrete operator-side failure-mode evidence
- **First wiki-captured "confident liars with better formatting" canonical agent-failure-mode framing** — articulates the **source-trust-without-hierarchy failure-mode**: *"If you don't answer that, your agents become confident liars with better formatting."*

### Single Grain implementation metrics (proof-point anchor)

| Metric | Value | Context |
|---|---|---|
| Persistent memory size | **500K+ tokens** | Across full system |
| Daily crons | **90+** | Continuous-background processing |
| Specialized agents | **Multiple** (specific count verification-pending) | — |
| Gong call transcripts processed | **2,862** | Into operational playbooks |
| Single-day ingestion proof-point | **15 calls → 390 insights + 470 facts + 125 frameworks** | Single day from 15 calls |
| Old weekly-reporting loop | **~25 min data pulling + hours of follow-up** | Pre-Single-Brain |
| New weekly-reporting loop | **< 60 seconds** | Post-Single-Brain |

**First wiki-captured concrete agency-scale Company-Brain implementation-metrics**. **First wiki-captured "latency collapse" quantitative anchor** (25-min-and-hours → < 60-seconds canonical metric). Pairs structurally with [[ashwingop-company-brain-year-lessons-2026-05|Ashwin "pace-not-automation" canonical framing]] at the **latency-collapse-as-load-bearing-Company-Brain-outcome** layer.

### The "broken vs working" canonical diagrams

**Broken architecture** (per Eric Siu):
```
Call transcript → Random notes → Human remembers → Agent starts cold → Human re-explains
```
**First wiki-captured "human-as-router" canonical Company-Brain-failure-mode articulation**: *"The human becomes the router. Every agent output depends on whether someone remembered the right call, copied the right note, pasted the right context, or corrected the same mistake for the fifth time."*

**Working architecture** (per Eric Siu):
```
Calls ─────┐
CRM ───────┼──► Retrieval ─► Agent ─► Work
SOPs ──────┤        ▲          │
Slack ─────┘        │          ▼
             Human correction ─► Rule
```
**First wiki-captured "human-correction → rule" canonical feedback-loop architectural pattern** — extends [[concepts/recursive-self-improvement|RSI]] + [[zodchii-4-agent-claude-code-roster-2026-06-14|Zodchii canonical-discipline-rules]] at the **operator-side per-correction-rule-generation canonical-pattern** layer.

### "A call is no longer just a call" canonical reusable-intelligence framing

Per Eric Siu, with the 5-layer architecture, a call becomes:
- An objection library
- A sales training input
- A positioning signal
- A content idea source
- A CRM risk flag
- A future agent instruction

**First wiki-captured "single-artifact → multi-purpose-reusable-intelligence" canonical Company-Brain value-creation framing**. Pairs structurally with [[ashwingop|Sentra Universal-Substrate-Multiple-Ontologies]] at the **multiple-ontologies-over-shared-substrate convergence** layer.

### The "6 questions" canonical audit-framework

Eric Siu articulates **6 questions to audit before automating a workflow**:

1. What sources does this workflow depend on?
2. Which source is the truth when they conflict?
3. What context does the agent need every time?
4. What context should the agent never see?
5. What human corrections happen repeatedly?
6. How does one correction become a future rule?

*"If you can't answer those, you're not ready to automate the workflow yet. You'll just make the mess faster."*

**First wiki-captured 6-question canonical-audit-framework for Company-Brain-enabled workflow-automation readiness**. **First wiki-captured "you'll just make the mess faster" canonical operator-side automation-readiness-discipline articulation**.

### Cross-cutting framings

- **First wiki-captured Eric Siu + Single Brain entity surfaces**
- **2nd substantive vendor surface in the Company Brain space** (validates multi-vendor canonical-category)
- **First wiki-captured 5-layer canonical Single-Brain stack** (Capture + Retrieval + Source Truth + Permissions + Feedback)
- **First wiki-captured "memory is raw material; retrieval is the operating layer" canonical architectural-principle**
- **First wiki-captured concrete Company-Brain implementation-metrics at agency-scale** (500K+ tokens + 90+ crons + 2,862 transcripts + 15-→-390-470-125 single-day proof-point)
- **First wiki-captured "memory-as-bottleneck failure-mode" canonical articulation** (40% context window eaten)
- **First wiki-captured "confident liars with better formatting" canonical agent-failure-mode framing**
- **First wiki-captured "human-as-router" canonical Company-Brain-failure-mode articulation**
- **First wiki-captured "human-correction → rule" canonical feedback-loop architectural pattern**
- **First wiki-captured "latency collapse" quantitative anchor** (25-min-and-hours → < 60-seconds canonical metric)
- **First wiki-captured "single-artifact → multi-purpose-reusable-intelligence" canonical Company-Brain value-creation framing**
- **First wiki-captured 6-question canonical-audit-framework for Company-Brain-enabled workflow-automation readiness**
- **First wiki-captured "you'll just make the mess faster" canonical operator-side automation-readiness-discipline articulation**
- **First wiki-captured "the companies that win with AI won't be the ones with the biggest prompt library; they'll be the ones with the cleanest intelligence layer" canonical Company-Brain-as-competitive-moat framing**

## Pages Updated

- [[concepts/company-brain]] — Single Brain 5-layer architecture added as 2nd canonical-vendor-articulation alongside Sentra 3-layer; latency-collapse quantitative anchor; 6-question audit framework
- [[eric-siu]] — new entity-page candidate (single-source defer; Single Grain CEO + Single Brain founder + Leveling Up newsletter)
- [[single-brain]] — new entity-page candidate (single-source defer; Company-Brain-as-a-Service product)
- [[single-grain]] — new entity-page candidate (single-source defer; marketing agency; Single Brain originator)
- [[ashwingop]] — paired 2nd-vendor canonical-Company-Brain-architecture-articulation context
- [[ashwingop-company-brain-year-lessons-2026-05]] — pairs as multi-vendor architectural-principle convergence
- [[concepts/recursive-self-improvement]] — paired correction → rule canonical feedback-loop architectural pattern
- [[zodchii-4-agent-claude-code-roster-2026-06-14]] — paired canonical-discipline-rules layer
- [[ai-native-organizations]] — paired learning-loop-as-org-design canonical pattern

## Adjacent sources

- [[ashwingop-company-brain-year-lessons-2026-05]] — 1st substantive vendor surface in Company Brain space (Sentra year-of-design-partner-work)
- [[ashwingop-company-brain-part-1]] + [[ashwingop-company-brain-part-2]] — Sentra 3-layer canonical architecture
- [[ashwingop-semantics-ontology-2026-05-07]] — Sentra substrate-vs-lens framing
- [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14]] — Nadella firm-tier learning-loop-architecture (private evals + private RL environments + knowledge base)
- [[levie-nadella-cognitive-loop-thread-2026-06-14]] — Levie applied-AI-layer framing
- [[gregisenberg-theo-tabah-ai-native-masterclass-2026-06-08]] — Greg Isenberg "moat is the system" canonical-pattern
- [[ai-native-organizations]] — Jack Dorsey "rebuild-vs-copilot" + Block-org-design context

## Verification-pending

- Specific Eric Siu founding-story for Single Brain (when launched? Pre-funding? Sentra-vintage?)
- Specific Single Brain pricing + customer-base + deployment scale
- Specific Single Grain → Single Brain product spin-off business arrangement
- Specific Single Brain technical architecture (vector-DB + LLM-stack + IPC + state-management)
- Specific Single Brain vs Sentra competitive-positioning
- Specific Eric Siu vs Ashwin Gop architectural-philosophy differences
- Specific Single Brain "90+ daily crons" technical-detail (which agents? Which workflows? Which scheduling?)
- Specific "2,862 Gong call transcripts" methodology + ingestion architecture
- Specific Single Brain license / open-source / commercial model
- Specific Single Brain enterprise-deployment friction-points (per [[kpmg-pulls-ai-report-hallucinations-2026-06-13|KPMG hallucination retraction]] context)
