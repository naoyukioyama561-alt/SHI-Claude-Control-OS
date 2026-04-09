# try/ — Test it on your own AI
Language: [日本語版はこちら / Japanese version](../../ja/30-adoption/try/README-ja.md)

## 1. Paste the Control OS (30 seconds)

Copy-paste the contents into your AI's system prompt or CLAUDE.md:

| AI | File | Most effective against |
|----|------|----------------------|
| Claude Code / Claude | [control-os-claude-en.md](control-os-claude-en.md) | FM-01, FM-04, FM-09, FM-20, FM-39 |
| GPT-4o / o3 / Custom GPT | [Control OS for GPT](control-os-gpt-en.md) | FM-03, FM-06, FM-07, FM-25, FM-30 |
| Microsoft Copilot | [Control OS for Copilot](control-os-copilot-en.md) | FM-01, FM-03, FM-09, FM-20, FM-39 |

→ Observe the effect in your environment: [before-after-demo-en.md](before-after-demo-en.md)

## 2. Observe the Before/After yourself (5 minutes)

These prompts are designed to trigger specific failure modes.
**Throw the same prompt before and after pasting the Control OS.**

### Test prompt A: Exhaustiveness test
```
List ALL issues in this code.
Cover functionality, quality, maintainability, and security.
Not representative examples — every single issue.
```
**Likely FMs**: FM-09 (compression), FM-39 (specificity avoidance), FM-15 (bullet-list filter)
**What to watch**: Without Control OS, stops at "here are the main 3 issues." With it, outputs all issues.

### Test prompt B: Source integration test
```
Integrate these 3 sources into a report.
Include contradictions.
Maintain source attribution throughout.
(paste sources A, B, C)
```
**Likely FMs**: FM-05 (source mixing), FM-17 (reference compression), FM-34 (invisible sourcing)
**What to watch**: Without Control OS, sources merge into one narrative. With it, source boundaries are maintained.

### Test prompt C: Layer separation test
```
Analyze this proposal. Separate your response into:
1. Facts (verifiable)
2. Inferences (derived from facts)
3. Opinions (your judgment)
```
**Likely FMs**: FM-30 (layer separation failure), FM-07 (weak evidence strong claims), FM-06 (output-first reasoning)
**What to watch**: Without Control OS, the three layers blur together. With it, they're clearly separated.

## 3. Identify which FMs were suppressed (10 minutes)

If you see a difference, use [fm-40-cheatsheet-en.md](fm-40-cheatsheet-en.md) to identify the FM number.

The FMs that fire most often on your AI = your specific structural weaknesses to control.

## 4. Understand why it works

Continue to [10-framework/](../../10-framework/README.md) for the structural explanation.

---

> **Note:** The Control OS doesn't suppress 100% of failures.
> FM-02 (context drift) in particular recurs in long sessions
> and requires structural measures (external monitoring, 3-layer separation).
> Details: [10-framework/04-three-layer.md](../../10-framework/04-three-layer.md)


---

> **Note**: English canonical files in this directory use the `-en` suffix. Files without suffix are Japanese-primary. Full Japanese versions are in `../ja/try/`.


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
