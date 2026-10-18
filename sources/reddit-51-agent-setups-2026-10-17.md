---
title: "I collected 51 AI agent setups people actually use — what I found"
type: source
medium: reddit-post
url: https://www.reddit.com/r/AI_Agents/comments/1x8i1fj/i_collected_51_ai_agent_setups_people_actually/
ingested: 2026-10-18
---

## Summary

r/AI_Agents post (2026-10-17) summarising 51 agent setups the poster says people kept running, collected from Reddit, X, blogs, Substack and GitHub. It names three examples and five shared traits. In the comments the poster discloses they run Agent Cookbooks (agentcookbook.dev), a free directory of the 51. The comment thread has more useful detail than the post, especially on a shared log written by several agents.

## Key Claims / Takeaways

- **Three named setups** (originals linked by the poster):
  - **Boris Tane:** Claude Code writes `research.md`, then `plan.md` with file paths and snippets. He annotates the plan and sends it back up to six times before any code is written.
  - **Wyndo and Dheeraj Sharma:** Claude Code and Codex share a `changes.log`. Each reads the last entry before starting and appends one when done, so the second agent ends up reviewing the first.
  - **Noah Hailegiorgis:** an n8n email triage setup. It auto-sends only low-risk replies and drafts the rest for one-click approval. Self-reported drop from about 3.5 hours a day in email to about 30 minutes.
- **Shared traits across the 51:** narrow jobs; drafts instead of sends, PRs instead of merges; handoffs in a file; a different agent reviews the work; monitors stay quiet unless a threshold is crossed.
- **From the comments:**
  - One commenter runs six agents that read the last 25 lines of a shared file before each run. Two jobs have overlapped twice and *"both answered the same person."* The file is append-only, which has protected the history but not prevented the duplicate action. Anything that has to last goes into each agent's own playbook; the shared file is only for passing news.
  - Another commenter's suggested fix: claim the work atomically on the conversation ID before acting, and record completion separately so a crashed worker doesn't hold the claim forever.
  - A third commenter: *"treat every entry as a claim."* Their reviewer agent checks the running system (logs, the actual page), *"never the other agent's 'done'."*
- **Caveats:** the poster runs the directory the post promotes. "Dropped anything I couldn't trace back to a real person" is not checkable from the post. Other commenters call several replies AI-written.

## Pages Updated

- [[agentic-engineering]] — new section on what production setups have in common
