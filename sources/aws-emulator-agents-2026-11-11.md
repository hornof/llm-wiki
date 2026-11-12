---
title: "AWS Emulator and the engineer's job when agents write the code"
type: source
medium: article
url: https://www.allthingsdistributed.com/2026/11/aws-emulator-and-the-engineers-job-when-agents-write-the-code.html
ingested: 2026-11-11
---

## Summary

A guest post by Swami Sivasubramanian on Werner Vogels' blog (2026-11-11) launching **AWS Emulator**, a local copy of AWS APIs that coding agents can test against. Agents built it themselves, working from AWS's public API models and checking against real AWS. The post's real subject is what an engineer's job becomes when agents write the code. Also covered: [[simon-willison|Willison]]'s link post (https://simonwillison.net/2026/Nov/11/aws-emulator/) and the GitHub repo `aws/aws-emulator`.

## Key Claims / Takeaways

- **What it is:** AWS Emulator *"gives coding agents a local copy of AWS to test against"*. Released under CC0.
- **How agents built it.** They start from fidelity tests, *"end-to-end customer scenarios devised from the public API models"*. *"The agents correct each test until it passes against real AWS, so the test records how AWS behaves. The agents then build the emulator until it passes that same test"*. Given one prompt, Kiro *"returned a passable first version of an SQS emulator in about 15 minutes."*
- **Scale.** Willison: *"29,684 commits in the first three weeks of the project."* AWS has *"over 200 services"*, too many to emulate by hand. The repo had about 2,000 stars on 2026-11-11 (GitHub API).
- **The lesson, from Sivasubramanian's own rebuild.** Rebuilding a replication engine that first took *"about four months"*, he *"supervised the agent for four nights before I saw that it had no way to check its results. Once it had a spec and a test environment, the rebuild took about two hours."*
- **The engineer's job:** *"to give them room to work on their own and to build the specs, tests, and merge gates that decide when that work is correct."* The merge gate here uses *"multiple security agents"* plus a general reviewer and *"deterministic checks that stop agents from touching code they are not supposed to."*
- **Known gaps are public.** The repo's *"things-that-do-not-work"* folder lists behaviors the agents found that don't yet match AWS.
- **Willison's caveat:** *"It currently requires Docker to run on macOS or Windows."*
- **For the owner:** a tested-against-reality local emulator is the missing piece for agent loops that call AWS. Try it before writing mocks. [Judgment.]

## Pages Updated

- [[amazon]] — Traction Signals
- [[agentic-engineering]] — new section on specs and test environments
