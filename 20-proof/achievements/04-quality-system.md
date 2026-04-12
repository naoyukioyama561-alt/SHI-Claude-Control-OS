# Achievement No.4: Quality System (4+1 Layer Architecture)
Language: [日本語版はこちら / Japanese version](../../ja/20-proof/achievements/04-quality-system-ja.md)

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Public](https://img.shields.io/badge/availability-Public-blue)

## What Was Observed

In the author's environment [observed: single environment], a **quality system** was built on a 4+1 layer architecture:

| Layer | Name | Responsibility |
|-------|------|---------------|
| Layer 0 | **Observation Gate** | Pre-execution: observe current state, define target, get approval |
| Layer 1 | **Self** | Self-detection + immediate correction |
| Layer 2 | **Structure** | Hooks/watchers auto-detect + block |
| Layer 3 | **Completion Definition** | Evidence + 5-set inspection |
| Layer 4 | **Third-party Verification** | Pattern escalation + incident logging + learning control |

Additional components:
- **reason_code system**: Every quality issue is classified with a structured reason code
- **5-set mandatory inspection**: Preconditions, Prohibitions, Execution observation, PASS criteria, Rollback
- **Escalation chain**: Automated escalation from self-detection to structural blocking to third-party review

## What Was Observed to Hold

- Quality cannot be maintained by any single layer — it requires **cascading verification** where each layer catches what the previous misses
- The reason_code system transforms vague quality complaints into **actionable, trackable categories**
- The 5-set inspection makes "done" objectively verifiable, designed to prevent the common failure of "I think it's done" without evidence

## Key Insight (考え方のポイント)

> The following reflects what was observed in the author's environment:

The quality system was not designed theoretically — it **evolved through actual failures**. Each layer was added because real incidents proved the previous layers were insufficient.

The most important insight: **quality is not a checklist — it is a multi-layer defense** where each layer has a structurally different detection mechanism. Self-monitoring catches obvious errors; structural hooks catch what self-monitoring misses; completion definitions catch what hooks miss; third-party verification catches systemic patterns.

→ Full documentation: [`10-framework/05-quality-system.md`](../../10-framework/05-quality-system.md)

---

> For implementation details and data, see [SCOPE-MATRIX.md](../../SCOPE-MATRIX.md).

![Diagram showing 4+1 quality system architecture — conceptual design](../../images/diagrams/quality-system-4plus1.svg)


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
