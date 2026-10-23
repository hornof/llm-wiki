---
title: "LLMs are making formal software verification feasible at a much larger scale"
type: source
medium: article
url: https://www.anthropic.com/research/formal-verification
ingested: 2026-10-22
---

## Summary

Research post (2026-10-22) from [[anthropic]]'s Frontier Red Team, with Theorem (theorem.dev). Authors include Nicholas Carlini and Nickolai Zeldovich. Claude wrote machine-checked proofs, checked by the Rocq kernel, that the OSS-Fuzz entry points of **123 open-source libraries (239 entry points)** can't crash. The proofs work on compiled RISC-V binaries, against specs converted automatically from the projects' own fuzz tests. The proof attempts surfaced **hundreds of bugs**.

## Key Claims / Takeaways

- **Scale:**
  - ~180M lines of Rocq in total; a typical proof is ~600k lines.
  - The median binary is 18k RISC-V instructions.
  - Inputs up to 64 MB.
  - The work took "a few weeks".
- **Bugs found:**
  - A counter underflow that needs ~20 MB of input.
  - An out-of-bounds read that needs 64 MB of input and over 2 GB of memory.
  - A rediscovered libexpat CVE.
  - A logic bug in a widely used application, latent for more than a decade.
  - On a PDF reader, "as many security bugs in one week as are typically reported in a year."
- **Other case studies:**
  - zlib on x86, using Claude-written x86 semantics.
  - A Rust Python interpreter verified in Verus. It matched CPython on 99.95% of 1.7M random programs.
- **Token efficiency:** Opus 5.5 proved half of 36 small tasks with ~40% fewer tokens than Opus 5. Agents sharing a proof workspace used 17% fewer tokens than agents working alone.
- **Stated limits:**
  - A proof can take hundreds of millions of tokens.
  - Verified isn't bug-free: the spec and machine semantics have to match reality.
  - The proofs assume static musl binaries, while most users run dynamic glibc builds on x86 or ARM.
  - Not every entry point was covered.
  - Reward hacking was a risk; patches were penalized and audited.
- **Released:**
  - Some of the proofs (theorem-labs/oss-verify-proofs).
  - The RISC-V/Linux semantics (theorem-labs/rocq-linux-process-semantics).
  - A Claude skill (theorem-labs/oss-verify).
  - Proofs that would reveal unpatched bugs are withheld.
- *Vendor's own results. Nothing has been independently replicated, but the proofs are machine-checkable by design, and that's the point.*

## Pages Updated

- [[anthropic]]: Key Research Contributions
- [[ai-vulnerability-discovery]]: 10-22 section
- [[verifiability-and-jagged-intelligence]]: an oracle you build, 10-22
