---
title: "Karpathy moved on from vibe coding. Here's Everything About Agentic Coding."
type: source
medium: reddit-post
url: https://www.reddit.com/r/AIAgentsInAction/comments/1t2n3xz/karpathy_moved_on_from_vibe_coding_heres/
ingested: 2026-05-03
---

## Summary
Reddit post on r/AIAgentsInAction (May 3, 2026) by user BoringContribution7 popularizing Karpathy's vibe-coding-vs-agentic-engineering distinction for a practitioner audience. Adds a coined term ("cognitive debt"), three concrete failure modes for vibe coding at scale, and a 4-step practical workflow. The post itself is third-party — it summarizes [[karpathy-vibe-coding-agentic-engineering]] without quoting Karpathy directly. Comments reveal a notable practitioner-skepticism signal: multiple top responses dismiss the post as "AI slop" or "too much to read," even though the underlying framing is Karpathy's.

## Key Claims / Takeaways

### Distinction (restated from Karpathy)
- "Vibe coding is YOLO, agentic engineering is *agent builds, human owns.*" — clean one-liner reformulation of the [[vibe-coding]] / [[agentic-engineering]] split.
- Same tools, different operator.

### Why vibe coding breaks at scale — three named failure modes
1. **Security holes compound** — concrete numerical claim: an agent writing 1,000 PRs/week at a 1% vulnerability rate ships 10 new vulnerabilities every week. Vibe coding has no gate because the human isn't reading the diffs.
2. **Architecture rots** — skipping design means three months later "nobody can explain why the codebase is shaped the way it is. There's no reasoning to follow because no reasoning happened."
3. **Context collapses** — long sessions degrade; agent loses track of earlier decisions; code starts contradicting itself; developer never catches it because they aren't reading diffs.

### "Cognitive debt"
The accumulated cost of poor agent management, lost context, and unreliable behavior. Author claims vibe coding produces it faster than any prior workflow. Novel coinage in this post — not from Karpathy's primary source.

### 4-step practical workflow (the substantive how-to)
1. **Write the spec before prompting anything** — what the feature does, edge cases, data model, what can break. The step vibe coders skip.
2. **Break it into scoped tasks** — "Build me an auth system" is a vibe prompt; "Implement password reset using existing Resend integration, store token in Redis with 15-min TTL, here's the spec" is a scoped task.
3. **Review the diff like it's a human PR** — "If you can't explain what a module does, it doesn't merge."
4. **Test before shipping** — tests you wrote or reviewed, not tests the agent generated and you skimmed.

### Three habits framing
- Write a spec before every agent task (even one paragraph of bullets).
- Read every diff. If the agent changed 200 lines, you read 200 lines.
- Run the tests before calling anything done.

### Practitioner sentiment from the comments (signal)
- "Too much to read. Methinks you are compensating." (+2)
- "Its AI spam so they didn't think at all" (+2)
- "Reads like ai slop from a non software engineer." (+3)
- "Boring, for sure." (+1)
- "It's all the same thing" (dismissive of the entire distinction)
- One dissent in the other direction: "With good setup (agents instructions, automated tests) there's no need to think about architecture and control everything, and you still get a high quality solution created." — practitioner pushing back *toward* vibe coding being viable with the right scaffolding.

The comments are valuable practitioner-sentiment data: even when the underlying framing is correct (Karpathy's), AI-formatted summaries in agent-focused subreddits are being rejected on stylistic grounds. The Karpathy distinction is propagating *as ideas* but the format is hitting community antibodies.

## Pages Updated
- [[vibe-coding]] (added: three-failure-mode framing, cognitive-debt coinage, practitioner-skepticism note)
- [[agentic-engineering]] (added: 4-step practical workflow, propagation signal)

## Pages Created
- (none — all relevant concept pages already existed)
