---
name: Gray Swan
type: company
focus: AI security and red-teaming
status: emerging
last_updated: 2026-11-03
---

## What It Is

**Gray Swan** is an AI security company that red-teams models and publishes a prompt-injection benchmark. Its CEO is Matt Fredrikson, and [[openai]] board member Zico Kolter appears with Fredrikson in the company's main interview. The wiki first saw the company through a Latent Space episode, *Red-Teaming after Mythos*, and later through Google citing its benchmark in two model launches.

*(Rewritten 2026-11-03 to remove automated-pass filler. The page used to count two separate signals on 06-23 and 06-24; both were the same Latent Space episode, listed by the brief on consecutive days.)*

## Traction Signals

- **2026-10-28: Google reports Gemini 4 Carbon at 0.0% attack success on Gray Swan's IPI benchmark**, down from Argon's 0.7% ([[google-gemini-4-carbon-2026-10-28]]).
- **2026-10-13: Google reports Gemini 4 Argon at 0.7% on the same benchmark** ([[google-gemini-4-argon-launch-2026-10-13]]). A frontier lab quoting a third party's benchmark in its launch post is a stronger signal than the interview. IPI is presumably indirect prompt injection, where the attack comes in through content the model reads rather than from the user [unsourced: neither source expands the name].
- **2026-06-23/24: Latent Space interview, *Red-Teaming after Mythos*** ([[dailybrief-roundup-2026-06-23]], [[dailybrief-roundup-2026-06-24]]). Kolter and Fredrikson on why AI security differs from traditional cybersecurity. The brief's summary was that AI security *"isn't just cybersecurity reskinned"*. That's the brief's wording, not a quote from the episode, which wasn't fetched.

## Key People

- **Matt Fredrikson**: CEO.
- **Zico Kolter**: on OpenAI's board, and in the interview alongside Fredrikson. The wiki hasn't captured Kolter's formal role at Gray Swan.

## How to Use It

The wiki has no hands-on notes. Its benchmark is the practical touchpoint: when a lab reports Gray Swan IPI numbers, they measure resistance to injected instructions in documents and tool output. See [[prompt-injection]].

## Compared To

- **Lab-internal red teams** ([[anthropic]], [[anthropic-public-record]]): Gray Swan is an outside firm whose benchmark labs cite.
- **[[metr]] and [[arena]]**: evaluation businesses measuring capability and preference. Gray Swan measures attack resistance.
- **Runlayer** ([[dailybrief-roundup-2026-06-24]]): runtime security for enterprise agents, not model red-teaming.

## Resources

- [[google-gemini-4-carbon-2026-10-28]] — Carbon at 0.0% on Gray Swan IPI
- [[google-gemini-4-argon-launch-2026-10-13]] — Argon at 0.7%
- [[dailybrief-roundup-2026-06-24]] — the Latent Space interview
- [[dailybrief-roundup-2026-06-23]] — the same episode, first listing
- [[latent-space]] — the podcast
- [[metr]], [[arena]] — other evaluation businesses
- [[prompt-injection]] — what IPI measures
