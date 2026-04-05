# Quality System Design (Public Structure)

AI quality degrades silently. By the time you notice, the damage is already in your codebase. This system catches degradation at four structural layers before it reaches your output.

> This document shows the **structural overview** of the quality system.
> Detailed implementation requirements (REQ-xx) are not included in the public version.

---

## Overview

A quality system addressing 6 structural problems in AI coding assistants:
1. Skipping verification
2. Not reading required materials
3. Omitting items
4. Careless work
5. Declaring instead of acting
6. Shallow thinking

Operates on top of existing subsystems ([redacted]).

---

## 4+1 Layer Architecture

| Layer | Responsibility | Existing Integration |
|-------|---------------|---------------------|
| Layer 0 (Observation Gate) | Pre-execution: observe, define target, confirm approval | [redacted] |
| Layer 1 (Self) | Self-detection + immediate correction | audit_log self-recording |
| Layer 2 (Structure) | Hook/watcher auto-detection + rollback | hooks, [redacted], pattern detection |
| Layer 3 (Completion Definition) | Evidence + 5-set inspection | [redacted] |
| Layer 4 (Third-party Verification) | Pattern escalation + incident logging + learning control | [redacted] |

---

## Mandatory 5-Set (All Problems)

Every completion report must include:

| Set | Content | Example |
|-----|---------|---------|
| Preconditions | Existing features/files this work depends on | "Gateway API is running" |
| Prohibitions | What must not be done | "Reusing previous results" |
| Execution observation | Logs/status to check | "curl response code" |
| PASS criteria | What constitutes success | "HTTP 200 + JSON response" |
| Rollback | Recovery on failure | "Submit correction report + check cascading effects" |

---

## reason_code System

| Code | Problem | Detection Layer |
|------|---------|-----------------|
| SKIP_SELF_DETECTED | Skipped verification (self-detected) | Layer 1 |
| POLL_SKIP_HOOK_BLOCKED | Polling skip (hook detected) | Layer 2 |
| POLL_SKIP_CONSECUTIVE | Consecutive polling skip | Layer 2 |
| STALE_EVIDENCE | Reused old results | Layer 3 |
| DISCREPANCY_DETECTED | Mismatch with [redacted] | Layer 4 |
| READ_SKIP_SELF_DETECTED | Skipped reading (self-detected) | Layer 1 |
| UNVERIFIED_NO_TOOL | Report without tool usage | Layer 2 |
| READ_SKIP_P49 | Mandatory file read skipped (P-49) | Layer 2 |
| MISQUOTE_DETECTED | Quote does not match actual content | Layer 4 |
| MISSING_ITEMS | Numbered items missing | Layer 2 |
| MISSING_EVIDENCE | No evidence attached | Layer 3 |
| MISSING_RESPONSE | Unanswered points exist | Layer 2 |
| CONSTRAINT_VIOLATION | Constraint/prohibition missed | Layer 2 |
| SIDE_EFFECT_UNDOCUMENTED | Side effects not documented | Layer 2 |
| SEMANTIC_FAIL | B-3/B-4 failed (semantic gap) | Layer 3 |
| AMBIGUOUS_INSTRUCTION | Instruction unclear (completion criteria undefined) | Layer 3 |
| CAPABILITY_LIMIT | Exceeds CC capability | Layer 4 |
| APPROVAL_REQUIRED | Destructive operation awaiting approval | Layer 0 |
| B1_OMISSION | Content omitted | Layer 3 |
| B2_FORMAT_DEVIATION | Format deviation | Layer 3 |
| B3_INTERPRETATION_SHRINK | Request interpretation shrunk | Layer 3 |
| B4_IMPLEMENTATION_GAP | Actual behavior differs from report | Layer 3 |
| B5_INSTRUCTION_ALTERED | Instruction altered | Layer 3 |
| P17_DECLARE_ONLY | Declaration only (no action) | Layer 2 |
| P17_CONSECUTIVE | Consecutive declarations | Layer 2 |
| MISSING_ACTION | implement instruction with action_count=0 | Layer 3 |
| INCOMPLETE_SPEC | 5-set incomplete | Layer 3 |
| PADDING_DETECTED | Adjacent sections are paraphrases (Jaccard > 0.7) | Layer 2 |
| ABSTRACT_DESIGN | No concrete references in 500+ char design | Layer 2 |
| COUNCIL_REVIEW_FAIL | Council review found 3+ issues | Layer 2 |
| SHALLOW_SELF_DETECTED | Shallow output (self-detected) | Layer 1 |

---

## Pattern Escalation Conditions

| Condition | Action |
|-----------|--------|
| Same reason_code occurs 2+ times | Register as pattern in [redacted] |
| Omission causes user pushback | Record in [redacted: database table] + register pattern |
| Same reason_code occurs 3+ times | Record in incident log -> trigger permanent countermeasure |

---

## Learning Escalation Conditions

| Condition | Learning Data Category |
|-----------|----------------------|
| verify pass + [redacted: monitoring service] pass + 5-set complete | High-quality data (priority accumulation) |
| fail -> correction -> pass cycle | Correction learning data (separate category) |
| Contains MISQUOTE / declaration-only / false report | Excluded (contamination prevention) |
| 5-set incomplete | Excluded |

*Note: `[redacted: monitoring service]`, `[redacted: database table]` etc. are redacted for safe public release. See [SCOPE-MATRIX.md](../../SCOPE-MATRIX.md) for what is available in each tier.*

---

## Problem-Layer Mapping

| Problem | What it guarantees | Detection method |
|---------|-------------------|-----------------|
| #1 No skipping verification | Did you call the API? | Hook block + raw_output verification |
| #2 Read what needs reading | Did you read the file? | Context read record + quote matching |
| #3 No omissions | Did you do all items? | items_count matching + check-response |
| #4 Careful work | Does it match the design? | Verification B-axis 5 items |
| #5 Action, not words | Did you take action? | action_count + P-17 detection |
| #6 Deep thinking | Is there substance? | Jaccard coefficient + concrete references + council auto-review |

Problems #1-5 guarantee form. Problem #6 guarantees meaning. All 6 must pass for "deep work."

---

## Response Chain Pattern (Generic)

```
Task received
  |
Layer 0: Observe current state -> Define target -> Check approval -> Start
  |
Layer 1 (Self): Execute -> Self-check -> Report
  | (miss)
Layer 2 (Structure): Auto-detect -> Block/flag -> Return to CC
  | (report submitted)
Layer 3 (Completion): Evidence check -> 5-set check -> Verify
  | (pass)
Layer 4 (Third-party): Pattern check -> Learning categorization -> Complete
  | (fail)
Escalation: 2x same code -> pattern registration -> 3x -> incident
```
