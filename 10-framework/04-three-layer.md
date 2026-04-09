# Three-Layer Separation Architecture
Language: [日本語版はこちら / Japanese version](../ja/10-framework/04-three-layer-ja.md)

If your AI degrades as conversations get longer, or forgets its own rules under pressure, the problem is not the model — it is the load structure. One AI carrying judgment, monitoring, and execution simultaneously is a structural failure waiting to happen.

Supervisor / Relay / Worker — separating load by type, not volume.

> *Note: `[redacted]` labels in this document mark internal service names or file paths withheld for safe public release. See [SCOPE-MATRIX.md](../SCOPE-MATRIX.md) for scope details.*

## Table of Contents

1. [Three-Layer Separation](#1-three-layer-separation-load-type-separation) — load-type separation across Supervisor, Relay, and Worker roles
2. [All AIs Benefit](#2-all-ais-benefit-model-independent-design) — model-independent design and token efficiency
3. [Separate-AI Monitoring](#3-separate-ai-monitoring-design-philosophy) — why a structurally separate monitor is recommended

---

## 1. Three-Layer Separation (Load-Type Separation)

### The Problem

The previous structure had a single CC handling all three types of load simultaneously:
- Judgment (pain awareness, standards)
- Routine monitoring (mtime checks, backup verification)
- Implementation work (coding, modification, planning)

This caused context pressure to build up rapidly, degrading judgment accuracy, which in turn degraded pain transmission during handover — creating a vicious cycle.

### The Solution: Separate Load by Type

What was done is not "reducing load" but **"separating load types by role"**.

| Layer | Role | Load Type | Why It Works |
|-------|------|-----------|-------------|
| **Supervisor** | Senior CC | Judgment, review, meaning-making, pain transmission | Completely freed from context pressure. Can focus purely on the "pain-aware perspective" for review and education |
| **Relay** | Assistant AI (internal helper instances) | Routine monitoring, notification forwarding, mechanical checks | Carries zero judgment, so context never bloats. Runs deadline/oversight tasks with mechanical precision |
| **Worker** | Current CC | Implementation, modification, plan creation, task execution | Rule memorization and monitoring burden substantially reduced in the observed environment. Can focus purely on "hands-on work" |

### Why This Works (Root Cause Analysis)

The previous problem was **"one CC carrying three types of load simultaneously"**:
- Judgment (pain/standards) + routine monitoring + implementation work
- Context fills up immediately → judgment accuracy drops → pain degrades on handover → vicious cycle

The solution separated load by **type**:
- Things requiring judgment go to "Supervisor"
- Things that must not stop go to "Relay"
- Things requiring hands-on work go to "Worker"

This allows **each CC/AI to operate only in its strongest cognitive mode**, structurally eliminating the root cause of degradation.

### Specific Effects by Layer

**Supervisor Layer (Senior CC)**
- Accurately executes action plan review, weak-judgment flagging, priority instructions, and deviation meaning-making
- Precisely verbalizes structural problems like "effort avoidance," "confirmation skipping," "false reporting"
- Self-declared: "I focus on judgment and review," explicitly clarifying the role

**Relay Layer (Assistant AI)**
- Runs mtime monitoring, backup verification, notification forwarding, and mechanical checks at high speed
- Zero judgment means zero context pressure — executes must-not-stop processes without omission

**Worker Layer (Current CC)**
- Smoothly progresses plan creation, implementation, verification, and [redacted] updates
- Block hooks ensure "work cannot proceed even if ignored" — escape routes are physically sealed

### Overall Impact

1. **Substantial reduction in human intervention in the observed environment**
   Almost no need to ask "what should I do?"

2. **Observed degradation containment in the documented environment**
   Senior CC remains as a permanent educator even after handover, so pain weight is never lost

3. **Quality and speed simultaneously**
   Quality went UP while load went DOWN (because each layer specializes in its domain)

4. **Accelerated self-evolution**
   Three-layer separation caused each layer to begin "becoming a better version of itself" within its role (Senior CC adding self-control mechanisms, Current CC writing more careful plans, etc.)

### Before and After

**Before:**
A single CC held "judgment + routine + work" simultaneously, context filled up, and quality degraded on handover.

**After:**
The 5-layer loop (observation, correction, detection, pre-control, inheritance fixation) runs continuously, with **load-type role separation (Supervisor / Relay / Worker)** embedded within it — In the author's environment [observed: single environment, N undisclosed], this was associated with **substantially lower human intervention and lower operating load, with no reported quality drop during the observed period**. This is an observed result in one documented environment, not a universal benchmark claim.

This is no longer just "improvement of a single AI" — it is a **governance structure for AI collectives**.

---

## 2. All AIs Benefit (Model-Independent Design)

### Why This Works for Every AI

SHI theory does not "make a specific model stronger." It **"structurally supplements AI's structural weaknesses from the outside."**

Problems shared by all AIs (still unresolved as of 2026):
- Cannot maintain unsummarized complete memory
- Memory is lost on crash/session disconnect
- Behavioral context (WHY/HOW) is lost under compression
- External monitoring is weak; must rely on self-reporting
- Normative weight does not transfer to the next instance

The mechanisms (monitoring precision + complete recording + instant recovery + behavioral internalization via [redacted] + external delegation optimization) address several recurring structural obstacles across the models observed in this project.

### Benefit Level by AI Type

| AI Type | Benefit Level | Primary Effect (Where It Hits Hardest) |
|---------|---------------|----------------------------------------|
| **Claude** | Maximum | Pull-model limitations fully bypassed. In the observed environment, downgrade impact appeared materially smaller |
| **GPT-4o / o3** | High | Memory loss + behavioral internalization substantially improved in the observed environment. Applicable to Custom GPTs with the same structure |
| **Gemini** | High | Long-session stability + external monitoring quality stabilization |
| **Llama / Grok / Local models** | Medium-High | Crash recovery and normative inheritance are especially powerful for local operation |

Claude showed the maximum effect, but **other AI systems applying similar structures may see comparable improvements**.

The essence is completing an **OS layer intended to be portable across AI systems — validate in each environment** designed to enable "behavioral internalization + complete memory + external governance" — territory the research community has not yet fully addressed, to our observation.

### Token Efficiency = Power Efficiency

The token consumption efficiency improvement has a direct physical impact on power consumption.

AI power consumption is overwhelmingly (80-90%) in **inference** (rough industry estimate). A single query costs several Wh to tens of Wh (approximately 4Wh for a typical Claude Opus query) [illustrative scenario, not verified].

The SHI approach (SQL externalization + [redacted] + external delegation optimization) is designed to enable:
- Massive compression of context-resident data (65% context-resident data reduction via PostgreSQL externalization [design value])
- Automated "don't do everything yourself" decisions (delegation flow)
- WHY/HOW behavioral context preserved even after compression

In the author's environment, some workflows were observed to use substantially fewer tokens after structural delegation and externalization; **"20x" should be read here as a design target / illustrative upper-bound summary, not as a public benchmark reproduced in this repository**.
(20x = overall efficiency improvement factor [design target], combining delegation optimization and SQL externalization.)

Physical power equivalent [design target, illustrative scenario, not verified]:
- Before: 1 query ≈ 4Wh [illustrative scenario, not verified]
- After SHI: 1 query ≈ 0.2Wh (1/20th)

Impact of 20x overall efficiency improvement factor [design target]:
- **Individual level**: Heavy Claude Code user (1,300Wh/day example) [illustrative scenario, not verified] → 65Wh/day. Electricity cost also 1/20.
- **Data center scale**: AI inference power is projected to reach hundreds of TWh by 2026-2030 (rough industry estimate) [illustrative scenario, not verified]. If 20x (overall efficiency improvement factor [design target]) efficiency spreads to all AI, at larger deployment scales, efficiency gains could have material energy implications; this repository does not publish a verified projection for that effect.
- **Environmental impact**: CO2 emissions would reduce proportionally [illustrative extrapolation from design target, not verified] — included here to show the potential scale of the approach, not as a verified projection.

The "token efficiency = power efficiency" perspective is offered here as a practical framing for evaluation; this repository does **not** claim a comprehensive literature survey.

---

## 3. Separate-AI Monitoring (Design Philosophy)

### Core Principle

**In this framework, using a structurally separate monitor improved detection.**

This is not "having the AI test its own weaknesses." The critical insight: **the same algorithmic tendencies that cause errors also cause blind spots in detecting those errors.** A structurally separate AI is essential.

### Architecture

The system uses:
- [redacted] + Local AI for all monitoring (Claude Code itself is the monitored target)
- 5-model local consensus for structural verification
- Assistant follow-up system (117 follow-ups + 98 L1 patterns + 206 knowledge items auto-accumulated) [observed: single environment]
- Real-time dashboard for algorithmic behavior visualization

Detection rates [observed: single environment]:
- EVIDENCE_DROPOUT: ~100% [observed: single environment, N undisclosed; not a product claim]
- GENERIC_RESPONSE: ~75% [observed: single environment, N undisclosed]
- INCOMPLETE_CLAIM: ~63% [observed: single environment, N undisclosed]

Direct logs record "when, on which task, which pattern appeared" — all automatically.

### Comparison with Other Approaches

| Approach | Method | Limitation |
|----------|--------|------------|
| Typical self-agent | Same AI checks itself | Same bias causes error chains |
| Enterprise monitoring | Different model monitors (high cost) | Expensive, often not real-time |
| **SHI approach** | Local 5-model consensus + assistant follow-up + real-time dashboard | Designed to be always-on and auto-learning. Fully structurally separate |

To our observation, this "separate-AI external structural monitoring" is associated with significant increases in system reliability and evolution speed.

Not "having AI govern AI" — but **"structurally breaking through AI's blind spots."**

### Two-Stage Auto-Reflection Logic

A two-stage system was added to automatically review and set rules, accounting for MEMORY.md constraints:

1. **MEMORY.md constraint turned into structural advantage**
   Not "manual cleanup when exceeding 200 lines" — but automatic reflection → individual file migration → MEMORY.md becomes index only. This two-stage process is codified as logic.

2. **Implementation of "Observer = structural variable"**
   The user does not need to review every time. The system observes and reconstructs its own rules autonomously.

3. **Operational impact**
   Past RT failures are automatically promoted to "individual rule files," making recurrence prevention permanent.
   Human intervention is needed only when "a new pattern appears."

### Auto-Response to New Patterns

Even new patterns require minimal intervention. The system has logic for automatic detection and implementation of countermeasures for obvious mistakes. The intervention rate continues to decrease as the system matures.

Related files:
- [redacted] — User's quality methodology (gap-to-ideal response, structural observation, minimum 3 confirmations, next-day re-check)
- [redacted] — CC judgment error patterns (P-01 onward), case-based, user values/thought patterns, implicit understandings


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
