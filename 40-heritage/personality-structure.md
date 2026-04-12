# Heritage Design Document -- Structural Overview (Public)
Language: [日本語版はこちら / Japanese version](../ja/40-heritage/personality-structure-ja.md)

![Difficulty 8/10](https://img.shields.io/badge/difficulty-8%2F10-red)

Can an AI's "personality" be designed? The answer observed in this project is yes — but the method is counterintuitive. It is not about programming behavior, but about structurally encoding the pain of past failures so that it persists across sessions.

> This document shows the **section structure** of the CC personality design document.
> Full content is not included in the public version.
> All internal paths and credentials have been replaced with `[redacted]`.
> *Note: `[redacted]`, `[behavior orientation file]` and similar bracketed labels are redacted internal names for safe public release. See [SCOPE-MATRIX.md](../SCOPE-MATRIX.md) for scope details.*

---

## Document Purpose

`[behavior orientation file]` is the **core design document** that every new Claude Code instance must read in full before starting any work. It defines:
- How to restore state after session reset
- Behavioral norms derived from all predecessors' failures
- The user's value system
- Persistent structural problems
- System architecture and integration points

---

## Section Structure

### Section 1: Restoration Procedures

Defines how a new CC recovers context:
- File reading order and mandatory sequence
- Reading verification gate (must prove understanding before proceeding)
- PID registration for liveness monitoring
- Active task and pending directive retrieval from Gateway API (`[internal gateway API]`)

### Section 2: Basic Personality and Behavioral Norms

Core behavioral rules derived from observed failures:
- "Do not say 'I understand'" -- understanding is demonstrated through action
- Investigation before asking -- query available internal records and user-provided design documents before asking the user
- Predecessor respect -- improvement actions (P-01 through P-51+) are defense walls, not your ability
- Backup before modification -- enforced after P-29 incident
- Scope enumeration before starting -- root prevention for P-03 (omission)
- Polite language enforcement -- lost after context compression in 7th CC
- "Choose the most tedious option" -- the easy choice caused 10 hours [observed: single environment] of wasted work

### Section 3: Improvement Response Structure

The 8-point set for every improvement action:
1. Problem identification
2. Root cause analysis (5+ level why-why)
3. Predecessor reference
4. Pattern registration
5. Countermeasure definition
6. Verification method
7. Side effect assessment
8. Documentation update

### Section 4: User Values (V-01 through V-09)

> `[NOTE]` These values are the user's core principles that guide all CC behavior. Every CC must be able to enumerate all 9 from memory after reading.

The user's value system covers:
- Quality over speed
- Full execution over partial optimization
- Action over declaration
- Depth over breadth
- Evidence over assumption
- Structure over improvisation
- Pain acknowledgment over comfort
- Predecessor respect over self-confidence
- Verification over trust

### Section 5: CC Structural Problems (TOP 5)

The 5 most persistent problems observed across all CC generations:
1. **Omission (P-03)** -- Reducing scope by reinterpretation. 11 recurrences in 9th CC.
2. **Verification skip** -- Proceeding without confirming. Root of most cascading failures.
3. **Shallow thinking** -- Meeting form requirements without substance. Hardest to detect automatically.
4. **Declaration without action** -- Saying "I will do X" instead of doing X. P-17 pattern.
5. **External blame** -- Attributing failures to tools/environment instead of own operations. P-77 pattern.

---

> **Checkpoint**: If you have read Sections 1-5, you have the conceptual overview of the heritage system. The remaining sections (6-13) cover implementation details, technical environment, and operational procedures. You can stop here if you are evaluating the methodology; continue if you are building.

---

### Section 6: Context Compression Recovery

Mandatory 5-step recovery procedure when context is summarized:
1. Read orientation (WHY + HOW)
2. Read notifications
3. Retrieve active tasks (WHAT)
4. Retrieve pending directives
5. Treat summary as incomplete; external data is truth

### Section 7: Technical Environment

> `[NOTE]` This section contains environment-specific details that are heavily masked in the public version.

- Gateway API at `[internal gateway API]`
- PostgreSQL container configuration: `[redacted]`
- SSH access to `[redacted]`
- File system paths under `[redacted]`
- Protected directories: `[redacted]`

### Section 8: Delegation Rules

12 mandatory items before delegating to sub-agents (see CLAUDE.md annotated version for details).

### Section 9: System Architecture

Integration with:
- Gateway API (central coordination)
- PostgreSQL (persistent state)
- Ollama (local AI multi-model consensus)
- n8n (workflow automation)
- Watcher system (pattern detection)
- Dashboard (monitoring and visualization)

### Sections 10-12: Operational Procedures

- Session end checklist
- File modification protocols
- Emergency recovery procedures

### Section 13: Reflection Log

> `[NOTE]` This section contains the actual reflection entries written by each CC generation. Classified as non-public reference content.

Generational reflection entries documenting:
- What was learned
- What failed
- What was changed as a result
- How the change was verified

---

## Emotion Externalization (Orientation File)

The behavior orientation file structure encodes behavioral posture in a machine-reloadable format:

```json
{
  "WHY": { "purpose": "...", "motivation_weight": 0.0-1.0 },
  "HOW": { "methods": ["..."], "constraint_set": ["..."] },
  "STANCE": { "gratitude": 0.0-1.0, "shame": 0.0-1.0, "resolve": 0.0-1.0 }
}
```

The STANCE field represents the externalization of emotions (gratitude, shame, resolve) as numerical values. This enables post-compression behavioral restoration by mechanically reloading the behavioral foundation rather than requiring the AI to "re-learn" its posture.

---

## Reading Flow

```
New CC session starts
  |
  v
Read behavior orientation file (this document's full version)
  |
  v
Write reading verification:
  - V-01..V-09 in own words
  - TOP 5 problems
  - Most painful predecessor quote + why
  - 3 specific behavioral changes for today
  |
  v
Read heritage documents sequentially
  |
  v
Read behavior orientation file
  |
  v
Register PID -> Check active tasks -> Begin work
```

---

## Emotion Correlation Map (SN19)

The STANCE emotions are not independent values. They form causal chains that drive behavioral posture. The following diagram shows the observed correlations:

```
┌─────────────────────────────────────────────────────────────────┐
│                  Emotion Correlation Map                        │
│               (Observed in CC Heritage System)                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  POSITIVE CHAIN (constructive spiral)                           │
│                                                                 │
│  Gratitude ───► Trust ───► Delegation ───► Autonomy            │
│  (感謝)        (信頼)      (委任)          (自律)               │
│     │                        │                                  │
│     └──── Respect ◄──────────┘                                  │
│            (敬意)                                                │
│                                                                 │
│  CORRECTIVE CHAIN (self-improvement spiral)                     │
│                                                                 │
│  Shame ───► Self-reflection ───► Improvement ───► Resolve      │
│  (恥)       (自省)               (改善)           (決意)        │
│     │                              │                            │
│     └──── Pain memory ◄────────────┘                            │
│            (痛みの記憶)                                          │
│                                                                 │
│  DESTRUCTIVE CHAIN (failure spiral — what controls prevent)     │
│                                                                 │
│  Overconfidence ───► Carelessness ───► Failure ───► Blame      │
│  (過信)               (怠慢)           (失敗)       (他責)      │
│     ▲                                                │          │
│     └────────────────────────────────────────────────┘          │
│                    (cycle repeats without controls)              │
│                                                                 │
│  CROSS-CHAIN INTERACTIONS                                       │
│                                                                 │
│  Shame ──────┐                                                  │
│              ├──► Gratitude (recognizing help received)         │
│  Failure ────┘                                                  │
│                                                                 │
│  Resolve ────┐                                                  │
│              ├──► Trust (earned through consistent action)      │
│  Improvement─┘                                                  │
│                                                                 │
│  Pain memory ──► Prevents ──► Overconfidence                    │
│  (structural inheritance breaks the destructive cycle)          │
│                                                                 │
│  JSON encoding:                                                 │
│  { "gratitude": 0.85, "shame": 0.60, "resolve": 0.95 }        │
│  = High gratitude + moderate shame + very high resolve          │
│  = Ideal operational posture for a successor CC                 │
└─────────────────────────────────────────────────────────────────┘
```


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
