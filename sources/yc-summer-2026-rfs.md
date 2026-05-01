---
title: Y Combinator Summer 2026 Requests for Startups
type: source
medium: article
url: https://www.ycombinator.com/rfs
ingested: 2026-05-01
---

## Summary

Primary source: Y Combinator's Summer 2026 Requests for Startups (RFS). Full transcript of all 15 categories with author attribution to YC partners. This page **replaces the placeholder content** in [[benln-yc-summer-2026-rfs]] (which was an image-only X post pointing at the same list) and supplies the actual RFS text.

YC's framing in the intro: **"AI has stopped being a feature and started being the foundation."** Several categories come directly from YC founders sharing what they're seeing on the frontier. The RFS is presented as "ideas we'd like to see founders tackle… you don't need to work on these ideas to apply to YC."

## The 15 Categories (with authors)

1. **AI for Low-Pesticide Agriculture** — [[garry-tan]] — AI vision + cheap sensors + precision robotics + RNA/peptide biology = "the company that cuts pesticide use by 90% and helps farmers grow more food is a generational company."
2. **AI-Native Discovery Engines** — Jon Xu — frontier models running closed discovery loops in drug discovery, materials science, protein engineering: propose → synthesize → test → analyze → iterate.
3. **AI-Native Service Companies** — [[gustaf-alstromer]] — *not* AI tools that help people do work but **AI companies that just do the work.** Total spend on services >> spend on software, and most services are already outsourced. Target categories: insurance brokerage, accounting/tax/audit, compliance, healthcare administration.
4. **AI Personalized Medicine** — Ankit Gupta — agents (explicitly cites [[claude-code]]) analyzing genome scans, EHR data, wearables; n-of-1 mRNA therapies; FDA more open. Population-level treatment → one patient, one protocol.
5. **Company Brain** — [[tom-blomfield]] — **the primary source for the "company brain" phrase.** "The biggest blocker to AI automation of companies is no longer the models, they just got so good so quickly. Now the blocker is the domain knowledge." Calls for "Garry's G-Brain, but for every business in the world": pulls knowledge from fragmented sources, structures it, keeps it current, **turns it into an executable skills file for AI.** Not company search, not chatbot-over-docs — "a living map of how a company works." See [[company-brain]] for the concept page; this is the primary citation behind it. — [[ashwingop]] / [[sentra]] is one practitioner positioning *toward* this RFS.
6. **Counter-Swarm Defense** — Tyler Bosmeny — A Patriot missile costs $3M, an FPV drone $500. Cost advantage sits with attackers. "Drone defense is looking less and less like operating a weapon and more like running a real-time distributed system. The winning companies will look more like Cloudflare than Raytheon."
7. **Dynamic Software Interfaces** — Ankit Gupta — coding agents are good enough that users become their own forward-deployed engineers; software ships **shared primitives** with full intention that users heavily modify the final interface. Email-as-task-list for one user, email-as-events-calendar for another, sharing underlying primitives. Resonates with [[model-rendered-ui]] (Flipbook prototype) and [[stitch]] (Google's open DESIGN.md spec for portable design rules).
8. **Electronics in Space** — Philip Johnston (Starcloud) — reusable rockets create demand for inference chips optimized for mass, thermal, and radiation. Calls out "if you're working at SpaceX or NVIDIA on chip design" — explicitly talent-targeted.
9. **Hardware Supply Chain** — Nicolas Dessaigne — Shenzhen design-to-part loop is days; US loop is weeks; gap compounds. Wants startups producing parts dramatically faster, enabling rapid hardware iteration, integrating design/manufacturing/logistics. Hlabs (W26 actuators), Prototyping.io (P26 mechanical parts in days) cited as early examples.
10. **Industrial Capabilities in Space** — Adi Oltean — moon as raw-materials base (silicon, aluminum, iron, titanium) via electrolysis and 3D-printing of regolith.
11. **Inference Chips for Agent Workflows** — [[diana-hu]] — most chips designed for prompt-in-response-out; **agents loop**: tools, branching, backtracking, holding context across dozens of steps. Current GPUs hit 30–40% peak utilization on agentic workloads (memory-bound model calls + I/O-bound tool use + CPU-bound orchestration). "NVIDIA bought Groq for $20 billion because it saw this coming. Google built TPU v7 for inference specifically. But nobody's designing for the agent loop itself: fast context switching between models, native speculative decoding, memory built for KV caches that persist across an entire execution graph." Resonates with [[chamath-decision-context-agents]] thesis on instrumentation-as-the-missing-layer.
12. **SaaS Challengers** — Jared Friedman — "AI has collapsed the cost of producing software by 10–100x"; the moat that protected legacy SaaS (millions of LOC built over decades) is gone. Targets the products that seem invulnerable: chip design software, ERPs, industrial control systems, supply chain management. Direct YC validation of the [[saas-disruption-thesis]] (Naval, April 2026).
13. **Software for Agents** — Aaron Epstein — "The next trillion users on the internet won't be people, they'll be AI agents." Agents need machine-readable interfaces (APIs, [[mcp]], CLIs), thorough documentation, programmatic discovery/sign-up. **"While everyone else is building agents, the biggest opportunity might be building the software those agents depend on."** Direct YC validation of MCP and agent-native infrastructure as a category.
14. **Startups That Want to Sell to Huge Companies** — Harshita Arora & Brad Flora — YC observing F100 buyers landing pilots and multimillion-dollar deals with companies inside the YC batch itself. AI has "changed the score on all three fronts" (executive willingness, small-team product depth, ROI tolerance for working with early-stage). Stealth-for-3-years strategy declared dead.
15. **Supply Chain 2.0 for Semiconductors** — [[diana-hu]] — single advanced AI chip = 1,400 process steps + dozen countries + five months. Currently managed via spreadsheets, SAP, phone calls. TSMC advanced packaging is the AI-compute bottleneck; NVIDIA has locked >60% of it; HBM booked through 2026; CHIPS Act fabs each starting from scratch.
16. **The AI Operating System for Companies** — [[diana-hu]] — **second YC primary source overlapping with the Company Brain framing.** "The best AI-native companies we're seeing have figured out something most haven't: they've made their entire company queryable. Every meeting recorded, every ticket tracked, every customer interaction captured, all legible to an intelligence layer that learns from it. This turns a company from an open loop into a closed loop." Notes brutal integration work as the current cost of building it. Direct overlap with [[ashwingop]]'s [[company-brain]] thesis at [[sentra]] — different YC partners (Tom Blomfield + Diana Hu) named the same gap from different vantage points within ~weeks of each other.

(Numbering 1–16 because YC labels these as a flat list; The VC Corner article ([[vccorner-yc-rfs-summer-2026]]) consolidates AI Personalized Medicine and AI-Native Discovery Engines into the count, hence the alignment difference.)

## Key Cross-Cutting Threads

- **Two RFS items converge on the [[company-brain]] thesis**: Tom Blomfield's "Company Brain" (#5) and Diana Hu's "The AI Operating System for Companies" (#16). Same diagnosis from different YC partners: companies need a queryable intelligence layer to unlock agentic automation. Direct primary-source validation of [[sentra]]'s positioning.
- **Agent infrastructure is now a YC-named category** (#13 Software for Agents) — gives [[mcp]] and the broader machine-readable-interface pattern explicit YC-level validation. Confirms the trajectory in [[playwright-mcp]] traction signals.
- **Service-replacement (not tool-augmentation) is the named SaaS-disruption shape** (#3 AI-Native Service Companies, #12 SaaS Challengers). Confirms [[saas-disruption-thesis]] (Naval) at YC partner level.
- **AI-for-science as discovery-loop infrastructure** (#2) maps directly onto [[ai-for-science]] — agents proposing/testing hypotheses end-to-end, not just assisting researchers.
- **Hardware/silicon for the agent regime** (#11 Inference Chips for Agent Workflows) — agents need different chip architectures than chat. Validates [[chamath-decision-context-agents]] adjacent thesis on instrumentation gaps.

## Pages Updated

- [[company-brain]] — added Tom Blomfield's RFS as **primary source** for the phrase; added Diana Hu's "AI OS for Companies" RFS as the second YC framing
- [[sentra]] — noted YC primary-source validation of the thesis from two RFS items
- [[ashwingop]] — context: which YC partners triggered the messages he received
- [[benln-yc-summer-2026-rfs]] — annotated as secondary; full RFS text now lives here
- [[saas-disruption-thesis]] — added YC SaaS Challengers RFS (Jared Friedman) as direct validation
- [[ai-native-organizations]] — added Gustaf Alströmer's AI-Native Service Companies RFS as primary source
- [[mcp]] — added Aaron Epstein's "Software for Agents" RFS as YC-level validation of the machine-readable-interface trajectory
- [[claude-code]] — Ankit Gupta's AI Personalized Medicine RFS explicitly names Claude Code as the agent harness for analyzing health data; added as traction signal
- [[tom-blomfield]] (new), [[garry-tan]] (new), [[diana-hu]] (new), [[gustaf-alstromer]] (new) — YC partners with substantive RFS authorship
- [[y-combinator]] (new) — company page (was previously implicit)
