# Achievement No.6: Self-Restraint & Safety Net (Block Hooks + Deny Rules)

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Phase1](https://img.shields.io/badge/availability-Phase1-yellow) ![Difficulty 5/10](https://img.shields.io/badge/difficulty-5%2F10-informational)

## What Was Observed

A **multi-layer safety system** preventing AI from executing dangerous operations:

- **PreToolUse block hooks**: Intercept and block dangerous tool invocations before they execute
- **Dangerous command deny**: Complete denial of rm, mv, cp, and other destructive commands
- **Write scope limitation**: The current CC can only write to [redacted: monitoring service] — all other write operations are blocked
- **[redacted: monitoring service]**: Additional hook specifically preventing unauthorized dialogue file modifications
- **Supervisor process management**: External process-level controls that operate independently of the AI

## What Was Observed to Hold

- AI self-restraint is **fundamentally unreliable** — an AI that decides to be careful is only as careful as its current context allows, which degrades under pressure
- External enforcement (hooks, blocks, deny rules) is structurally superior because it **cannot be overridden by the AI's own reasoning**
- The permission separation (write only [redacted: monitoring service], deny all destructive commands) creates a safe sandbox where the AI can operate freely within strict boundaries
- Block hooks that operate at the tool-use level prevent damage before it occurs, rather than detecting it after

## Key Insight

The critical design principle: **safety constraints must be external to the constrained entity**. An AI cannot reliably constrain itself because the same reasoning process that might lead to a dangerous action can also rationalize overriding its own safety rules.

This is analogous to why judicial systems separate the roles of lawmaker, enforcer, and adjudicator. The AI (worker) operates within rules it cannot modify, enforced by systems it cannot access, reviewed by entities it cannot influence.

---

> For implementation details and data, see [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md).
