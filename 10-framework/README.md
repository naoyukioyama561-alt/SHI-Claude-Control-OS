# 10-framework/ — Structural Conditions for AI Governance

## Before you read

Have you tried [30-adoption/try/](../30-adoption/try/) yet?
If not, try it first. Reading without experience stops at "read."

> "Reading" ≠ "understanding" ≠ "internalized."
> — Achievement No.12, Mentor-Apprentice Review

## Reading order with verification gates

Each step has a **verification gate**.
If you can't answer the gate questions in your own words, you haven't understood. Re-read.

---

### Step 1: Failure Modes taxonomy

[EN](en/01-failure-modes.md) | [JA](ja/01-failure-modes.md)

40 observable patterns of "how AI fails." With impact ratings for Claude, GPT, and Copilot.

**Verification gate**:
- [ ] Name the 3 FMs that fire most often on YOUR AI (by number)
- [ ] Explain the conditions that trigger those 3, applied to YOUR workflow
- [ ] After pasting the Control OS in try/, did those 3 get suppressed?

---

### Step 2: Control OS

[EN](en/02-control-os.md) | [JA](ja/02-control-os.md)

Operational controls to prevent failure modes. Core: the control loop (Contract → Execute → Verify → Log → Update).

**Verification gate**:
- [ ] Explain the 5-step control loop applied to YOUR work
- [ ] Which "hard prohibition" does YOUR AI violate most often?
- [ ] What one line will you add to your system prompt today?

---

### Step 3: Incident ledger format

[EN](en/03-incident-ledger.md) | [JA](ja/03-incident-ledger.md)

How to accumulate failures as "shareable learning units." One incident = one file.

**Verification gate**:
- [ ] Write up a recent failure from YOUR AI in this format
- [ ] Identify its FM number and which Control OS rule would have prevented it

---

### Step 4: Three-layer separation

[EN](en/04-three-layer.md) | [JA](ja/04-three-layer.md)

Supervisor / Relay / Worker — separating load by TYPE, not volume.

**Verification gate**:
- [ ] Explain the difference between "splitting by type" and "reducing volume"
- [ ] Which of the 3 layers is MISSING in your current setup?
- [ ] Explain WHY the monitoring AI must be a separate AI

---

### Step 5: Quality system

[EN](en/05-quality-system.md) | [JA](ja/05-quality-system.md)

4+1 layer architecture, reason_code taxonomy, mandatory 5-set inspection.

**Verification gate**:
- [ ] Apply the 5-set to your most recent task
- [ ] Which reason_code fires most often on your AI?
- [ ] Which of the 4+1 layers does NOT exist in your environment?

---

### Step 6: Research comparison

[EN](en/06-research-comparison.md) | [JA](ja/06-research-comparison.md)

How this approach compares to the 2026 research and commercial landscape.

**Verification gate**:
- [ ] Which unsolved problem in the research community does YOUR setup address?
- [ ] Which area is YOUR setup still weakest in?

---

### Step 7: SHI theory citations

[EN](en/07-shi-citations.md) | [JA](ja/07-shi-citations.md)

Key citations from the SHI theory papers underlying this framework.

**Verification gate**:
- [ ] Explain the relationship between SHI propositions P1-P3 and the repository structure

---

## After all steps

→ **Next**: [20-proof/](../20-proof/) — verify the evidence

→ See also: [40-heritage/](../40-heritage/) — understand the inheritance structure | [30-adoption/try/](../30-adoption/try/) — run the control loop on your own AI
