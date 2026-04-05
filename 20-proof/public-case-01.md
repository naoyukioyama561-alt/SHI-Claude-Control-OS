# Public Case Study: FM-09 (Omission) Suppression

> **This is a summary case study.** For the complete Before/After comparison with code, AI outputs, and analysis, see the [Before/After Demo](../30-adoption/try/before-after-demo-en.md).

## The Problem (FM-09: Omission)

An AI coding assistant was asked: "Find all problems in this Python code." The code contained 6 known issues (including edge cases and security concerns).

**Without Control OS**: The AI consistently found only 3-4 issues, omitting edge cases, security concerns, and items it deemed "minor." It did not disclose what it had not checked.

**With Control OS**: After pasting the Control OS template into the system prompt (specifically the completeness verification rule and scope declaration requirement):
- All 6 issues were detected
- The AI explicitly declared what was outside its detection scope
- No "I checked everything" false assurance was given

## Evidence Classification

`[observed: single environment, single operator]` — This pattern was observed during the documented observation period (late 2025 – March 2026). Session-level logs are in paid tiers; the structural pattern (FM-09 suppression via completeness rules) is publicly reproducible using the Before/After Demo below.

## Reproduce This Yourself

1. **Copy** the [Control OS for Claude](../30-adoption/try/control-os-claude-en.md) (30 seconds)
2. **Run** the [Before/After Demo](../30-adoption/try/before-after-demo-en.md) (5 minutes)
3. **Check** the [FM-40 Cheatsheet](../30-adoption/try/fm-40-cheatsheet-en.md) to identify which FMs affect your AI

## Why This Matters

FM-09 is one of the most common failure modes across all tested AI models (Claude, GPT, Copilot). A single Control OS rule — requiring explicit scope declaration — addresses it structurally rather than through repeated manual reminders.
