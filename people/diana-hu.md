---
name: Diana Hu
type: person
affiliation: Y Combinator (Group Partner)
signal_sources: [yc-rfs]
last_updated: 2026-05-01
---

## Who They Are

YC Group Partner. Authored **three** entries in [[yc-summer-2026-rfs]] — the most of any single partner — covering inference silicon, semiconductor supply chain, and the "AI Operating System for Companies." Background in deep tech / chip-adjacent infrastructure; this RFS positioning suggests strong technical depth at the silicon-and-systems layer.

## Their Current Focus

Funding founders at three adjacent gaps:

1. **Hardware for the agent regime** — chips designed for the agentic loop, not the prompt-in-response-out paradigm.
2. **Semiconductor supply chain tooling** — real-time allocation tracking, multi-tier risk monitoring, export compliance. The current state runs on spreadsheets, SAP, and phone calls.
3. **Closed-loop intelligence layer for companies** — make every meeting, ticket, and customer interaction queryable; turn the company from open loop to closed loop.

## Notable Takes

- **Inference chips for agents** ([[yc-summer-2026-rfs]] §11, April 2026): **"Most AI chips are designed for a world where inference means 'prompt in, response out.' Agents don't work that way."** Specific architectural needs called out: fast context switching between models, native speculative decoding, memory built for KV caches that persist across an entire execution graph. "NVIDIA bought Groq for $20 billion because it saw this coming. But nobody's designing for the agent loop itself."
- **Current GPUs at 30–40% peak utilization on agentic workloads** because the work is bursty — memory-bound model calls + I/O-bound tool use + CPU-bound orchestration. The compiler/scheduler matters as much as the silicon ("Groq's real insight wasn't the chip. It was the compiler that made the chip work").
- **AI Operating System for Companies** ([[yc-summer-2026-rfs]] §16, April 2026): **"Make their entire company queryable."** Every meeting recorded, every ticket tracked, every customer interaction captured, all legible to an intelligence layer. Closed-loop ↔ open-loop framing: "I've seen teams that do this cut sprint time in half and ship twice as much." Direct overlap with [[ashwingop]]'s [[company-brain]] thesis at [[sentra]] — two YC partners (Diana + [[tom-blomfield]]) independently named the same gap.
- **Supply Chain 2.0 for Semiconductors** ([[yc-summer-2026-rfs]] §15): "1,400 process steps, dozen countries, five months." Cites the 2021 chip-shortage incident where a $300 chip held up a $50,000 car and $210B in vehicles didn't get built. TSMC advanced packaging is the current AI-compute bottleneck; NVIDIA has locked >60%; HBM booked through 2026.

## Where to Follow

- YC page: https://www.ycombinator.com/people/diana-hu
