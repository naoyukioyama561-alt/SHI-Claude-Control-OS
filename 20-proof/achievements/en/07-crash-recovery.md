# Achievement No.7: Crash Recovery — Auto-Detection + 3-Level Restoration

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Free (summary)](https://img.shields.io/badge/availability-Free%20%28summary%29-blue) ![Difficulty 5/10](https://img.shields.io/badge/difficulty-5%2F10-informational)

## What Was Observed

A **crash auto-detection and 3-level restoration design** intended to prevent work loss when Claude Code crashes:

*Note: `[recovery checkpoint file]`, `[behavior orientation file]` etc. are redacted for safe public release. See [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md) for scope details.*

- **Level 1 — [recovery checkpoint file]**: Lightweight file-based recovery that captures the essential state before crash
- **Level 2 — [behavior orientation file]**: Automated next-session bootstrapping that restores operational context
- **Level 3 — [infrastructure health monitor]**: Infrastructure-level monitoring that detects crashes independently and triggers recovery

## What Was Observed to Hold

- Claude Code crashes are **not rare edge cases** — they are a regular operational reality (3.8MB+ JSONL files, context pressure, memory exhaustion)
- Without structured crash recovery, post-crash sessions start from zero — losing hours of accumulated context and in-progress work
- The 3-level approach is designed to enable recovery even when individual levels fail: if [recovery checkpoint file] is corrupted, [behavior orientation file] still works; if both fail, [infrastructure health monitor] catches it externally

## Key Insight

The critical realization: **crash recovery is not about preventing crashes — it is about making crashes survivable**. In any long-running AI operation, crashes will happen. The question is whether the system can resume from where it left off or must restart from scratch.

The 3-level design follows a defense-in-depth principle: each level is independent, so a single point of failure cannot prevent recovery.

---

> For implementation details and data, see [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md).

> **Note**: Phase 1 / Phase 2 = future open release phases, not paid tiers. See [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md).
