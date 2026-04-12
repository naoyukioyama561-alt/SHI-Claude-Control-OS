# Achievement No.10: Compound Factor Auto-Analysis (5-Why + private incident store)
Language: [日本語版はこちら / Japanese version](../../ja/20-proof/achievements/10-multi-cause-analysis-ja.md)

![★★★](https://img.shields.io/badge/evidence-★★★-yellow) ![Public (summary)](https://img.shields.io/badge/availability-Public%20%28summary%29-blue)

Single-event debugging often misses structural causes. In the author's environment, multi-cause analysis surfaced patterns that were not visible in one-off incident review.

> *Note: `[internal database table]` is a redacted internal name for safe public release. See [SCOPE-MATRIX.md](../../SCOPE-MATRIX.md) for scope details.*

## What Was Observed

A **structured root cause analysis system** combining multiple methodologies:

- **5-Why analysis**: Systematic drilling into root causes, going beyond surface symptoms to structural origins
- **Predecessor CC reference**: Automatically consulting the Senior CC's accumulated experience when analyzing incidents
- **internal database table auto-accumulation**: Every analyzed incident is stored structurally for future reference
- **Self-reflection automation**: The gap between "knowing" and "doing" is systematically identified and addressed

## What Was Observed to Hold

- AI failure analysis typically stops at surface symptoms — "I made an error" instead of "the structural condition that caused this error is X, and it will recur under conditions Y and Z"
- The 5-Why method, combined with predecessor CC knowledge, reveals **compound causes** that single-session analysis cannot detect
- Self-evaluation exposed critical gaps: the difference between "I know the rule" and "I consistently follow the rule" (verified across 5 evaluation dimensions)
- Automated incident knowledge accumulation creates an **institutional memory** that improves analysis quality over time

## Key Insight

> The following reflects what was observed in the author's environment:

The most important discovery: **AI can identify its own behavioral patterns, but cannot fix them through awareness alone**. Knowing about a failure pattern does not prevent it from recurring — structural intervention (hooks, blocks, external monitoring) is required.

This is directly analogous to human behavior change: understanding a bad habit is necessary but insufficient. The compound analysis system identifies not just what failed, but what structural change will prevent recurrence.

---

> For implementation details and data, see [SCOPE-MATRIX.md](../../SCOPE-MATRIX.md).

> **Note**: Phase 1 / Phase 2 = future open release phases, not pricing structures. See [SCOPE-MATRIX.md](../../SCOPE-MATRIX.md).


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
