# Achievement No.9: Post-Compression Behavior Persistence (Orientation File + SQL)

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Free (summary)](https://img.shields.io/badge/availability-Free%20%28summary%29-blue) ![Difficulty 6/10](https://img.shields.io/badge/difficulty-6%2F10-informational)

> *Note: `[behavior orientation file]` is a redacted internal name for safe public release. See [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md) for scope details.*

## What Was Observed

A system designed to preserve **behavioral patterns after context compression**, addressing the problem of AI "forgetting how to act" after summarization:

- **[behavior orientation file].json**: Encodes WHY (purpose), HOW (methods), and STANCE (behavioral posture) — the three layers of behavioral internalization
- **SQL externalization**: Critical behavioral data stored in PostgreSQL, immune to context compression
- **WHAT/WHY/HOW 3-layer model**: Distinguishes between knowing what to do, understanding why, and having it internalized as automatic behavior
- **Compression-resistant design**: Post-compression sessions automatically reload behavioral foundations

## What Was Observed to Hold

- Context compression causes **behavioral regression** — the AI loses not just facts but behavioral patterns (in the author's environment, 4 instances [observed: single environment] of 2-hour review forgetting were recorded within a single session)
- The 3-layer internalization model (WHAT/WHY/HOW) correctly predicts which behaviors survive compression and which don't
- In the author's observed environment, SQL externalization + [behavior orientation file].json together were associated with **near-complete behavioral restoration** after compression events

## Key Insight

> The following reflects what was observed in the author's environment:

The fundamental insight: **AI behavior is more fragile than AI knowledge**. Facts can be re-learned from external sources, but behavioral patterns — the "how to act" knowledge — are destroyed by compression because they exist as implicit context, not explicit data.

The solution: make implicit behavioral patterns explicit by encoding them in a structured format ([behavior orientation file].json) that can be reloaded mechanically, bypassing the need for the AI to "re-learn" its behavioral stance.

---

> For implementation details and data, see [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md).

> **Note**: Phase 1 / Phase 2 = future open release phases, not paid tiers. See [SCOPE-MATRIX.md](../../../SCOPE-MATRIX.md).
