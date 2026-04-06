# Public Expression Guide — 公開表現定義集

Version: 3.0 | Last updated: 2026-04-06

This document is the single source of truth for every expression used in this public repository.

---

## 0. Applicability Surface

This guide applies to **all externally visible expressions**, including:

| Surface | Examples | Sections that apply |
|---------|----------|-------------------|
| Markdown body text (EN/JA) | README, achievements, framework docs | 1,2,3,4,5,6,7 |
| Headings / titles (H1-H6) | Page titles, section headings | 1,3,5 (no brackets) |
| Demo HTML (UI-visible text) | demo/en/*.html, demo/jp/*.html | 3,4,8 |
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

Every number, claim, or result must carry exactly one label. **No unlabeled claims.**

| Label | Meaning | Mechanical marker (must contain) | SNS-safe short |
|-------|---------|----------------------------------|----------------|
| `[observed: single environment, single operator]` | Measured in author's environment | "observed", "single environment" | "Observed in one environment" |
| `[design target]` | Architecture goal, not measured | "design target" or "design value" | "Design target, not benchmark" |
| `[illustrative]` | Example, not data | "illustrative" or "example" | "Illustrative example" |
| `[illustrative scenario, not verified]` | Hypothetical extrapolation | "not verified" | "Unverified scenario" |

### Specific numbers

| Number | Required label | Prohibited usage |
|--------|---------------|-----------------|
| 132 (failure modes) | `[observed: single environment]` | "132 proven failure modes" |
| ~100% (detection rate) | `[single environment, N undisclosed; not a product claim]` | "100%" without tilde or label |
| 65% (reduction) | `[design value]` | "65% improvement" without label |
| 20x (token reduction) | `[design target]` | "20x faster" or "20x efficiency" without label |
| 12+ (CC generations) | Context sentence required | Standalone "12 generations of AI" |

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
| **Conditionally permitted** | In `> Note:` blocks explaining redaction system | "`[external monitoring hook]` is a redacted label..." |
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

| Image file | Shows | Does NOT show | Required caption if cropped |
|-----------|-------|--------------|----------------------------|
| before-after-comparison-en.svg | Conceptual before/after | Not measured data | "Conceptual — verify with PROVE-IT.md" |
| status-card-detection-en.svg | Detection rate visualization | Not benchmark | "Single environment — see metrics.md" |
| three-layer-separation-en.svg | Architecture diagram | Not deployment guide | "Design architecture" |
| dashboard-overview-en.svg | Dashboard layout concept | Not live dashboard | "Illustrative layout — all values are samples" |

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

## 11. Compliance Checklist

Before any commit:

- [ ] Every number has a label from Section 2
- [ ] No brackets in titles or UI text (Section 5)
- [ ] No "paid tier" / "有料" (Section 6)
- [ ] No universal assertions (Section 3)
- [ ] Assertion markers present per Section 3 table
- [ ] EN/JA impression symmetry checked (Section 7)
- [ ] Every image listed in Section 8
- [ ] Demo pages have illustrative banners
- [ ] New expressions checked against Section 10

---

## 12. Pilot Application

Before applying to all 190 files:
1. Apply to 5 representative files (README, 1 achievement EN, 1 achievement JA, 1 demo, 1 framework doc)
2. Have both AIs verify: "Does the pilot match the definitions?"
3. Fix definition ambiguities found during pilot
4. Then apply to remaining files in order: Entry points → Structure files → Demos → Deep content
