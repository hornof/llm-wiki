---
name: Steve Yegge
type: person
affiliation: Independent / author of Gas Town (pre-AI: Google, Grab, Sourcegraph)
signal_sources: [github, blog]
last_updated: 2026-06-08
---

## Who They Are

Steve Yegge is a veteran software engineer (Amazon, Google, Grab, Sourcegraph) and longtime blogger best known pre-AI for the *Platforms Rant* and *Stevey's Drunken Blog Rants*. **First wiki entity surface 2026-06-08** via [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn's Loop Engineering synthesis]] as **author of [Gas Town](https://github.com/gastownhall/gastown)** — the **deep end of stage-5 multi-agent-orchestration loops** in the wiki-captured Loop Engineering lineage.

## Their Current Focus

**Gas Town** ([github.com/gastownhall/gastown](https://github.com/gastownhall/gastown); launched January 2026): open-source multi-agent Claude Code orchestration project.

Per [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn]]: *"twenty to thirty Claude Code instances coordinated by a Mayor agent, with patrol agents that run continuous loops and state stored in git so work survives a crash. That is the continuous orchestration loop that oversees other threads Trash Panda was reaching for, shipped and open source."*

**Architecture**:
- **20-30 Claude Code instances** running concurrently
- **Mayor agent** as the supervisor / coordinator
- **Patrol agents** running **continuous loops**
- **State stored in git** for crash-recovery durability
- **Open source** (verification-pending on license + recent commit activity)

**First wiki-captured concrete multi-agent-orchestration loop with named-role architecture (Mayor + Patrol)** — sibling pattern to [[zodchii-4-agent-pipeline-2026-05-30|zodchii's 4-agent pipeline]] (Planner/Coder/Tester/Reviewer):
- zodchii pattern: **discrete handoff** via `.pipeline/{spec,changes,test-results,review}.md` files
- Yegge pattern: **continuous + git-durable** supervised orchestration

## Notable Takes

- **Gas Town as continuous-orchestration-loop-shipped** (2026-01, via [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn]]): Mayor + Patrol multi-agent Claude Code architecture with git-backed durability. First wiki-captured public concrete instantiation of the *"loop supervising other loops"* pattern Van Horn identifies as stage 5 of the [[loop-engineering|Loop Engineering]] lineage.

## Where to Follow

- GitHub: [gastownhall/gastown](https://github.com/gastownhall/gastown)
- Wiki sources: [[mvanhorn-wtf-is-a-loop-2026-06-07]]
- Related concept: [[loop-engineering]]
- Pre-AI context: Platforms Rant, Stevey's Drunken Blog Rants

## Verification-pending

- Gas Town repo current state (commit activity, license, contributor count)
- Yegge's currently-stated affiliation (independent vs employed)
- Yegge's broader 2026 AI-coding-side voice presence beyond Gas Town
