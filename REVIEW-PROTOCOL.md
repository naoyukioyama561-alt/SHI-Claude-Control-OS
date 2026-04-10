# Review Protocol — レビュー再発防止手順書

This document supplements PUBLIC-EXPRESSION-GUIDE.md (PEG).
Reviewers must follow both PEG and this protocol.

---

## Purpose

Prevent the following review failures:
- Rating △ violations as ○ (baseline violations treated as "○ with remaining issues")
- Skipping Section 25 baseline checklist mapping
- Assigning ratings by impression instead of structural verification

---

## Mandatory Review Phases

### Phase 1: Scan (find violations only — do NOT rate yet)
- Traverse all files
- List every violation candidate
- Do NOT assign △/○/◎ at this stage

### Phase 2: Map to Section 25 Baseline Checklist
For each violation found in Phase 1:

1. **Q1**: Which Section 25 baseline condition does this violate? (cite condition number and text)
2. **Q2**: Which PEG Section does that condition reference? (cite Section number)
3. **Q3**: Is this violation in one file or does it propagate to multiple files/items?

- If a baseline condition is matched → **△ lock** for that item
- If no baseline condition is matched → classify as resonance gap (○/◎ boundary)

### Phase 3: Rate (only after Phase 2 is complete)

Conversion rule (mechanical, no judgment):
- Baseline FAIL (any condition) → **△**
- Baseline PASS + Resonance FAIL → **○**
- Baseline PASS + Resonance PASS → **◎**

### Phase 4: Baseline Declaration (mandatory output before final rating)

For each of the 5 items, output:
```
[Item name baseline check]
- Condition 1: ✅/✗ → if ✗, cite file:line
- Condition 2: ✅/✗ → if ✗, cite file:line
...
→ baseline PASS/FAIL → rating locked to ○/△
```

This output is mandatory. Skipping it invalidates the review.

### Phase 5: Reverse Check (before submitting final output)
- If rating is ○: confirm baseline FAIL count = 0
- If rating is ◎: confirm baseline FAIL = 0 AND resonance FAIL = 0
- If any contradiction → stop and downgrade

---

## Prohibited Review Patterns

| Pattern | Why prohibited | Correct behavior |
|---------|---------------|-----------------|
| "○ with remaining issues" | Baseline violation = △, not ○ | Rate △, then provide fix plan |
| "Almost ◎" | Soft ◎ is invalid per PEG Section 25 | Rate ○, cite missing resonance conditions |
| "Broadly compliant" | "Every" means every, not most | Check every instance |
| Rating by impression before checklist | Skips structural verification | Always Phase 2 before Phase 3 |
| Mixing baseline and resonance fixes | Conflates △→○ with ○→◎ | Separate fix plans: △→○ first, then ○→◎ |

---

## Fix Plan Format

When violations are found, provide two separate plans:

### Plan A: △→○ (baseline fixes — must be done first)
For each △ item:
- File:line
- Current text
- Proposed fix
- Which baseline condition this resolves

### Plan B: ○→◎ (resonance fixes — only after all △ are resolved)
For each ○ item:
- Which resonance condition is not met
- File:line where the gap is visible
- Proposed improvement

---

## Canonical Label Enforcement

Labels are checked by **allowlist only**:
- `[observed: ...]`
- `[design target]`
- `[illustrative]`
- `[illustrative scenario: not verified]`

Any label not exactly matching the allowlist is a baseline FAIL.
"Close enough" does not pass. Spelling, punctuation, and format must be exact.

---

## Number Scan (independent from text review)

Every review must include a dedicated number scan:
- Search for: %, x, times, items, hours, days, N=, ranges (80-90%), ratios (1/20)
- For each number: verify label is directly attached, canonical, and in allowlist
- Any unlabeled number = baseline FAIL for 誤読耐性

---

## EN/JA Parity Check (comparison review, not separate reviews)

- Build a comparison table for evidence labels, tone strength, scope qualifiers
- If one side is stronger → baseline FAIL for EN/JA parity condition
- "Meaning is close" does not pass — impression strength must match
