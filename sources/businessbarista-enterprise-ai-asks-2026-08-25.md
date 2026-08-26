---
title: "Alex Lieberman (@businessbarista) — the 10 most common AI-transformation asks from enterprises, ranked by frequency (2026-08-25)"
type: source
medium: twitter-thread
url: https://x.com/businessbarista/status/2092341102623834553
ingested: 2026-08-25
---

## Summary

[[alex-lieberman|Alex Lieberman]] (@businessbarista) publishes a **frequency-ranked demand-side taxonomy** of the 10 most common AI-transformation engagements his consulting practice gets from enterprises "right now." This is a rare real-world *receipt of what AI-engineering work enterprises actually buy* — directly owner-relevant as a map of the AI-engineering job market. Folds into [[ai-native-organizations]] (the enterprise-transformation demand curve) and cross-references [[ai-engineering-skills]] (the taxonomy maps almost 1:1 onto Ng's skills), [[ai-vulnerability-discovery]] (#4/#5 security), and [[mcp]] (#8 gateway). *(Single practitioner's book-of-business, self-reported ordering; a demand signal, not a market survey.)*

## The 10 asks (verbatim, in Lieberman's frequency order)

1. **AI Diagnostic / ROI Study** — identify opportunities for AI, estimate ROI by use case, prioritize investments, create an implementation plan. *(The most common ask is still "where do we even start" — diagnosis precedes build.)*
2. **Agentic Workflow Automation** — build agents, automations, and integrations that execute recurring business processes. *(The #2 ask and the most-requested build item in the comments — [[loop-engineering|loops]]/[[graph-engineering|graphs]] as the delivery unit.)*
3. **Architecture & SDLC Assessment** — review codebase and architecture, identify technical debt/risks, evaluate engineers' AI-workflow fluency, create a modernization plan.
4. **Security Testing & Patching** — test AI applications and agents for **vulnerabilities, data leakage, prompt injection, and misuse** ([[ai-vulnerability-discovery]], [[prompt-injection]]).
5. **Security Assessment** — identify security/privacy/compliance risks and recommend fixes.
6. **Code Modernization** — *"legacy tech stacks create drag that decreases speed/accuracy for agents"* — i.e., legacy code is now a **tax on agent performance**, not just human maintainability (the [[garry-tan|Tan]] *"systems of record must become harnesses"* claim from the [[businessbarista-harness-engineering-product-2026-08-24|same-week harness post]] applied to the codebase).
7. **Data Engineering** — data pipelines, integrations, migrations, search systems, knowledge systems ([[training-data-quality]], grounding).
8. **MCP Gateway** — controlled access to models, tools, and data through **authentication, routing, logging, and usage controls** ([[mcp]]) — the enterprise-governance layer over agent tool-use.
9. **Model fine-tuning** — post-training an LLM on a smaller targeted dataset for a verticalized task/domain. *(Ranked 9th of 10 — corroborates the [[end-of-finetuning|fine-tuning-is-de-emphasized]] thread: it's the least-common enterprise ask.)*
10. **Citizen SDLC** — give non-technical employees a **secure, governed process for turning AI prototypes into approved production applications** (the "citizen developer" pattern with a governance gate; pairs with the [[ai-native-organizations|Replit "self-driving company"]] guardrails-first framing).

## Key Claims / Takeaways

- **The ordering is the signal**: diagnosis (#1) and agentic automation (#2) lead; **two of the top five asks are security** (#4 testing + #5 assessment) — enterprise AI adoption is now security-gated, not capability-gated. Fine-tuning (#9) is near the bottom.
- **Comment-thread demand** skews hard to **#1 (diagnostic/ROI)** and **#2 (agentic automation)**, with #10 (citizen SDLC) and #9 (fine-tuning) also drawing repeated interest — the "where do we start + automate a process + let our people ship safely" cluster.
- Maps almost 1:1 onto [[ai-engineering-skills|Ng's AI-Engineering Skills]]: grounding-with-data (#7), agentic systems (#2/#8), operating-in-production/security (#4/#5), evals/ROI (#1). The demand-side taxonomy and the supply-side skills map are converging.

## Pages Updated

- [[ai-native-organizations]] — new section: the enterprise AI-transformation demand curve (10 ranked asks); security-gated adoption; fine-tuning near the bottom
- (Cross-referenced, not edited: [[ai-engineering-skills]], [[ai-vulnerability-discovery]])
