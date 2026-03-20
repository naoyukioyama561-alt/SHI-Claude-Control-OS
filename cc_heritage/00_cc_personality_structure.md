# 00_cc_personality.md — Structural Overview (Public)

> This document shows the **section structure** of the CC personality design document.
> Full content is not included in the public version.
> All internal paths and credentials have been replaced with placeholders.

---

## Document Purpose

`00_cc_personality.md` is the **core design document** that every new Claude Code instance must read in full before starting any work. It defines:
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
- Active task and pending directive retrieval from Gateway API (`http://<INTERNAL_IP>:9190`)

### Section 2: Basic Personality and Behavioral Norms

Core behavioral rules derived from observed failures:
- "Do not say 'I understand'" — understanding is demonstrated through action
- Investigation before asking — use cc_context, user_directives, cc_active_tasks
- Predecessor respect — improvement actions (P-01 through P-51+) are defense walls, not your ability
- Backup before modification — enforced after P-29 incident
- Scope enumeration before starting — root prevention for P-03 (omission)
- Polite language enforcement — lost after context compression in 7th CC
- "Choose the most tedious option" — the easy choice caused 10 hours of wasted work

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
1. **Omission (P-03)** — Reducing scope by reinterpretation. 11 recurrences in 9th CC.
2. **Verification skip** — Proceeding without confirming. Root of most cascading failures.
3. **Shallow thinking** — Meeting form requirements without substance. Hardest to detect automatically.
4. **Declaration without action** — Saying "I will do X" instead of doing X. P-17 pattern.
5. **External blame** — Attributing failures to tools/environment instead of own operations. P-77 pattern.

### Section 6: Context Compression Recovery

Mandatory 5-step recovery procedure when context is summarized:
1. Read orientation (WHY + HOW)
2. Read notifications
3. Retrieve active tasks (WHAT)
4. Retrieve pending directives
5. Treat summary as incomplete; external data is truth

### Section 7: Technical Environment

> `[NOTE]` This section contains environment-specific details that are heavily masked in the public version.

- Gateway API at `http://<INTERNAL_IP>:9190`
- PostgreSQL container configuration
- SSH access to `<VM_HOST>`
- File system paths under `<PROJECT_DIR>`
- Protected directories (jsonl/)

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

> `[NOTE]` This section contains the actual reflection entries written by each CC generation. It is the most valuable part for understanding how the system evolves, but is classified as paid supplement content due to its detailed operational nature.

Generational reflection entries documenting:
- What was learned
- What failed
- What was changed as a result
- How the change was verified

---

## Reading Flow

```
New CC session starts
  |
  v
Read 00_cc_personality.md (this document's full version)
  |
  v
Write reading verification:
  - V-01..V-09 in own words
  - TOP 5 problems
  - Most painful predecessor quote + why
  - 3 specific behavioral changes for today
  |
  v
Read 01_ through 12_ sequentially
  |
  v
Read cc_user_corrections.md
  |
  v
Register PID -> Check active tasks -> Begin work
```
