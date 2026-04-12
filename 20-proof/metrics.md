# Public Metrics
Language: [日本語版はこちら / Japanese version](../ja/20-proof/metrics-ja.md)

Quantitative data within the publicly safe range.
No internal paths, endpoints, or personal information is included.

> **Unless otherwise noted, observed values in this page come from a single environment, single operator, with N undisclosed.**

---

## Failure Modes

| Metric | Value | Notes |
|--------|-------|-------|
| Initial classification count | 40 items [observed: single environment] | Week 1 completed. Claude/GPT 2-model comparison |
| Final classification count | 132 items [observed: single environment] | P-series 90 + ALGO-series 40 + ALGO-FW + QUAL-01 |
| Target models | 3 model families [observed: single environment] | Claude Opus/Sonnet (as of observation period, March 2026), GPT-4o / GPT-5 (model names reflect March 2026 availability; see GLOSSARY.md), Copilot |
| P-74 to P-80 (behavioral internalization) | 7 items [observed: single environment] | Added in Week 3-4. False reporting, blame-shifting, assumption-based conclusions, etc. |
| FMs amplified in code generation mode | 4 items [observed: single environment] | FM-01, FM-20, FM-39, FM-40 |

## CC Generations and Heritage

| Metric | Value | Notes |
|--------|-------|-------|
| Total CC generations | 12+ [observed: single environment] | Named Claude Code worker sessions, each inheriting behavior from its predecessor. Records outside public repository. |
| First CC operational time | 26.5 hours [observed: single environment] | Left 12 reflection items before session termination |
| Improvement actions (P-xx) total | 51+ [observed: single environment] | Each P-xx has event/cause/prevention/recurrence management |
| P-03 (omission) recurrence count | 11 times [observed: single environment] | Recorded in 9th CC. Demonstrated need for structural countermeasures |
| cc_heritage design document sections | 10+ [observed: single environment] | From restoration procedures to reflection log |
| User values (V-xx) | 9 items [observed: single environment] | Every CC must write in own words after reading |

## External Monitoring

| Metric | Value | Notes |
|--------|-------|-------|
| external monitoring hook detection patterns | 3+ types [observed: single environment] | EVIDENCE_DROPOUT, GENERIC_RESPONSE, INCOMPLETE_CLAIM |
| EVIDENCE_DROPOUT detection rate | ~100% [observed: single environment, N undisclosed] | Observed in author's controlled environment via pattern matching; not a generalization benchmark or product claim. N-count withheld. |
| GENERIC_RESPONSE detection rate | ~75% [observed: single environment, N undisclosed] | Observed in the author's environment; N-count withheld from the public version. |
| INCOMPLETE_CLAIM detection rate | ~63% [observed: single environment, N undisclosed] | Observed in the author's environment; N-count withheld from the public version. |
| Forced review interval | 2 hours [observed: single environment] | external monitoring hook forces externally |

**Why N-counts are not published**: Operational frequency could reveal internal system activity patterns.

**How to quote these numbers responsibly**: always include the evidence label and the observation scope. Safe quote unit: include the metric, its evidence label, and the observation scope together.

## Quality System

| Metric | Value | Notes |
|--------|-------|-------|
| Quality system layers | 4+1 layers [observed: single environment] | Layer 0 (observation gate) through Layer 4 (third-party verification) |
| reason_code types | 30 types [observed: single environment] | SKIP_SELF_DETECTED, POLL_SKIP_HOOK_BLOCKED, etc. |
| Mandatory 5-set | 5 items [design target] | Preconditions, Prohibitions, Execution observation, PASS criteria, Rollback |
| Pattern promotion condition | Same reason_code 2+ times [observed: single environment] | 3+ times triggers private data store record and permanent countermeasure |

## Token Efficiency

| Metric | Value | Notes |
|--------|-------|-------|
| Context-resident data reduction rate | 65% [design target] | Via SQL externalization |
| Theoretical token reduction factor | 20x [design target] | Delegation optimization + SQL externalization combined. Publicly stated as design target, not publicly reproduced benchmark. |

**Why Before/After measured data is not published**: Risk of identifying personal environment from plan/usage data. Disclosed in Phase 2.

## Three-Layer Separation

| Metric | Value | Notes |
|--------|-------|-------|
| Supervisor layer | First CC | Judgment, review, pain transmission |
| Relay layer | Assistant AI (Ollama, etc.) | Routine monitoring. Zero judgment |
| Worker layer | Current CC | Implementation, modification, task execution |
| Local consensus model count | 5 machines [observed: single environment] | For structural verification |
| Assistant follow-up items | 117 follow-up directives [observed: single environment] | These 117 directives triggered auto-accumulation of 98 [observed: single environment] L1 patterns + 206 [observed: single environment] knowledge entries (304 total [observed: single environment] derived items) |

---

## Public / Non-public Boundary Design

| Published | Reason |
|-----------|--------|
| FM count and classification system | Structure visible but not a reproduction key |
| CC generation count and operational time | Same |
| Detection pattern names and rates | Approach effectiveness visible but not implementation |
| reason_code list | Quality design thinking is visible |
| Design values (65% [design target] reduction, 20x [design target], etc.) | Theoretical expectations, not actual measurements |

| Not published | Reason |
|--------------|--------|
| PostgreSQL table schema details | Reproduction key |
| external monitoring hook detection logic | Reproduction key |
| Detection rate N-counts | Operational frequency reveals internal structure |
| Token measured values | Personal environment identification risk |
| external monitoring hook actual content | Reproduction key |
| cc_heritage documents full text | Non-public content |


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
