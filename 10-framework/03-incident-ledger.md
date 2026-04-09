# Incident Ledger (Public Core)
Language: [日本語版はこちら / Japanese version](../ja/10-framework/03-incident-ledger-ja.md)

A ledger of real-world failures formatted as shareable, reproducible learning units.

Principle:
- **One incident = one file**
- Each incident must include:
  - What happened (observable)
  - Why it happened (root pattern)
  - How it was fixed
  - How recurrence is prevented (Control OS patch)
  - How to verify it is resolved

Public-safe:
- Replace all endpoints/paths/identifiers with placeholders.

---

## 1. Where incidents live

Incident files should be organized by language:
- `ledger/incidents/EN/`
- `ledger/incidents/JA/`

Index files:
- `ledger/incidents/EN/000_INDEX.md`
- `ledger/incidents/JA/000_INDEX.md`

---

## 2. Standard incident format

Required structure:

### 1) Title
`<INCIDENT_ID> — <SHORT_NAME>`

### 2) Context
What was being attempted.

### 3) Symptoms (observable)
What was seen.

### 4) Root pattern
Link to a Failure Mode ID (FM-xx) and explain the mechanism.

### 5) Fix (immediate)
Concrete steps taken (public-safe, no endpoints/paths).

### 6) Prevention (permanent)
What was changed in Control OS (rule/check/tooling).

### 7) Verification
How to confirm resolution.

### 8) Notes
Non-sensitive nuance.

---

## 3. Classification and linking

Each incident must link:
- At least one Failure Mode ID (`FM-xx`)
- At least one Control OS section (rule/check updated)

This avoids "story-only" content and turns the ledger into a control system.

---

## 4. What makes an incident high-impact

A high-impact incident:
- Is recognizable ("I've seen this happen")
- Has a clear failure signature
- Shows the minimal control that prevents recurrence
- Is easy to share as a single file

---

## 5. Redaction rules (ledger-specific)

Replace, always:
- Hostnames/endpoints -> `<HOSTNAME>`, `<ENDPOINT>`
- Local paths -> `<LOCAL_PATH_WIN>`, `<LOCAL_PATH_LINUX>`
- Private handles/emails -> `<PRIVATE_HANDLE>`, `<EMAIL>`
- Runbooks/topology hints -> `<RUNBOOK_REF>`, `<INFRA_TOPOLOGY_REF>`

Keep:
- The causal chain
- The control patch
- The verification steps (abstracted)

---

## Example incident template

```markdown
# RT-001 — Example Incident Title

## Context
The coding agent was asked to update a configuration file for a monitoring service.

## Symptoms
- The agent modified a file it was not supposed to touch
- No backup was created before modification
- The original file content was lost

## Root pattern
- FM-32 (Requirement invention): The agent added constraints not in the original request
- FM-06 (Output-first reasoning): Decided the modification was needed before verifying

## Fix
1. Restored file from backup (manual)
2. Re-ran the original task with explicit scope constraints

## Prevention
- Added Control OS rule 5.1: Files not newly created must not be modified by default
- Added mandatory backup requirement before any file modification

## Verification
- Confirmed original file is restored
- Tested that the new rule blocks unprompted file modifications

## Notes
This pattern was observed across multiple sessions.
The backup requirement was later formalized as a hard prohibition.
```


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
