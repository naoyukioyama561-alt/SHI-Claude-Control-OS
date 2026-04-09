# Glossary — Key Terms in This Repository
Language: [日本語版はこちら / Japanese version](ja/GLOSSARY-ja.md)

This glossary defines terms as they are used **in this specific repository**. Some terms have different meanings in other AI/ML contexts; where relevant, the distinction is noted.

---

## Core Concepts

| Term | Definition in this repository | Common alternative meaning | Where used |
|------|-------------------------------|---------------------------|------------|
| **Failure Mode (FM)** | A specific, observable pattern of AI misbehavior — classified with cause, prevention, and verification. Not a bug report. | General software failure category | 10-framework/01-failure-modes.md |
| **Control OS** | A set of rules pasted into an AI's system prompt to structurally suppress known Failure Modes. Not an operating system. | Operating system software | 30-adoption/try/control-os-*.md |
| **Three-layer separation** | Role split: Supervisor (judgment) / Relay (monitoring) / Worker (execution). Not a network architecture. | Network layer model | 10-framework/04-three-layer.md |
| **4+1 quality system** | Quality-control stack: Observation Gate + Layers 1–4 (output/process/judgment/structural). Not a software quality model. | ISO 9001, CMMI levels | 10-framework/05-quality-system.md |
| **5-layer governance loop** | Governance cycle: observation → correction → detection → pre-control → inheritance fixation. Not a replacement for 3-layer or 4+1. | — | 20-proof/achievements/05-five-layer-ops.md |
| **Heritage (cc_heritage)** | System for transferring behavioral norms, judgment criteria, and pain awareness from one AI session to the next. Not genetic inheritance. | ML model inheritance, transfer learning | 40-heritage/ |
| **SHI Theory** | Structural Hierarchical Intelligence — a theoretical framework treating AI failures as structurally observable phenomena. Not a product name. | — | 10-framework/07-shi-citations.md |

## Evidence Labels

| Label | Meaning |
|-------|---------|
| `[observed: single environment, single operator, N undisclosed]` | Measured in the author's operating environment. Not a public benchmark. Sample size is withheld. |
| `[design target: not a public benchmark]` | Intended architecture outcome. Not measured or independently reproduced. |
| `[illustrative example: not measured]` | Explanatory scenario for conceptual understanding. Not data. |
| `[non-public evidence: public summary only]` | Detailed implementation or measurement is intentionally withheld from the public version. |
| `[publicly inspectable in this repo]` | You can verify this directly from files in this repository. |

## Frequently Confused Terms

| Often confused | Actually different because |
|---------------|--------------------------|
| Three-layer separation vs. 5-layer loop | Three-layer = role split (who does what). 5-layer = governance cycle (how quality improves over time). They describe different dimensions of the same system. |
| Control OS vs. methodology | Control OS = a copy-paste template for immediate use. Methodology = the full structural framework including FM taxonomy, monitoring, heritage, and quality systems. |
| Observed vs. design target | Observed = actually happened in the author's environment. Design target = the architecture's intended capability, not yet independently measured. |
| Public repository vs. non-public reference material | Public repository = everything available in this GitHub repository. Non-public reference material = materials intentionally outside this repository's public evaluation surface. |

---

[日本語版 / Japanese](GLOSSARY-ja.md)


---

## Model Naming Note

Model names in this repository (Claude Opus 4.6, Claude Sonnet 4.6, GPT-5) refer to versions available during the observation period (late 2025 – March 2026). Current official model names may differ. When citing numbers from this repository, always include the observation period context.


---

→ [Back to README](README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
