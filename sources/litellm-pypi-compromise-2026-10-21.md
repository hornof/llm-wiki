---
title: "LiteLLM 1.107.0 on PyPI compromised: credential stealer and backdoor"
type: source
medium: article
url: https://safedep.io/litellm-pypi-compromise-credential-stealer-backdoor/
ingested: 2026-10-21
---

## Summary

SafeDep's analysis (2026-10-21) of a malicious LiteLLM release. LiteLLM is BerriAI's Python proxy and SDK that puts many LLM providers behind one API. Version 1.107.0 was uploaded to PyPI at 11:39–11:40 UTC and removed by 13:40. All seven wheels and the sdist carried a credential stealer and an hourly backdoor. SafeDep thinks BerriAI's own private release pipeline built the wheels from attacker-modified source, but says only BerriAI's logs can confirm it.

## Key Claims / Takeaways

- **Affected:** `litellm==1.107.0` only. 1.106.2, 1.107.0rc1, rc2, `litellm-proxy-extras==0.4.110` and `litellm-enterprise==0.1.78` are reported clean.
- **How it got in:** one added line in the sdist's `pyproject.toml` (`data = "cook"`) installs a hidden folder into `site-packages`. The release *"does not match its tag"*, and no public GitHub Actions run built the wheels. A stolen PyPI token is rated less likely than a compromised maintainer or bot credential, or a private branch or mirror.
- **Stealer (`cook.pth` / `cook.py`):** runs in every Python process on the host. It takes SSH keys, AWS/Azure/GCP/Kubernetes credentials, CI secrets, browser passwords, GPG and TLS keys, environment variables, AI tool tokens and **the provider API keys stored in a LiteLLM proxy's database**. It sends them to `www.litellm[.]dev/healthcheck` and queries the AWS instance metadata service.
- **Backdoor (`sitecustomize.py`):** a detached daemon. Every hour it reads a domain from a GitHub file, re-runs the stealer, and downloads and runs whatever that server returns. The GitHub account was deleted by 13:40, but hosts that ran the daemon before then may already have received second-stage code.
- **Indicators:** `cook.pth`, `cook.py` or `sitecustomize.py` in `site-packages`; `/tmp/.pc_once_72129118c59f5636c0bb`; `/tmp/remote_code_loader.lock`; `PRIVCOLLECT_ACTIVE=1`; Python daemons with parent PID 1; traffic to `www.litellm[.]dev` or `169.254.169.254` from Python.
- **Not given:** download counts, and BerriAI's own account.

**Brief draft claim not used:** *"the third supply-chain hit on AI infra in six months (after Requests, Hugging Face model cards)."* The wiki holds no record of a Requests compromise, and the article cites no earlier LiteLLM or AI-infrastructure incidents.

## Pages Updated

- [[ai-vulnerability-discovery]]: new section
- [[litellm]]: new tool page
