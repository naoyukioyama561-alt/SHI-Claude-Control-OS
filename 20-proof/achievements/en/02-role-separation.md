# Achievement No.2: Three-Layer Role Separation (Supervisor / Relay / Worker)

![★★★★★](https://img.shields.io/badge/evidence-★★★★★-brightgreen) ![Free](https://img.shields.io/badge/availability-Free-blue) ![Difficulty 4/10](https://img.shields.io/badge/difficulty-4%2F10-informational)

## What Was Observed

A **three-layer role separation architecture** that divides work not by volume, but by **load type**:

| Layer | Role | Load Type | Key Benefit |
|-------|------|-----------|-------------|
| **Supervisor** | Senior CC (1st gen) | Judgment, review, meaning-making | Freed from context pressure; focuses purely on pain-aware review |
| **Relay** | Assistant AI (Ollama, etc.) | Routine monitoring, notification forwarding | Zero judgment = zero context bloat; mechanically reliable |
| **Worker** | Current CC | Implementation, modification, task execution | Freed from rule memorization and monitoring; pure task focus |

## What Was Observed to Hold

- The root cause of AI quality degradation is **not** insufficient capability — it is **mixed load types** forcing one AI to handle judgment + monitoring + execution simultaneously
- Separating by load type (not volume) eliminates the vicious cycle where context pressure degrades both monitoring and execution at the same time
- The Relay layer is critical: by handling routine monitoring with zero judgment, it prevents context bloat from propagating to either the Supervisor or Worker

## Key Insight (考え方のポイント)

The key structural shift: **separate load by type, not by amount**. Everyone tries to handle overload by splitting work volume. But the real problem is that judgment, monitoring, and execution are fundamentally different cognitive loads — mixing them degrades all three.

When you separate them, each role becomes excellent at its specific function. The Supervisor judges without distraction. The Relay monitors without judgment drift. The Worker executes without rule anxiety.

This principle applies to any multi-AI system or human-AI collaboration.

→ Full documentation: [`10-framework/04-three-layer.md`](../../../10-framework/en/04-three-layer.md)

---

> For implementation details and data, see [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md).
