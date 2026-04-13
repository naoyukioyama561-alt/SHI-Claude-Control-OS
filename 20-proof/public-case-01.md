# Public Case Study: FM-09 (Omission) Suppression
Language: [日本語版はこちら / Japanese version](../ja/20-proof/public-case-01-ja.md)

> **This is a summary case study.** For the complete Before/After comparison with code, AI outputs, and analysis, see the [Before/After Demo](../30-adoption/try/before-after-demo.md).

## The Problem (FM-09: Omission)

An AI coding assistant was asked: "Find all problems in this Python code." The code contained multiple known issues [illustrative] (including edge cases and security concerns).

**Without Control OS**: The AI found only a subset of the issues [illustrative], omitting edge cases, security concerns, and items it deemed "minor." It did not disclose what it had not checked.

**With Control OS**: After pasting the Control OS template into the system prompt (specifically the completeness verification rule and scope declaration requirement):
- In this documented example [observed: single environment, single operator], all 6 known issues in the sample were detected
- In this documented example, the AI explicitly declared what was outside its detection scope
- No "I checked everything" false assurance was given

## Evidence Classification

`[observed: single environment, single operator]` — This pattern was observed during the documented observation period (late 2025 – March 2026). Session-level logs are in non-public material; the structural pattern (FM-09 suppression via completeness rules) is publicly reproducible using the Before/After Demo below.

## Reproduce This Yourself

1. **Copy** the [Control OS for Claude](../30-adoption/try/control-os-claude.md) (30 seconds)
2. **Run** the [Before/After Demo](../30-adoption/try/before-after-demo.md) (5 minutes)
3. **Check** the [FM-40 Cheatsheet](../30-adoption/try/fm-40-cheatsheet.md) to identify which FMs affect your AI

## Why This Matters

In the author's observed environment, FM-09 recurred across Claude, GPT, and Copilot workflows [observed: single environment, single operator]. The reproducible claim in this public repository is that explicit scope declaration can materially reduce omission behavior, as demonstrated in the [Before/After Demo](../30-adoption/try/before-after-demo.md). Readers should verify this effect in their own environment.

[日本語版](../ja/20-proof/public-case-01-ja.md)


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
