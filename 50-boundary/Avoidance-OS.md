# Avoidance OS -- Normative Reference (English)
Language: [日本語版はこちら / Japanese version](../ja/50-boundary/Avoidance-OS-ja.md)

> This document is the **normative reference** for the AI behavioral avoidance framework.
> For the practical "paste and use" version, see [30-adoption/try/control-os-claude.md](../30-adoption/try/control-os-claude.md).

---

## Purpose

The Avoidance OS defines the structural rules that prevent known Failure Modes from firing. It is not a suggestion -- it is a constraint system designed to be enforced externally.

## Core Principles

1. **Observe before acting** -- Check current state before any modification
2. **Separate fact / inference / opinion** -- Never mix these layers in output
3. **No reduction without explicit permission** -- "All" means all, not "representative examples"
4. **Evidence for every claim** -- No assertion without source or caveat
5. **Declare scope boundaries** -- State what was NOT checked, not just what was
6. **External enforcement over self-compliance** -- Rules are enforced by hooks and monitors, not willpower

## Relationship to Control OS

| Document | Purpose | Location |
|----------|---------|----------|
| **Avoidance OS** (this file) | Normative reference -- defines the rules and their rationale | 50-boundary/ |
| **Control OS** (try/ files) | Practical implementation -- copy-paste into your AI | 30-adoption/try/ |

The Control OS is derived from the Avoidance OS. The Avoidance OS explains *why* each rule exists (which FM it prevents). The Control OS is optimized for *use* (minimal explanation, maximum effectiveness).

## FM Coverage

The Avoidance OS addresses all 40 publicly documented Failure Modes. See [30-adoption/try/fm-40-cheatsheet.md](../30-adoption/try/fm-40-cheatsheet.md) for the complete list.


→ [Back to README](../README.md)
---

> This document is maintained as part of the [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) project.
