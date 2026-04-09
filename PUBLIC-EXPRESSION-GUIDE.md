# Public Expression Guide — 公開表現定義集
Language: [日本語版はこちら / Japanese version](ja/PUBLIC-EXPRESSION-GUIDE-ja.md)

Version: 4.1 | Last updated: 2026-04-07

This document is the single source of truth for every expression used in this public repository.

---

## 0. Applicability Surface

This guide applies to **all externally visible expressions**, including:

| Surface | Examples | Sections that apply |
|---------|----------|-------------------|
| Markdown body text (EN/JA) | README, achievements, framework docs | 1,2,3,4,5,6,7 |
| Headings / titles (H1-H6) | Page titles, section headings | 1,3,5 (no brackets) |
| Demo HTML (UI-visible text) | demo/*.html, ja/demo/*.html | 3,4,8 |
| SVG embedded text | `<text>`, `<title>`, `<desc>`, legends | 2,3,8 |
| alt text / ARIA labels | `alt=""`, `aria-label=""` | 3,4 |
| HTML meta / OGP tags | `<title>`, `<meta og:title>`, `<meta description>` | 1,3,4 (SNS crop test) |
| File names / URL slugs | `01-failure-modes.md`, anchor IDs | Filename rules (below) |
| Code block comments | `# comment text` | 3 (comments only, not code) |
| Code block output examples | Fenced block sample output | 3 |
| CITATION.cff fields | `abstract:`, `keywords:` | 1,3 |
| Issue/PR templates | `.github/ISSUE_TEMPLATE/*.md` | 3,9 |
| GitHub repo description | About field | 1 |
| Badges | shields.io URLs | Filename rules |

**Not in scope**: Code logic itself (functional code, not comments).

**Safety scan clarification**: "Token" in security context means authentication tokens, API keys, secrets — NOT general English words like "Token Monitor" (a dashboard page title) or "token consumption" (a methodology term).

---

## 1. Project Identity

| Item | Defined Expression | Prohibited | SNS-safe 1-line |
|------|-------------------|------------|-----------------|
| Repository name | SHI-Claude-Control-OS | SHI-Control-OS, Control OS (standalone) | SHI-Claude-Control-OS |
| What this is | A structural governance methodology | Product, tool, software, platform, service | "AI governance methodology — copy-paste templates + verification guide" |
| Scope | For reducing repeated AI failures | For eliminating / guaranteeing / solving | "Reduces repeated AI failures in the author's observed environment" |
| Author stance | One attempt to break the pattern | Breaks the pattern, solves the problem | "One documented approach — verify in your environment" |

---

## 2. Evidence Labels (Vocabulary Rules)

Every number, claim, or result must carry exactly one **evidence class** and zero or more **qualifiers**. No unlabeled claims.

### General rule (applies to ALL numbers, not just listed ones)

| If the number is... | Assign evidence class | Then add qualifiers as needed |
|---------------------|----------------------|------------------------------|
| Measured in author's environment | `[observed]` | `single environment`, `single operator`, `N undisclosed` |
| An architecture goal, not measured | `[design target]` | — |
| An example or explanatory value | `[illustrative]` | — |
| A hypothetical extrapolation | `[illustrative scenario]` | `not verified` |
| None of the above | **Do not use.** Route to Section 10 (Review required) | — |

### Canonical label format

```
[evidence-class: qualifier1, qualifier2]
```

Example: `[observed: single environment, N undisclosed]`

### Composition rule (how labels and tone markers work together)

Every claim-bearing sentence needs **both**:
1. An **evidence label** (from this section) — attached to the number or claim
2. A **tone marker** (from Section 3) — embedded in the sentence structure

Example: "In the author's environment **[tone marker: observed fact]**, detection rate was ~100% **[observed: single environment, N undisclosed]** **[evidence label]**."

### Specific numbers (canonical forms)

| Number | Canonical label | Prohibited usage |
|--------|----------------|-----------------|
| 132 | `[observed: single environment]` | "132 proven failure modes" |
| ~100% | `[observed: single environment, N undisclosed; not a product claim]` | "100%" without tilde |
| 65% | `[design target]` | "65% improvement" without label |
| 20x | `[design target]` | "20x faster" without label |
| 12+ | `[observed]` + context sentence | Standalone "12 generations" |

Numbers not listed here: apply the general rule above.

### Exceptions (no label required)
- **Conceptual comparisons without numbers** (e.g., Before/After tables describing behavior changes) — these are `[illustrative]` by nature and do not need inline labels
- **Section/heading structure numbers** (e.g., "3-layer", "4+1", "5-layer") — these are structural names, not claims
- **Time estimates for reader actions** (e.g., "30 seconds", "5 minutes", "15 minutes") — these are usage guidance, not measured claims

---

## 3. Meaning Rules (What may be claimed)

### Assertion Tone — 4 levels with mechanical markers

| Level | When to use | Required markers (at least one) | Prohibited markers |
|-------|-------------|--------------------------------|-------------------|
| **Observed fact** | Single-environment measurement | "In the author's environment", "was observed", "in the documented environment" | "proves", "guarantees", "always" |
| **Design intention** | Architecture goal | "designed to", "intended to", "the design goal is" | "achieves", "ensures", "eliminates" |
| **Conditional** | Cross-environment applicability | "should be validated", "may vary", "readers should verify" | "any AI system", "all environments", "universally" |
| **Invitation** | Reader action | "try", "verify", "challenge", "in your environment" | "you must", "you need to buy" |

### Prohibited assertion patterns

| Pattern | Why prohibited | Replace with |
|---------|---------------|-------------|
| "fundamentally unreliable" | Universal claim from single observation | "was not reliable enough in the observed environment" |
| "dramatically improved" | Unmeasured superlative | "substantially improved in the observed environment" |
| "near-zero human intervention" | Sounds like product guarantee | "substantially lower human intervention was observed" |
| "proof it works" | Implies universal proof | "verification record under stated conditions" |
| "any AI system" | Untested universality | "intended to be portable; validate in each environment" |
| "guarantees" / "ensures" / "保証する" | Product warranty language | "designed to" / "intended to support" |

---

## 4. Reception Rules (How readers will interpret)

### First-impression test
For every page, answer: "If a skeptical engineer opens this page directly from a GitHub file browser (not via README), what is their first impression?"

| Impression | Acceptable? | Action |
|-----------|-------------|--------|
| "This is well-organized" | ◎ | Keep |
| "This looks professional" | ○ | Keep |
| "What's [internal database table]?" | ✗ | Remove brackets from visible position |
| "Is this a sales page?" | ✗ | Remove commercial language |
| "This seems like unfinished work" | ✗ | Clean up redaction artifacts |
| "This claim seems too strong" | ✗ | Add observation scope label |

### SNS crop test
For every file's opening 1-2 sentences: "If only this text is posted on X, does the author's reputation benefit or suffer?"

| Outcome | Action |
|---------|--------|
| Benefit ("this person is careful and honest") | ◎ Keep |
| Neutral | ○ Acceptable |
| Suffer ("this person is making grand claims") | ✗ Rewrite with scope label |

---

## 5. Redaction Expressions

### Classification

| Classification | Rule | Example |
|----------------|------|---------|
| **Permitted** | Natural-language description, no brackets | "private data store", "internal gateway API" |
| **Conditionally permitted** | In `> Note:` blocks explaining redaction system, **only after the first heading + opening description** (not in the first-impression zone — title, badges, and opening sentence must be bracket-free) | "`[external monitoring hook]` is a redacted label..." |
| **Prohibited** | Brackets in titles, UI text, tables, callouts | `# Achievement ([internal database table])` |
| **Requires review** | New redaction patterns not listed here | File issue before using |

### Title-safe replacements

| Internal concept | Title/UI expression | Body text expression |
|-----------------|--------------------|--------------------|
| Internal database tables | PostgreSQL-based / private data store | "internal data store (name withheld for public release)" |
| Behavior orientation file | Orientation File | "behavior orientation file" |
| Apprentice review file | (omit from title) | "apprentice review file" |
| Monitoring service | External monitoring | "external monitoring hook" |
| Internal paths/scripts | (omit from title) | "(omitted for public release)" |

---

## 6. Scope & Phase Expressions

| Item | Defined Expression | Prohibited |
|------|-------------------|------------|
| This repository | Public repository | Free tier, free version |
| Phase 1 / Phase 2 | Future open release phases | Paid tier, paid version |
| Clarification note | "Phase 1 / Phase 2 = future open release phases, not paid tiers" | (omitting this near Phase references) |
| Primary surface | "This repository is the primary evaluation surface" | "Free tier is sufficient" |
| 有料/無料 | 公開版 / 非公開版 or Phase1/Phase2 | 有料版, 有料ティア, 無料版 |

---

## 7. EN/JA Interpretation Symmetry

**Rule: EN and JA must produce the same reader impression, not the same literal text.**

| Dimension | How to check |
|-----------|-------------|
| Assertion strength | Does the JA version sound more authoritative than EN? If yes, soften JA |
| Responsibility scope | Does one version imply broader applicability? Align to the narrower scope |
| Formality level | JA natural formality ≠ EN authority. "です/ます" is neutral, not authoritative |
| Evidence labels | Same labels in both languages (EN label + JA translation in parentheses) |

### Common asymmetry patterns to catch

| EN (OK) | JA (too strong) | JA (corrected) |
|---------|----------------|----------------|
| "was observed to..." | "〜することが確認された" | "〜する傾向が観測された" |
| "designed to..." | "〜を保証する" | "〜を支援する設計" |
| "in the author's environment" | (omitted) | "著者の環境では" |
| "this methodology is intended to be portable" | "どのAIにも適用可能" | "移植可能を目指しているが各環境で検証が必要" |

---

## 8. Image & Demo Definitions

Every image and demo page is a standalone public artifact.

### Images

| Image file (EN/JA pair) | Shows | Does NOT show | Required caption if cropped |
|-----------|-------|--------------|----------------------------|
| before-after-comparison | Conceptual before/after of behavior | Not measured data | "Conceptual — verify with PROVE-IT.md" |
| cc-heritage-inheritance | Heritage weight transfer concept | Not operational data | "Conceptual design — verify in your environment" |
| dashboard-overview | Dashboard layout concept | Not live dashboard | "Illustrative layout — all values are samples" |
| detection-trend-comparison | Detection trend visualization | Not benchmark | "Single environment trend — see metrics.md" |
| mini-quality-layers | Quality system overview (compact) | Not implementation spec | "Design overview" |
| mini-shi-propositions | SHI theory propositions (compact) | Not proven theory | "Theoretical framework overview" |
| mini-three-layer | Three-layer architecture (compact) | Not deployment guide | "Design architecture" |
| quality-system-4plus1 | 4+1 quality layer diagram | Not operational data | "Design architecture" |
| session-continuity-card | Session continuity concept | Not measured data | "Design concept" |
| status-card-detection | Detection rate card | Not benchmark | "Single environment — see metrics.md" |
| status-card-health | Health check card | Not live status | "Illustrative status" |
| status-card-quality | Quality metrics card | Not benchmark | "Illustrative metrics" |
| status-card-structure | Structure overview card | Not deployment | "Design overview" |
| three-layer-separation | Three-layer architecture (full) | Not deployment guide | "Design architecture" |
| overview-infographic-en/ja | Three-layer separation and five-layer quality management concept | Not measured benchmark | "Conceptual design [illustrative] — verify with PROVE-IT.md" |

Each image exists as `.svg` (English) and `.svg` (Japanese), or `.png` (EN/JA pair). Both must follow the same rules.

### Demo pages
- Classification: `[illustrative]`
- All numbers, names, statuses = sample values
- Every page must have a top banner stating this
- No bracket notation in UI-visible text
- Category labels for non-core systems: "(illustrative)" suffix

---

## 9. Contribution & Participation

| Item | Defined Expression | Prohibited |
|------|-------------------|------------|
| Contribution stance | "You do not need to write code to contribute" | "PRs welcome" alone |
| Canonical control | "Core theoretical claims are maintained by the author" | "Author-curated" alone |
| Collaboration | "Validation work is collaborative by design" | (omitting alongside canonical control) |
| CTA order | Try → Report observation → Challenge claim → Suggest improvement → Star/share | Star as first CTA |

---

## 10. Exception Management

| Classification | Rule | Process |
|----------------|------|---------|
| **Principle** | Default rule. Apply without review | Automated check |
| **Conditionally permitted** | Allowed in specific contexts (listed in this guide) | Self-check against guide |
| **Prohibited** | Never allowed | Automated check + review |
| **Review required** | New pattern not covered by this guide | Open Issue before using; add to guide if approved |

When a new expression is needed:
1. Check this guide first
2. If not covered → file as "review required"
3. If approved → add to this guide (guide is living document)
4. Never introduce new expressions without checking

---

## 11. Filename & Slug Rules

| File type | Pattern | Prohibited |
|-----------|---------|------------|
| EN Markdown | `kebab-case-en.md` or `kebab-case.md` | spaces, uppercase, `_en` |
| JA Markdown | `kebab-case-ja.md` | `_jp`, `_japanese` |
| SVG (conceptual) | `concept-name.svg` (EN in `/images/diagrams/`) / `concept-name-ja.svg` (JA in `/ja/images/diagrams/`) | `image1.svg`, `fig-01` |
| Demo HTML | `demo/page.html`, `ja/demo/page.html` | `demo_en.html` |
| Anchor IDs / slugs | lowercase-kebab | prohibited terms from Section 1 |

Filenames must not contain prohibited terms from any section (e.g., `free-tier-quickstart.md` is prohibited).

---

## 12. Code Block Applicability

| Content | This guide applies? | Notes |
|---------|-------------------|-------|
| Code body (functional code) | No | Code is code, not expression |
| Code comments (`# comment`) | **Yes** | Comments are public expression |
| Console output examples | **Yes** | Sample output is public |
| Prose before/after code blocks | **Yes** | Normal section rules |

---

## 13. SVG Internal Text & Accessibility Rules

### SVG embedded text
All `<text>`, `<title>`, `<desc>` elements inside SVG files must follow Section 2 (labels) and Section 3 (tone) rules, same as body text.

### alt text / ARIA labels

| Context | Required alt text pattern | Prohibited |
|---------|--------------------------|------------|
| Conceptual SVG | "Diagram showing [what it shows]" | "Proof of", "Benchmark" |
| Data visualization SVG | "Visualization of [metric] — single environment" | Absolute claims |
| Demo screenshot | "Sample dashboard — illustrative values" | Concrete numbers as facts |
| Decorative image | `alt=""` | Content description (causes confusion) |

### HTML meta / OGP tags
All `<title>`, `<meta name="description">`, `<meta property="og:title">`, `<meta property="og:description">` must pass Section 3 (tone) and Section 4 (SNS crop test).

---

## 14. Image Addition Meta-rule

When adding a new image or SVG:
1. **Must** add a row to Section 8's image table (PR and image commit together)
2. Required columns: File name | Shows | Does NOT show | Required caption if cropped
3. Images classified as `[illustrative]` follow Section 8 demo rules
4. **Committing an image without updating Section 8 is prohibited**

---

## 15. Guide Version Management

| Change type | Version bump | Process |
|-------------|-------------|---------|
| New prohibited expression | Minor (3.1) | PR with impact file list |
| New section | Major (4.0) | PR + pilot verification on 5 files |
| Typo/clarification | Patch (3.0.1) | Direct commit |

- Every change to this guide potentially affects all 190+ files
- Before changing: list impacted files in the PR description
- After changing: verify propagation to affected files
- Version and date are tracked in the file header

---

## 16. EN/JA Parity Review Unit

Parity is checked at these units:

| Unit | Check method |
|------|-------------|
| Page title (H1) | 1:1 impression match |
| Section headings (H2-H6) | 1:1 impression match |
| Evidence labels | Identical (EN label + JA translation) |
| Body paragraphs | Paragraph-level impression parity |
| CTAs | Same order, same strength |

**Rule**: When EN and JA differ in strength, always align to the **narrower/weaker** expression.

---

## 17. Compliance Checklist

Before any commit:

- [ ] Every number has a label per Section 2 general rule
- [ ] No brackets in titles, UI text, or first-impression zone (Section 5)
- [ ] No "paid tier" / "有料" / "free tier" (Section 6)
- [ ] No universal assertions; tone markers present (Section 3)
- [ ] Evidence labels + tone markers both present for claim sentences (Section 2 composition rule)
- [ ] EN/JA impression symmetry verified per Section 16 units
- [ ] Every image registered in Section 8 (Section 14 meta-rule)
- [ ] All SVG `<text>` elements pass Section 2+3 rules (Section 13)
- [ ] All alt/title/aria text passes Section 3 rules (Section 13)
- [ ] Demo pages have illustrative banners in first viewport
- [ ] No prohibited terms in filenames (Section 11)
- [ ] Code comments checked for Section 3 violations (Section 12)
- [ ] HTML meta/OGP tags pass SNS crop test (Section 13)
- [ ] New expressions checked against Section 10
- [ ] All internal links resolve (no broken links)
- [ ] LICENSE, CITATION.cff, badges, and GitHub About description are consistent with Section 1
- [ ] No TODO, placeholder, "coming soon", or draft markers in public files
- [ ] Badge text follows Section 1 and Section 6 (no "Free tier" in badge labels)

---

## 17.5. Link, Asset & Metadata Integrity

| Check | Rule |
|-------|------|
| Internal markdown links | All internal relative links must resolve to existing files |
| Image references | All image references must point to files listed in Section 8 |
| EN↔JA cross-links | EN file links to JA equivalent must exist, and vice versa |
| LICENSE | Must say MIT, consistent with CITATION.cff `license:` field |
| CITATION.cff | `title`, `authors`, `date-released`, `license` must match repo reality |
| GitHub repo description | Must follow Section 1 (methodology, not product) |
| Badge text | Shields.io URLs must not contain prohibited terms from Section 6 |
| Placeholder artifacts | No `TODO`, `FIXME`, `coming soon`, `placeholder`, `draft` in any public file |

---

## 18. External AI Review Procedure

When sending this repository for external AI review:

1. **Include this file (PUBLIC-EXPRESSION-GUIDE.md) in the zip**
2. **Instruction to reviewer**: "Read PUBLIC-EXPRESSION-GUIDE.md first. It is the single source of truth. Judge each of the 5 items (初見3秒理解, 信頼阻害要因ゼロ, 公開安全性, OSS受容性, 誤読耐性) as ◎ or ○ based solely on whether this guide's conditions are met."
3. **◎**: All conditions in this guide are satisfied
4. **○**: One or more conditions in this guide are violated. Reviewer must cite the Section number, condition, file path, and line
5. **Additional proposals**: Reviewer may suggest improvements beyond this guide's scope, but these do not affect ◎/○ judgment
6. **Prohibited**: Judging ○ for reasons not defined in this guide

### 5 Items and their governing sections

| Item | Primary sections | ◎ condition (all must pass) |
|------|-----------------|-------------|
| 初見3秒理解 | 1, 4 | (a) README H1 states project identity per Section 1 (b) Pain statement within first 15 lines (before any framework explanation) (c) "What this is" within first 20 lines (d) "Try it" section with time estimate within first 3 scrolls (e) Interactive demo link within first 3 scrolls |
| 信頼阻害要因ゼロ | 3, 4, 5, 6, 7 | (a) Zero bracket notation in titles/UI per Section 5 (b) Every page with brackets has a Note: explanation (c) Zero Section 6 prohibited terms (d) EN/JA parity per Section 16 (e) Zero broken internal links |
| 公開安全性 | 0, 5, 8, 13 | (a) Zero IP/email/token/password in all files per Section 0 surfaces (b) SECURITY.md explains safety design (c) All images registered in Section 8 (d) Demo banners present in first viewport |
| OSS受容性 | 1, 6, 9 | (a) LICENSE/CONTRIBUTING/CODE_OF_CONDUCT/SECURITY/CITATION exist (b) CONTRIBUTING states non-code contribution welcome (c) Issue templates provide observation/challenge paths (d) Zero Section 6 prohibited terms in entry documents |
| 誤読耐性 | 2, 3, 4, 7, 13 | (a) Every number has evidence label per Section 2 (b) Every assertion has tone marker per Section 3 (c) Zero Section 3 prohibited patterns (d) EN/JA impression parity per Section 16 (e) SVG text passes Section 2+3 |

### Review output template

For each item, output:
```
## [Item name]: ◎ or ○
Conditions checked: (a)✅ (b)✅ (c)✅ (d)✗ (e)✅
If ○: Section X, condition (d) violated at [file:line]: "quoted text"
Proposed fix: [修正案]
```

---

## 19. Pilot Application

Before applying to all 190 files:
1. Apply to 5 representative files (README, 1 achievement EN, 1 achievement JA, 1 demo, 1 framework doc)
2. Have both AIs verify: "Does the pilot match the definitions?"
3. Fix definition ambiguities found during pilot
4. Then apply to remaining files in order: Entry points → Structure files → Demos → Deep content


---

→ [Back to README](README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
