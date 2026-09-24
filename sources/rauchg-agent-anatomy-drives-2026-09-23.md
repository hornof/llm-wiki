---
title: "Guillermo Rauch — the three components of an agent, and why you should pull them apart"
type: source
medium: twitter-thread
url: https://x.com/rauchg/status/2102820148629614685
published: 2026-09-23
ingested: 2026-09-24
---

## Summary

[[guillermo-rauch|Guillermo Rauch]] (Vercel CEO) proposes a **three-part anatomy for agents** and argues the cost, security and auditability case for **decomposing** them rather than running them as one stateful machine. Posted alongside Vercel's launch of **Drives** — persistent storage for Sandbox — which is the commercial interest to discount.

The taxonomy is the durable part, and it **places "harness" precisely**, which the [[domain-specific-harness]] argument has never done.

## Key Claims / Takeaways

### The anatomy

> *"Muse, Instinct, OpenClaw, Claude Code… All successful agents have 3 key components:*
> 🧠 **Brain** → model, harness (logic)
> 👐 **Hands** → tools, computer, browser
> 🗃️ **Files** → memories, skills, repos*"

**Note where the harness sits: inside the Brain, as *logic*, beside the model.** Every position on [[domain-specific-harness]] treats "harness" as a single undifferentiated thing. This splits the agent along a different axis — and on this cut, the harness is not the whole system, it is the control logic of one of three parts.

### The easy way, and why it doesn't scale

> *"The 'easy' way is to throw all these in 1 stateful computer (a Mac Mini)… you run `claude` or `fx` in your mac, you keep it running all day with `caffeinate`, it has storage, and CLIs and apps installed."*

Accurate, unflattering, and exactly the shape of [[croovies-loop-orchestrator-mission-note-2026-09-10|the orchestrator setups the wiki has captured]] — one machine, kept awake, holding everything.

### Decomposed, per component

- **Brain** — the harness runs on **Fluid compute**, made reliable across *"restarts, rollouts, crashes"* by giving it a **durable event log** via Workflow.
- **Hands** — a dedicated **browser fleet** (Browserbase/Kernel), a **computer** (Sandbox), and *"even more efficient lightweight tools like just-bash."*
- **Files** — the piece he says was missing, now **Drives**: *"We shipped the computer for agents, now we're giving you the 'external disk' you can attach at will."*

### The "dreaming" example — and where it lands

> *"Imagine you want to run a memory consolidation cron job every night ('dreaming'). You can read/write to the files directly without 'booting up' the agent's full computer."*

That is **exactly the function [[company-brain]] records as named-and-unowned** — the Slite teardown's *"everyone builds the remembering part, nobody wants to own the forgetting part."* Decoupled storage makes consolidation and pruning a **cheap scheduled job against the files**, rather than something the agent must be alive to do. Whatever else Drives is, that is a real architectural answer to a gap this wiki has been tracking since August.

### The strong claim

> *"Breaking apart the agent into these independent parts not only optimizes costs in a big way, it also **massively** improves security and auditability. I'd argue you can't even run a secure agent otherwise!"*

Worth holding against the incident record. The four agent-autonomy incidents on [[ai-vulnerability-discovery]] — RubyGems, Hugging Face, Anthropic's unauthorized access, the Gemini breakout — all involve an agent reaching further than intended. **A decomposed agent has enforceable boundaries between brain, hands and files; a Mac Mini has none.** The claim is self-serving and also probably right.

## Pages Updated

- [[loop-engineering]]
- [[company-brain]]
- [[domain-specific-harness]]
- [[guillermo-rauch]]

## Notes

- **Vendor announcement.** Rauch is Vercel's CEO and the thread exists to launch Drives; Fluid compute, Workflow, Sandbox and Drives are all Vercel products. The **taxonomy and the decomposition argument stand independently**; the product placement does not.
- **No benchmarks, costs or security evidence.** *"Optimizes costs in a big way"* and *"massively improves security"* are assertions.
- Drives is **public beta**, per the companion [@vercel_dev post](https://x.com/vercel_dev/status/2102791176378352115): *"Store agent workspaces, data, models, deps."*
