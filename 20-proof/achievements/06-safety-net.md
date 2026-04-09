# Achievement No.6: Self-Restraint & Safety Net (Block Hooks + Deny Rules)
Language: [日本語版はこちら / Japanese version](../../ja/20-proof/achievements/06-safety-net-ja.md)

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Free (summary)](https://img.shields.io/badge/availability-Free%20%28summary%29-blue) ![Difficulty 5/10](https://img.shields.io/badge/difficulty-5%2F10-informational)

> *Note: `[designated write target]` and `[external monitoring hook]` are redacted internal names for safe public release. See [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md) for scope details.*

## What Was Observed

A **multi-layer safety system** designed to block dangerous operations before execution:

- **PreToolUse block hooks**: Intercept and block dangerous tool invocations before they execute
- **Dangerous command deny**: Complete denial of rm, mv, cp, and other destructive commands
- **Write scope limitation**: The current CC can only write to [designated write target] — all other write operations are blocked
- **[external monitoring hook]**: Additional hook specifically preventing unauthorized dialogue file modifications
- **Supervisor process management**: External process-level controls that operate independently of the AI

## What Was Observed to Hold

- In the author's observed environment, AI self-restraint **was not reliable enough** for safety-critical operation — an AI that decides to be careful is only as careful as its current context allows, which was observed to degrade under pressure
- External enforcement (hooks, blocks, deny rules) is structurally superior because it **cannot be overridden by the AI's own reasoning**
- The permission separation (write only [designated write target], deny all destructive commands) creates a safe sandbox where the AI can operate freely within strict boundaries
- Block hooks that operate at the tool-use level prevent damage before it occurs, rather than detecting it after

## Key Insight

> The design principle applied here was:

The critical design principle: **safety constraints must be external to the constrained entity**. An AI cannot reliably constrain itself because the same reasoning process that might lead to a dangerous action can also rationalize overriding its own safety rules.

This is analogous to why judicial systems separate the roles of lawmaker, enforcer, and adjudicator. The AI (worker) operates within rules it cannot modify, enforced by systems it cannot access, reviewed by entities it cannot influence.

---

> For implementation details and data, see [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md).

> **Note**: Phase 1 / Phase 2 = future open release phases, not paid tiers. See [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md).


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
