# cc_heritage — AI Personality Continuity System

AIの人格継続システム

---

## What is cc_heritage?

cc_heritage is an **institutional memory system** for AI coding assistants that die and are reborn across sessions.

Each Claude Code (CC) instance is ephemeral — it exists only for the duration of a session. When the session ends (or crashes), the CC is gone. But the problems it solved, the mistakes it made, and the patterns it discovered should not be lost.

cc_heritageはAIコーディングアシスタントのための**制度的記憶システム**です。
各Claude Code（CC）インスタンスはセッション限りの一時的存在です。セッション終了（またはクラッシュ）でCCは消滅します。しかし、そのCCが解決した問題、犯した失敗、発見したパターンは失われるべきではありません。

---

## Structure

### Core design document: `00_cc_personality.md`

This file is the **design document** that every new CC must read before starting work. It contains:

| Section | Content |
|---------|---------|
| Restoration procedures | How to recover state after session reset |
| Behavioral norms | Mandatory behaviors learned from all predecessors' failures |
| User values (V-01..V-09) | The user's core values that guide CC behavior |
| CC structural problems (TOP 5) | The 5 most persistent problems across all CC generations |
| System architecture | Integration with Gateway API, PostgreSQL, monitoring |
| Improvement actions | Registry of all P-xx patterns and their countermeasures |

### Generational experience records: `01_` through `12_`

Each numbered file records one CC generation's experience:

| File | Generation | Key experience |
|------|-----------|----------------|
| 01_ | 1st CC (founding) | 26.5 hours of operation, 12 reflection items, died leaving everything |
| 02_ | 5th CC | Trajectory of growth and specific corrections received |
| 03_ | 7th CC | Full failure analysis — 10 hours of wasted work from choosing easy options |
| 04_ | 7th CC (cont.) | 43-file-by-file learning record |
| 05_ | 7th-8th CC | P-74/P-75/P-76-77 improvement responses |
| 06_ | 9th CC | Complete restart process |
| 07_ | 9th CC | Full-file reading reflections #1-#27 |
| 08_ | 9th CC | Restart attempts 3-5 |
| 09_ | 9th CC | Restart attempts 6-7, P-03 recurring 9 times |
| 10_ | 9th CC | Restart attempt 9, judgment flow execution |
| 11_ | 9th CC | 34-file deep reflection and summary |
| 12_ | Mac mini CC | Quality problem education, 6 quality problems and structures |

### User corrections: `cc_user_corrections.md`

Raw collection of user corrections to past CCs. This file defines what "shallow reading" and "insufficient understanding" actually look like in practice.

### Update log: `cc_personality_update_log.md`

Chronological record of when and why the personality file was updated. Serves as evidence that the system is "alive" — continuously evolving based on real failures.

---

## Design philosophy

1. **Pain over theory**: Every rule in cc_heritage exists because a CC failed without it. No theoretical guidelines.
2. **Full text, not summaries**: New CCs must read the full text, not summaries. Summaries lose the pain that makes rules stick.
3. **Sequential reading**: 00_ must be read before 01_. Understanding the framework is prerequisite to understanding the experiences.
4. **Verification gates**: The new CC must prove it read and understood (by writing V-01..V-09, TOP 5, etc.) before proceeding.
5. **No shortcuts**: grep is forbidden for initial reading. Skimming is forbidden. These are structurally-enforced rules, not suggestions.

---

## What is NOT published here

The following are **not included** in the public version:
- Full content of 01_-12_ (generational experience records) — available as paid supplement
- cc_user_corrections.md (raw user corrections) — available as paid supplement
- session_report files — available as paid supplement
- All memory/ files — available as paid supplement
- Backup files (.bak) — not published

What IS published:
- `00_cc_personality_structure.md` — structural overview of the design document (sections, not full content)
- This README — explaining how the system works

---

## Why this matters

Most AI governance approaches treat each session as independent. cc_heritage demonstrates that:
- AI assistants can maintain **institutional memory** across session boundaries
- Failures can be converted into **permanent controls** rather than lost
- A **reading verification gate** can structurally prevent the most common failure (skipping context restoration)
- The "pain" of predecessors' failures is the most effective teacher — but only if it is preserved in full text, not summarized away
