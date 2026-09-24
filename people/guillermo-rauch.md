---
name: Guillermo Rauch
type: person
affiliation: CEO, Vercel; creator of Next.js and Socket.io
signal_sources: [twitter]
last_updated: 2026-09-24
---

## Who They Are

Guillermo Rauch is **CEO of Vercel** and the creator of **Next.js** and Socket.io — a platform voice rather than a lab or research one, which is what makes him useful here: he is arguing about **where agents should run**, not what they can do.

Paged 2026-09-24 on a second substantive surface. Flagged as a borderline create-candidate at lint 2026-09-10 (two surfaces, below bar); the [[rauchg-agent-anatomy-drives-2026-09-23|agent-anatomy thread]] is the first where he contributes a named framework rather than a product note.

## Notable Takes

- **The three components of an agent (2026-09-23)** ([[rauchg-agent-anatomy-drives-2026-09-23]]): *"All successful agents have 3 key components:* 🧠 **Brain** → model, harness (logic); 👐 **Hands** → tools, computer, browser; 🗃️ **Files** → memories, skills, repos." Named against real systems — Muse, Instinct, OpenClaw, Claude Code.
  **The placement is the contribution.** Every position on [[domain-specific-harness]] treats "harness" as one undifferentiated thing; Rauch cuts the agent along a different axis and puts the harness **inside the Brain, as logic, beside the model**.
- **Decompose or you cannot secure it**: *"Breaking apart the agent into these independent parts not only optimizes costs in a big way, it also massively improves security and auditability. I'd argue you can't even run a secure agent otherwise!"* Self-serving — he sells the components — and consistent with the [[ai-vulnerability-discovery|four agent-autonomy incidents]], every one of which is an agent reaching further than intended.
- **The honest description of current practice**: *"The 'easy' way is to throw all these in 1 stateful computer (a Mac Mini)… you keep it running all day with `caffeinate`."* An accurate and unflattering portrait of the orchestrator setups this wiki has captured.
- **Storage decoupling enables "dreaming"** — a nightly memory-consolidation cron that reads and writes files *"without booting up the agent's full computer."* Lands directly on the gap [[company-brain]] names: everyone builds the remembering part, nobody owns the forgetting part.

## How to Read Him

**Platform CEO with product in the argument.** Fluid compute, Workflow, Sandbox and Drives are all Vercel; the anatomy thread exists to launch Drives. The frameworks are usable on their own; treat cost and security claims as unevidenced assertions until someone outside Vercel measures them.

## Where to Follow

- X: [@rauchg](https://x.com/rauchg) · Vercel
- Related: [[domain-specific-harness]], [[loop-engineering]], [[company-brain]], [[ai-vulnerability-discovery]]

## Verification-pending

Cost and security claims for decomposed vs monolithic agents — no benchmarks published; Drives adoption beyond public beta.
