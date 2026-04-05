# PROVE IT -- Public Verification Protocol

This document exists not to convince you, but to help you **evaluate how far you can verify each claim** using only publicly available information.

---

Note: Square-bracket placeholders (e.g., `[external monitoring hook]`, `[internal database table]`, `[redacted]`) are intentional redactions for safe public release. They are not incomplete content.

Throughout this repository, `[redacted]` labels mark specific implementation details -- such as service names, database tables, or monitoring logic -- that have been withheld to prevent reproduction of the paid-tier system from public information alone. The surrounding context (design rationale, metrics, methodology) remains fully public so that readers can evaluate the approach without needing access to the redacted specifics.

## Verification Rule

Every claim in this repository falls into one of the following verification categories:

| Status | Definition | Reader action |
|--------|-----------|--------------|
| **Publicly usable** | You can copy-paste and test it yourself right now | Try it: [30-adoption/try/](30-adoption/try/) |
| **Publicly inspectable** | Design documents and methodology are fully public | Read and assess: [10-framework/](10-framework/) |
| **Publicly challengeable** | Claims are stated with evidence; you can dispute them | Challenge via [Issues](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS/issues) |
| **Publicly reproducible** | Methodology is documented enough to attempt reproduction | Build in your environment using [templates](30-adoption/templates/) |
| **Privately evidenced** | Evidence exists but is in paid tiers (design docs, logs, images) | Available in Phase1/Phase2 |
| **Conceptual only** | Theoretical framework without direct operational evidence | Assess on logical merit |

For how these statuses are displayed across the repository, see [SCOPE-MATRIX.md -- Display Rules](SCOPE-MATRIX.md#display-rules-for-github-5-points).

---

## Claim Map

| # | Claim | Verification status | Where to verify |
|---|-------|-------------------|-----------------|
| 1 | AI failure modes are observable and classifiable | **Publicly usable** | [FM-40 Cheatsheet](30-adoption/try/fm-40-cheatsheet-en.md) -- test on your own AI |
| 2 | Control OS suppresses common failure modes | **Publicly usable** | [Before/After Demo](30-adoption/try/before-after-demo-en.md) -- run the test yourself |
| 3 | 132 failure modes were classified | **Publicly inspectable** (40-item public taxonomy, FM-01 to FM-06 detailed) / **Privately evidenced** (full 132) | [01-failure-modes](10-framework/en/01-failure-modes.md) |
| 4 | Three-layer separation improves monitoring quality | **Publicly inspectable** | [Three-layer design](10-framework/en/04-three-layer.md) |
| 5 | External monitoring achieves higher detection rates than self-monitoring | **Publicly inspectable** (rates published) / **Privately evidenced** (N-counts) | [Metrics](20-proof/metrics.md) |
| 6 | Heritage system enables cross-session behavioral continuity | **Publicly inspectable** | [Heritage](40-heritage/personality-structure.md) |
| 7 | 4+1 layer quality system reduces quality failures | **Publicly inspectable** | [Quality system](10-framework/en/05-quality-system.md) |
| 8 | SHI theory provides a foundation for AI governance | **Conceptual only** | [Research comparison](10-framework/en/06-research-comparison.md) |

This is an 8-umbrella-claim map covering the [15 achievements](20-proof/achievements/README.md). Claim 1 → Achievements 1, 10; Claim 2 → Achievement 2; Claim 3 → Achievement 1; Claim 4 → Achievements 2, 3; Claim 5 → Achievement 3; Claim 6 → Achievements 9, 12; Claim 7 → Achievement 4; Claim 8 → Achievement 5.

---

## How to Read This Repository (Evaluation Protocol)

### Step 1: Try it (5 minutes)
Paste the Control OS into your AI. Run the Before/After test. Observe whether failure modes are suppressed.

### Step 2: Inspect the methodology (30 minutes)
Read the framework documents. Assess whether the structural analysis is logically sound.

### Step 3: Check the evidence (15 minutes)
Review the achievements, metrics, and timeline. Note which claims are publicly verifiable and which require paid tiers.

### Step 4: Challenge what you disagree with
Open an Issue using the [Challenge a Claim](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS/issues/new?template=claim-challenge.md) template. State your observation, what you expected, and what you actually saw.

### Step 5: Decide
Based on your own verification, decide whether the methodology is worth applying in your environment.

---

## What NOT to Do

- Do not assume all claims are true because the documentation is thorough
- Do not assume all claims are false because some evidence is behind paid tiers
- Do not evaluate the project based on the author's credentials -- evaluate it based on whether it works when you try it

## Proper Evaluation Stance

This repository should be evaluated on:
1. **Does the Control OS observably suppress failure modes when you test it?**
2. **Is the structural analysis logically coherent?**
3. **Are the public claims consistent with the public evidence?**

If the answer to all three is yes, the methodology has value regardless of what is or is not in the paid tiers.

---

> See also: [SCOPE-MATRIX](SCOPE-MATRIX.md) | [START-HERE](START-HERE.md) | [Back to README](README.md)

[日本語版 / Japanese](PROVE-IT-ja.md)
