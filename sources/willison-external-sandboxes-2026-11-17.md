---
title: "External sandboxes for coding agents (Willison) and Daniel Stenberg on the curl rewrites"
type: source
medium: article
url: https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/
ingested: 2026-11-20
---

## Summary

Two Simon Willison posts from the 2026-11-19 brief. The 2026-11-17 link post introduces the "external sandbox" pattern, built with Prime Radiant: the agent runs outside the sandbox and sends only the code it wants to execute into it. The 2026-11-18 [quotation post](https://simonwillison.net/2026/Nov/18/daniel-stenberg/) quotes curl maintainer Daniel Stenberg on agent-made Rust rewrites of curl. Willison's longer post on the Prime Radiant blog was not read.

## Key Claims / Takeaways

- **The pattern:** *"code executed by the agent runs inside a dedicated sandbox while the agent itself lives outside of that sandbox."* The aim is to make it *"safer to try out local models without worrying that a mistake or prompt injection attack might cause them to take damaging actions on a machine."*
- **Three implementations, one localhost API:** v86 (Alpine Linux in WebAssembly, via Node.js), Apple Containers, and Microsoft's Quicksand (QEMU and Alpine in a Python package). Pi, Claude Code or Codex can be pointed at it.
- **Network and secrets:** an optional HTTP/HTTPS allow-list proxy, plus *"a credential replacement mechanism to make authenticated API calls without sharing a secret with the agent."*
- **Stenberg on the rewrites:** while agents *"converted 185,000 lines of C code into 340,000 lines of Rust code (I counted), we merged over 300 commits in the actual curl project."* Over a little more than three weeks: *"A little over 200 bugfixes actually. 200 bugfixes that none of those rust rewrites have."* His question: *"Will these clones keep up?"*

## Pages Updated

- [[simon-willison]] — external sandboxes; the Stenberg quote
- [[prompt-injection]] — sandboxing the code an agent runs
