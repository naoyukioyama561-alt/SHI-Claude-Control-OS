# Failure Naming Template

Use this template to name and classify AI failures you observe in your own environment.

---

## Failure Record

| Field | Value |
|-------|-------|
| **ID** | FM-XXX or P-XXX |
| **Name** | (Short, descriptive name -- e.g., "Compression-first summarizer") |
| **Category** | (Output quality / Safety / Behavioral / Structural) |
| **One-line description** | |
| **Trigger condition** | (When does this failure fire?) |
| **Observable symptom** | (What does the user see?) |

## Analysis

| Field | Value |
|-------|-------|
| **Root cause** | (Why does this happen structurally?) |
| **Affected AI models** | (Claude / GPT / Copilot / Other -- with severity: Low/Med/High/V.High) |
| **Related FMs** | (Other FM IDs that co-occur or share root cause) |

## Countermeasure

| Field | Value |
|-------|-------|
| **Prevention rule** | (What rule in system prompt/CLAUDE.md prevents this?) |
| **Detection method** | (How do you observe whether it fired?) |
| **Verification method** | (How do you confirm the countermeasure works?) |
| **Effectiveness** | (Observed suppression rate: None/Partial/High/Complete) |

## Recurrence Management

| Field | Value |
|-------|-------|
| **Recurrence count** | |
| **Pattern promotion** | (If 3+ recurrences: escalate to structural countermeasure) |
| **Structural fix** | (Hook/block/external monitoring/inheritance lock) |

---

> Reference: [FM-40 Cheatsheet](../try/fm-40-cheatsheet.md) | [10-framework/01-failure-modes](../../10-framework/en/01-failure-modes.md)
