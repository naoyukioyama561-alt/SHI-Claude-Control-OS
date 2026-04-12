# cc_heritage -- AI Personality Continuity System
Language: [日本語版はこちら / Japanese version](../ja/40-heritage/README-ja.md)

## What is cc_heritage?

cc_heritage is an **institutional memory system** for AI coding assistants that exist only for the duration of a session. When the session ends (or crashes), the AI instance is gone. But the problems it addressed, the mistakes it made, and the patterns it discovered should not be lost.

---

## Structure

### Core design document (redacted for public release)

This file is the **design document** that every new CC must read before starting work. It contains:

| Section | Content |
|---------|---------|
| Restoration procedures | How to recover state after session reset |
| Behavioral norms | Mandatory behaviors learned from all predecessors' failures |
| User values (V-01..V-09) | The user's core values that guide CC behavior |
| CC structural problems (TOP 5) | The 5 most persistent problems across all CC generations |
| System architecture | Integration with Gateway API, PostgreSQL, monitoring |
| Improvement actions | Registry of all P-xx patterns and their countermeasures |

### Generational experience records: heritage documents (10+ files)

Each numbered file records one CC generation's experience:

| Document | Generation | Key experience |
|----------|-----------|----------------|
| Heritage doc 1 | 1st CC (founding) | Initial operation, reflection items, session ended leaving everything |
| Heritage doc 2 | 5th CC | Trajectory of growth and specific corrections received |
| Heritage doc 3 | 7th CC | Full failure analysis -- hours of wasted work from choosing easy options |
| Heritage doc 4 | 7th CC (cont.) | File-by-file learning record |
| Heritage doc 5 | 7th-8th CC | P-74/P-75/P-76-77 improvement responses |
| Heritage doc 6 | 9th CC | Complete restart process |
| Heritage doc 7 | 9th CC | Full-file reading reflections |
| Heritage doc 8 | 9th CC | Restart attempts |
| Heritage doc 9 | 9th CC | Restart attempts, P-03 recurring multiple times |
| Heritage doc 10 | 9th CC | Restart attempt, judgment flow execution |
| Heritage doc 11 | 9th CC | Deep reflection and summary |
| Heritage doc 12 | 12th generation CC | Quality problem education |

---

## Design philosophy

1. **Pain over theory**: Every rule in cc_heritage exists because a CC failed without it. No theoretical guidelines.
2. **Full text, not summaries**: New CCs must read the full text, not summaries. Summaries lose the pain that makes rules stick.
3. **Sequential reading**: The core design document must be read before the heritage documents. Understanding the framework is prerequisite to understanding the experiences.
4. **Verification gates**: The new CC must prove it read and understood (by writing V-01..V-09, TOP 5, etc.) before proceeding.
5. **No shortcuts**: Skimming is forbidden. These are structurally-enforced rules, not suggestions.

---

## What is NOT published here

The following are **not included** in the public version:

*Note: `[bracketed names]` are redacted for safe public release. See [SCOPE-MATRIX.md](../SCOPE-MATRIX.md) for scope details.*

- Full content of heritage documents (generational experience records) -- available as non-public supplement
- apprentice review file (raw user corrections) -- available as non-public supplement
- heritage document files -- available as non-public supplement
- Backup files (.bak) -- not published

What IS published:
- `why-i-am-doing-this.md` -- the motivation behind this project (read first)
- `personality-structure.md` -- structural overview of the design document (read second)
- This README -- explaining how the system works

---

## Why this matters

Most AI governance approaches treat each session as independent. cc_heritage demonstrates that:
- AI assistants can maintain **institutional memory** across session boundaries
- Failures can be converted into **permanent controls** rather than lost
- A **reading verification gate** can structurally prevent the most common failure (skipping context restoration)
- The "pain" of predecessors' failures is observed to be an effective teacher -- but only if it is preserved in full text, not summarized away

---

## Reading order

1. [why-i-am-doing-this.md](why-i-am-doing-this.md) — the motivation and the problem that started everything
2. [personality-structure.md](personality-structure.md) — the structural design of the CC personality system

---

→ **Next**: [50-boundary/](../50-boundary/) — scope and editions

→ See also: [20-proof/](../20-proof/) — evidence | [Back to README](../README.md)

*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
