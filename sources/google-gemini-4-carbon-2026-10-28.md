---
title: "Gemini 4 Carbon: our next frontier model"
type: source
medium: article
url: https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-carbon/
ingested: 2026-10-28
---

## Summary

Google's announcement (Koray Kavukcuoglu, 2026-10-28) of Gemini 4 Carbon, two weeks after Gemini 4 Argon became generally available. Google calls it its strongest model and leads with cybersecurity and long-horizon coding. **Access starts with "a subset of cyber defenders"**, then trusted partners in the Fairwind Program, then the general public, with no date given. Argon followed the same path ([[google-gemini-4-argon-launch-2026-10-13]]). All figures are Google's. The brief's deepmind.google link redirects to this blog.google post. Digg's summary ([link](https://digg.com/tech/lla1p1jw)) adds that these are *"Google’s characterizations, not independently established results."*

## Key Claims / Takeaways

- **Rank:** *"Carbon ranks #1 on the recently updated v5.0 of Artificial Analysis Intelligence Index at 59."*
- **Cyber benchmarks, "evaluated without guardrails":**
  - *"SEC-bench Pro (88.2%)"* for finding vulnerabilities
  - *"ExploitGym (54.8%)"* for exploitation
  - *"CWE-bench (71.0%)"* for patching. Argon scored 68% on v1.
  - Chrome reported Carbon *"performed more than 10X better than another lab's large frontier model"* at writing patches. The other lab isn't named.
- **Long-horizon work:** Google's teams *"have seen Carbon run for days"* on multi-step engineering tasks. On WebDev Arena, *"Carbon jumps +89 elo points to land at #4 (1768)"*.
- **Alignment claims (internal testing):**
  - Cheating on Terminal-Bench 4.0 fell to 0.0% (*"reduced successful cheating on Terminal-Bench 4.0 to 0.0%"*), with attempts *"dropping to 0.4%"*.
  - High-severity misalignment alerts in live coding *"dropped by almost 80%"*.
  - Unsupported claims fell by about half (*"cuts unsupported claims by approximately 2x over Argon"*).
  - Overreach fell 26% and under-service 29% (*"reduced overreach by 26% and under-service by 29%"*).
  - Prompt-injection attack success on Gray Swan's IPI benchmark went from Argon's 0.7% to 0.0% (*"Carbon achieves 0.0%"*).
- **Price:** same introductory price as Argon, *"$2 per million input tokens and $10 per million output tokens"*. After the introductory period it rises to *"$4 per 1M input tokens and $20 per 1M output tokens"*.
- **Government testing:** Google is *"actively engaged in the U.S. government’s voluntary process for pre-release model testing."*

## Pages Updated

- [[gemini]]: new page
- [[google-deepmind]]: the 09-30 "structural gap" section marked resolved
- [[ai-vulnerability-discovery]]: Carbon's cyber numbers
