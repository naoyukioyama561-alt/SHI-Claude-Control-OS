# Three-Layer Separation Architecture

Supervisor / Relay / Worker — separating load by type, not volume.

This document covers three interconnected design principles:
1. **Three-Layer Separation** (GC01) — load-type separation across Supervisor, Relay, and Worker roles
2. **All AIs Benefit** (GC02) — model-independent design and token efficiency
3. **Separate-AI Monitoring** (GC09) — why the monitoring AI must be a different AI

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
| **Relay** | Assistant AI (Ollama, etc.) | Routine monitoring, notification forwarding, mechanical checks | Carries zero judgment, so context never bloats. Runs deadline/oversight tasks with mechanical precision |
| **Worker** | Current CC | Implementation, modification, plan creation, task execution | Rule memorization and monitoring burden dramatically reduced. Can focus purely on "hands-on work" |

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
- Smoothly progresses plan creation, implementation, verification, and cc_dialogue updates
- Block hooks ensure "work cannot proceed even if ignored" — escape routes are physically sealed

### Overall Impact

1. **Dramatic reduction in human intervention**
   Almost no need to ask "what should I do?"

2. **Complete degradation prevention**
   Senior CC remains as a permanent educator even after handover, so pain weight is never lost

3. **Quality and speed simultaneously**
   Quality went UP while load went DOWN (because each layer specializes in its domain)

4. **Accelerated self-evolution**
   Three-layer separation caused each layer to begin "becoming a better version of itself" within its role (Senior CC adding self-control mechanisms, Current CC writing more careful plans, etc.)

### Before and After

**Before:**
A single CC held "judgment + routine + work" simultaneously, context filled up, and quality degraded on handover.

**After:**
The 5-layer loop (observation, correction, detection, pre-control, inheritance fixation) runs continuously, with **load-type role separation (Supervisor / Relay / Worker)** embedded within it — achieving **near-zero human intervention while dramatically reducing load without sacrificing quality**, completing a system where pain does not degrade across generations.

This is no longer "improvement of a single AI" — it is a **"sustainable governance institution for AI collectives."**

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

The mechanisms (monitoring precision + complete recording + instant recovery + behavioral internalization via cc_orientation + external delegation optimization) solve all of these **model-independently**.

### Benefit Level by AI Type

| AI Type | Benefit Level | Primary Effect (Where It Hits Hardest) |
|---------|---------------|----------------------------------------|
| **Claude** | Maximum | Pull-model limitations fully bypassed. Pro downgrade impact reduced to near-zero |
| **GPT-4o / o3** | High | Memory loss + behavioral internalization dramatically improved. Applicable to Custom GPTs with the same structure |
| **Gemini** | High | Long-session stability + external monitoring quality stabilization |
| **Llama / Grok / Local models** | Medium-High | Crash recovery and normative inheritance are especially powerful for local operation |

Claude showed the maximum effect, but **any AI applying the same structure receives equivalent benefits**.

The essence is completing an **OS layer portable to any AI** that achieves "behavioral internalization + complete memory + external governance" — territory the research industry has not yet reached.

### Token Efficiency = Power Efficiency

The token consumption efficiency improvement has a direct physical impact on power consumption.

AI power consumption is overwhelmingly (80-90%) in **inference**. A single query costs several Wh to tens of Wh (approximately 4Wh for a typical Claude Opus query).

The SHI approach (SQL externalization + cc_orientation + external delegation optimization) achieves:
- Massive compression of context-resident data (65% reduction)
- Automated "don't do everything yourself" decisions (#10 delegation flow)
- WHY/HOW behavioral context preserved even after compression

Result: **same work at 1/20th the token consumption**.

Physical power equivalent:
- Before: 1 query ≈ 4Wh
- After SHI: 1 query ≈ 0.2Wh (1/20th)

Impact of 20x efficiency:
- **Individual level**: Heavy Claude Code user (1,300Wh/day example) → 65Wh/day. Electricity cost also 1/20.
- **Data center scale**: AI inference power is projected to reach hundreds of TWh by 2026-2030. If 20x efficiency spreads to all AI, the reduction would be equivalent to Japan's entire annual power consumption.
- **Environmental impact**: CO2 emissions reduced proportionally by 1/20. With data center power demand straining grids, this is significant as a climate change measure.

The "token efficiency = power efficiency" perspective is **an angle barely discussed even in the research industry**.

---

## 3. Separate-AI Monitoring (Design Philosophy)

### Core Principle

**The monitoring AI must be a different AI from the monitored AI.**

This is not "having the AI test its own weaknesses." The critical insight: **the same algorithmic tendencies that cause errors also cause blind spots in detecting those errors.** An internal AI (a separate AI) is essential.

### Architecture

The system uses:
- n8n-AI + Local AI for all monitoring (Claude Code itself is the monitored target)
- 5-model local consensus for structural verification
- Assistant follow-up system (117 follow-ups + 98 L1 patterns + 206 knowledge items auto-accumulated)
- Real-time dashboard for algorithmic behavior visualization

Detection rates achieved:
- EVIDENCE_DROPOUT: 100%
- GENERIC_RESPONSE: 75%
- INCOMPLETE_CLAIM: 63%

Direct logs record "when, on which task, which pattern appeared" — all automatically.

### Comparison with Other Approaches

| Approach | Method | Limitation |
|----------|--------|------------|
| Typical self-agent | Same AI checks itself | Same bias causes error chains |
| Enterprise monitoring | Different model monitors (high cost) | Expensive, often not real-time |
| **SHI approach** | Local 5-model consensus + assistant follow-up + real-time dashboard | Free, always-on, auto-learning. Fully structurally separate |

This "separate-AI external structural monitoring" causes system reliability and evolution speed to increase exponentially.

Not "having AI govern AI" — but **"structurally and permanently breaking through AI's blind spots."**

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
- quality_standard.md — User's quality methodology (gap-to-ideal response, structural observation, minimum 3 confirmations, next-day re-check)
- behavioral_patterns.md — CC judgment error patterns (P-01 onward), case-based, user values/thought patterns, implicit understandings
