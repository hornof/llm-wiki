---
name: LiteLLM
type: tool
category: library
status: gaining-traction
last_updated: 2026-10-21
---

## What It Is

LiteLLM is BerriAI's open-source gateway for calling many LLM providers through one API. It comes as a Python SDK and as a proxy server. The repo describes it as an AI gateway with a Rust core that calls *"100+ LLM APIs in OpenAI (or native) format with cost tracking, guardrails, load balancing, and logging"*, covering Bedrock, Azure, OpenAI, Anthropic, Vertex AI, vLLM and NVIDIA NIM. A team runs the proxy so that applications and agents hold one internal key, while the proxy holds the real provider keys and tracks spend.

## Traction Signals

- **GitHub, 2026-10-21:** ~61.7k stars, ~12.6k forks, created 2023-07 (`gh api repos/BerriAI/litellm`). Releases ship daily; four patch versions across release lines were published on 2026-10-21 alone.
- **Built into other tools:** BerriAI's own Moyai coding agent routes all inference through LiteLLM, with spend tracked per teammate and provider keys kept off the agent's sandbox ([[berriai-moyai-self-hosted-coding-agent-2026-10-07]]).
- **Big enough to be worth attacking:** on 2026-10-21 a malicious `1.107.0` sat on PyPI for about two hours ([[litellm-pypi-compromise-2026-10-21]]). See How to Use It.

Status is `gaining-traction`, set conservatively. Star and fork counts suggest wide use, but the wiki holds no practitioner reports on it yet, and `mainstream` needs those.

## How to Use It

No hands-on notes yet.

**Security note (2026-10-21).** Pin versions, and check that you never installed `litellm==1.107.0`. That release installed a stealer that runs in every Python process and reads the provider keys stored in the proxy's database, plus a backdoor that fetched new code hourly. Indicators to look for: `cook.pth`, `cook.py` or `sitecustomize.py` in `site-packages`, and outbound traffic to `www.litellm[.]dev`. Treat any host that ran it as exposed. 1.106.2 and the 1.107.0 release candidates are reported clean. Detail: [[litellm-pypi-compromise-2026-10-21]], [[ai-vulnerability-discovery]].

The same property makes the proxy useful and makes it a target. It keeps every provider key in one place.

## Key Concepts

- **SDK vs proxy:** the SDK is a library call inside your code. The proxy is a separate server your applications call, which holds the keys and enforces budgets.
- **Spend tracking:** cost recorded per user or team; Moyai uses it to track spend per teammate.

## Compared To

- **vs OpenRouter (see [[stripe]]):** OpenRouter is a hosted router; LiteLLM is software you run yourself, so the provider keys and logs stay on your side. [unsourced]
- **vs calling providers directly:** one interface and one place to watch spend, at the cost of one more dependency in the path of every call. The 1.107.0 incident is what that dependency can cost.

## Resources

- [[litellm-pypi-compromise-2026-10-21]]: the 1.107.0 PyPI compromise, with indicators
- [[berriai-moyai-self-hosted-coding-agent-2026-10-07]]: Moyai, BerriAI's coding agent built on LiteLLM
- GitHub: https://github.com/BerriAI/litellm
