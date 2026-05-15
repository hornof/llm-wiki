---
title: "Ontario Auditor General: AI scribes routinely fabricate clinical facts"
type: source
medium: article
url: https://www.theregister.com/ai-ml/2026/05/14/ontario-auditors-find-doctors-ai-note-takers-routinely-blow-basic-facts/5240771
ingested: 2026-05-15
---

## Summary

The Register, 2026-05-14, on the Office of the Auditor General of Ontario, Canada audit of **20 AI Scribe vendors approved for Ontario healthcare providers**. **Systemic factual-fabrication and missed-content findings across the audited vendor set.** Audit also flags an evaluation-methodology problem: vendor selection weighted **domestic Ontario presence at 30%, medical note accuracy at only 4%**, bias controls at 2%, security/privacy at 2%. **Over 5,000 physicians currently use the program**; Ontario Health Ministry spokesperson cites "no known reports of patient harms," but the audit findings suggest the harm-detection surface is itself under-instrumented. Direct counterweight to [[latentspace-abridge-healthcare-os-2026-05-15|Abridge's 100M-visit narrative]] — vertical-AI at deployed scale does not imply vertical-AI at acceptable accuracy.

## Key Claims / Takeaways

### Error rates across 20 audited AI Scribe vendors

- **9 of 20** systems **fabricated information** and suggested treatments **never discussed** in patient-doctor recordings
- **12 of 20** systems **inserted incorrect drug information** into patient notes
- **17 of 20** systems **missed critical mental-health details** mentioned during consultations
- **6 of 20** systems **partially or completely missed patients' mental health issues**

Example errors named in the audit: falsely documenting *"no masses were found"* or *"patients were anxious"* when these conditions were **never discussed**.

### The vendor-selection methodology problem

The audit identifies a fundamental flaw in how the 20 vendors were approved:

| Criterion | Weight |
|---|---|
| Domestic Ontario presence | **30%** |
| Medical note accuracy | **4%** |
| Bias controls | 2% |
| Security / privacy | 2% |

The audit's own framing: *"inaccurate weightings could result in the selection of vendors whose AI tools may produce inaccurate or biased medical records or lack adequate protection to safeguard sensitive personal health information."*

### Deployment scope

- **5,000+ physicians** currently use one of the approved scribes through OntarioMD.
- OntarioMD recommends **manual review** of AI-generated notes — but **no mandatory attestation feature exists in any approved system**. The defense-in-depth layer the procurement assumes is structurally absent from the tooling itself.

### Regulatory / remediation framing

The audit implicitly recommends **reweighting evaluation criteria** to prioritize accuracy and security over domestic-administrative factors. No specific corrective action timeline disclosed.

## Why It Matters

- **Direct counterweight to vertical-AI-at-scale narratives.** [[latentspace-abridge-healthcare-os-2026-05-15|Abridge's]] 100M-visit number says nothing about per-note accuracy. The Ontario audit is the first wiki-tracked **independent third-party accuracy audit** of clinical-AI scribes at any scale. Both signals are real; they need to be held simultaneously.
- **Vendor-selection criteria as the binding constraint.** The 4%-weight-on-accuracy finding is structurally important: even if individual vendors *can* hit clinical accuracy, the procurement process selects against the trait. Useful as a generalizable pattern — anywhere AI procurement leans on local-presence / fit-with-existing-systems weighting (most enterprise RFPs do), accuracy is structurally under-selected.
- **Hallucination-detection in deployed healthcare AI is the right concern.** *"Never discussed in patient-doctor recordings"* fabrications are the worst-case failure mode for ambient documentation (the surface area Abridge built on). The Ontario findings name a deployment-side reality that the [[concepts/verifiability-and-jagged-intelligence]] framework predicted: outputs that look right but cite non-existent inputs.
- **"No known reports of patient harms" is the wrong calibration anchor.** The audit findings imply the harm-detection surface — patient awareness of fabricated records, downstream-clinician audit of mid-visit AI output, EHR-level diff visibility — is itself absent. Useful future signal to watch for: when does the first harm event surface, and what telemetry surfaced it.
- **Healthcare-AI procurement-side governance is now a tracked surface** for the wiki, alongside the deployment-side ([[latentspace-abridge-healthcare-os-2026-05-15|Abridge]]) and policy-side ([[anthropic-labor-market-impacts-2026-03-05|labor-market]]) threads.

## Cross-references

- [[latentspace-abridge-healthcare-os-2026-05-15]] — vertical-AI-at-scale counterpoint; paired source.
- [[concepts/verifiability-and-jagged-intelligence]] — failure-mode framework; fabricated clinical content is a domain-specific instance.
- [[ai-labor-market-impacts]] — Customer Service Reps + downstream-documentation roles at #2 on the Anthropic exposure ranking; Ontario audit is the deployment-side accuracy ceiling.

## Pages Updated

- [[concepts/verifiability-and-jagged-intelligence]] (updated — Ontario audit added as the first independent third-party clinical-AI accuracy audit; 9/20 vendor fabrication rate; vendor-selection-weighting-as-binding-constraint framing)
