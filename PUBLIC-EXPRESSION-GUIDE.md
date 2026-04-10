# Public Expression Guide

Version: 5.0 | Last updated: 2026-04-10

This document is the single source of truth for every expression used in the SHI-Claude-Control-OS public repository.
All AIs (Claude Code, external reviewers) creating or reviewing repository content must follow this guide.

---

## 1. Applicability Surface

This guide applies to **all externally visible expressions**, including:

| Surface | Examples | Sections that apply |
|---------|----------|-------------------|
| Markdown body text (EN/JA) | README, achievements, framework docs | 2,4,5,6,10,11 |
| Headings / titles (H1-H6) | Page titles, section headings | 2,5,9 (no brackets) |
| Demo HTML (UI-visible text) | demo/*.html, ja/demo/*.html | 5,6,12 |
| SVG embedded text | `<text>`, `<title>`, `<desc>`, legends | 4,5,12 |
| alt text / ARIA labels | `alt=""`, `aria-label=""` | 5,6 |
| HTML meta / OGP tags | `<title>`, `<meta og:title>`, `<meta description>` | 2,5,6 (SNS crop test) |
| File names / URL slugs | `01-failure-modes.md`, anchor IDs | Filename rules (below) |
| Code block comments | `# comment text` | 5 (comments only, not code) |
| Code block output examples | Fenced block sample output | 5 |
| CITATION.cff fields | `abstract:`, `keywords:` | 2,5 |
| Issue/PR templates | `.github/ISSUE_TEMPLATE/*.md` | 5,15 |
| GitHub repo description | About field | 2 |
| Badges | shields.io URLs | Filename rules |

**Not in scope**: Code logic itself (functional code, not comments).

**Safety scan clarification**: "Token" in security context means authentication tokens, API keys, secrets — NOT general English words like "Token Monitor" (a dashboard page title) or "token consumption" (a methodology term).

---

---

## 2. Project Identity

| Item | Defined Expression | Prohibited | SNS-safe 1-line |
|------|-------------------|------------|-----------------|
| Repository name | SHI-Claude-Control-OS | SHI-Control-OS, Control OS (standalone) | SHI-Claude-Control-OS |
| What this is | A structural governance methodology | Product, tool, software, platform, service | "AI governance methodology — copy-paste templates + verification guide" |
| Scope | For reducing repeated AI failures | For eliminating / guaranteeing / solving | "Reduces repeated AI failures in the author's observed environment" |
| Author stance | One attempt to break the pattern | Breaks the pattern, solves the problem | "One documented approach — verify in your environment" |

---

---

## 3. Entry-Surface Standard

The repository must not rely on “the reader already knows why this matters.”

Every primary entry surface must establish, in the first visible screen:

1. **pain recognition** — what repeated failure or friction this repository addresses
2. **identity clarity** — what this repository is, in plain language
3. **safe first action** — what the reader can do now in low risk / low time
4. **trust framing** — why the claims are scoped and how to verify them

### Entry surfaces
The following are treated as primary entry surfaces:
- README opening screen
- repository About text
- social preview text (OGP / description)
- top of deep-linked high-traffic docs
- demo landing page first viewport

### Minimum first-screen rule
A first-time reader should be able to answer all of the following within one screen or three scrolls at most:

- What problem is this about?
- What is this?
- Why should I trust the framing?
- What can I try right now?

If one of these is missing, the surface cannot exceed ○.

### Prohibited entry-surface failures
- opening with framework language before pain recognition
- opening with architecture before relevance
- opening with claims before scope
- opening with CTA before trust framing
- opening with internal terminology before plain-language identification


      |## 4.6 Forwardability Without Hype|

---

## 4. Evidence Labels (Vocabulary Rules)

Every number, claim, or result must carry exactly one **evidence class** and zero or more **qualifiers**. No unlabeled claims.

### General rule (applies to ALL numbers, not just listed ones)

| If the number is... | Assign evidence class | Then add qualifiers as needed |
|---------------------|----------------------|------------------------------|
| Measured in author's environment | `[observed]` | `single environment`, `single operator`, `N undisclosed` |
| An architecture goal, not measured | `[design target]` | — |
| An example or explanatory value | `[illustrative]` | — |
| A hypothetical extrapolation | `[illustrative scenario]` | `not verified` |
| None of the above | **Do not use.** Route to Section 17 (Review required) | — |

### Canonical label format

```
[evidence-class: qualifier1, qualifier2]
```

Example: `[observed: single environment, N undisclosed]`

### Composition rule (how labels and tone markers work together)

Every claim-bearing sentence needs **both**:
1. An **evidence label** (from this section) — attached to the number or claim
2. A **tone marker** (from Section 5) — embedded in the sentence structure

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

---

## 5. Meaning Rules (What may be claimed)

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

---

## 6. Reception Rules (How readers will interpret)

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

---

## 7. Recommendation & Resonance Rule

This guide does **not** define ◎ as mere compliance.

Compliance makes a page **eligible for public release**.
Recommendation-level quality makes a page **worthy of being forwarded, cited, or shared**.

A page, file, or repository is ◎-eligible only when it satisfies both:

1. **Baseline trustworthiness** — safe, clear, scoped, non-misleading, OSS-acceptable
2. **Reader-behavior impact** — makes a first-time reader want to do at least one of:
   - try it now
   - send it to a colleague
   - report an observation
   - challenge a claim constructively
   - bookmark it as a credible reference

### Important distinction
- **○** = compliant, safe, understandable, reviewable
- **◎** = ○ + behavior-changing, recommendation-worthy, screenshot-safe

### Prohibited shortcuts to ◎
The following do **not** count as recommendation value:
- hype language
- urgency theater
- vague social proof
- grandiosity
- “trust me” rhetoric
- bait-style numbers without scope
- sensational phrasing designed to force sharing

A file is not ◎ because it is loud.
A file is ◎ when it is careful **and** people still want to share it.

### Screenshot-safe principle
A ◎-eligible surface must remain reputation-positive even when:
- only the title is seen
- only the first 1–2 sentences are quoted
- only a cropped image is shared
- only a deep page is opened directly

If a cropped or isolated view becomes “technically correct but socially risky,” the file cannot be ◎.


      |## 17. Rating Model & Baseline Compliance Gate|

---

## 8. Forwardability Without Hype

A file or repository becomes ◎ not when it is merely polished, but when it creates a natural forwarding impulse **without requiring persuasion tricks**.

### Definition
“Forwardable” means:
A careful reader feels comfortable sending the file to a colleague, team, or public audience because doing so does not create reputational risk.

### Signals of true forwardability
- the reader can explain it in one sentence without distortion
- the file makes the reader look careful, not gullible
- the opening reduces embarrassment risk if shared in public
- the first action feels testable, not belief-based
- the repository invites verification, not obedience

### False-forwardability patterns (prohibited)
- “must-read” tone
- “everyone should see this” framing
- emotionally manipulative urgency
- authority theater
- oversized headlines unsupported by scoped evidence
- share-bait phrasing

### Rule
A repository that is technically compliant but socially awkward to forward is limited to ○.

    3. Section 10 を差し替え強化

現行の「paid tier / free tier 禁止」は良いのですが、
*“売り込み感の禁止” をもっと直接書く*べきです。|
review_instruction_v3.txt| でも OSS受容性と信頼阻害でここを強く見ています。

      差し替え案: |## 6. Scope, Access Boundary & Non-Sales Language|

---

## 9. Redaction Expressions

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

---

## 10. Scope, Access Boundary & Non-Sales Language

This repository may describe public/private boundaries, release phases, or evaluation surfaces.
It must never sound like a pricing funnel.

| Item | Defined expression | Prohibited |
|------|--------------------|------------|
| public boundary | public repository / public release surface | free tier / free version |
| non-public boundary | non-public implementation / private deployment / future open release phase | paid tier / paid version / premium |
| phase explanation | "Phase 1 / Phase 2 = future open release phases, not pricing tiers" | ambiguous “tier” language |
| evaluation surface | "This repository is the primary evaluation surface" | "free tier is enough" |
| access note | "Some implementation details are intentionally not public" | “unlock”, “upgrade”, “premium access” |
| contribution invitation | "validate", "report observation", "suggest improvement" | sales CTA wording |

### Non-sales rule
The repository must never create the impression that:
- the public repo is a teaser for a paid offering
- claims are withheld behind access language
- readers are being funneled rather than invited to verify

If a reader could plausibly say “this feels like a sales page,” the file cannot exceed ○.

      |## 8.5 Demo First-Viewport Rule|

現行は「デモに illustrative バナーを置く」まではありますが、
◎を狙うなら *“初見の誤読防止 + 試したくなる導線”* の両立が必要です。

---

## 11. EN/JA Interpretation Symmetry

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

---

## 12. Image & Demo Definitions

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

---

## 13. Demo First-Viewport Rule

Every demo landing surface must establish all of the following in the first viewport:

1. this is a demo / illustrative surface
2. what behavior or concept is being demonstrated
3. what is sample vs what is verified elsewhere
4. where to verify the real claim
5. what the reader can explore safely

### Minimum demo opening structure
Order:

1. Demo label
2. Plain-language purpose
3. Scope / illustrative notice
4. Verification pointer
5. Explore action

### Example pattern
- "Illustrative demo"
- "Shows how the quality layers are organized"
- "All values on this page are samples"
- "For verified claims, see PROVE-IT.md"
- "Try navigating the layers"

### Rule
A demo that is safe but inert may qualify for ○.
A demo becomes ◎ only when the reader understands the boundary **and** still wants to interact with it.

    5. 新設

      |## 8.6 Image Share-Safety Rule|

---

## 14. Image Share-Safety Rule

Every image intended for public view must be safe under detached circulation.

Detached circulation means:
- pasted into chat without caption
- reposted on SNS with only one line of context
- cropped to headline + one number
- embedded into slides without surrounding explanation

### For ○
- image does not overclaim
- image has required caption metadata in Section 12 table
- image does not expose hidden implementation or sensitive detail

### For ◎
- image remains trust-positive even when detached
- image increases curiosity without causing interpretive risk
- image is visually legible, semantically scoped, and citation-aligned

If an image is accurate only when read with surrounding prose, it cannot be ◎.

    6. 新設

      |## 9.5 Participation Without Code Rule|

|review_instruction_v3.txt| の OSS受容性で重要なのは、
「標準ファイルがある」だけでなく、*“コードを書けなくても参加したい” と感
じるか*です。

これを guide 本体に入れます。

---

## 15. Contribution & Participation

| Item | Defined Expression | Prohibited |
|------|-------------------|------------|
| Contribution stance | "You do not need to write code to contribute" | "PRs welcome" alone |
| Canonical control | "Core theoretical claims are maintained by the author" | "Author-curated" alone |
| Collaboration | "Validation work is collaborative by design" | (omitting alongside canonical control) |
| CTA order | Try → Report observation → Challenge claim → Suggest improvement → Star/share | Star as first CTA |

---

---

## 16. Participation Without Code Rule

This repository must not imply that contribution is limited to code.

### For ○
The repository must explicitly permit non-code contribution paths such as:
- reporting observations
- testing claims in another environment
- improving wording or translations
- identifying ambiguity or overstatement
- challenging a claim with evidence

### For ◎
The repository must make at least one non-code path feel legitimate and desirable.

A reader should be able to think:
- "I can help validate this"
- "I can report what happened in my environment"
- "I can contribute without pretending expertise I do not have"

If non-code participation exists only as a footnote and does not feel real, the repo cannot be ◎.

    7. 新設

      |## 16.5 Deep-Page Cold-Open Rule|

ここはかなり重要です。
|review_instruction_v3.txt| では「どのページを開いても『ちゃんとしてい
る』以外の感想が出ない」が◎条件です。

化されていません。そこを追加します。

---

## 17. Exception Management

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

---

## 18. Filename & Slug Rules

| File type | Pattern | Prohibited |
|-----------|---------|------------|
| EN Markdown | `kebab-case-en.md` or `kebab-case.md` | spaces, uppercase, `_en` |
| JA Markdown | `kebab-case-ja.md` | `_jp`, `_japanese` |
| SVG (conceptual) | `concept-name.svg` (EN in `/images/diagrams/`) / `concept-name-ja.svg` (JA in `/ja/images/diagrams/`) | `image1.svg`, `fig-01` |
| Demo HTML | `demo/page.html`, `ja/demo/page.html` | `demo_en.html` |
| Anchor IDs / slugs | lowercase-kebab | prohibited terms from Section 2 |

Filenames must not contain prohibited terms from any section (e.g., `free-tier-quickstart.md` is prohibited).

---

---

## 19. Code Block Applicability

| Content | This guide applies? | Notes |
|---------|-------------------|-------|
| Code body (functional code) | No | Code is code, not expression |
| Code comments (`# comment`) | **Yes** | Comments are public expression |
| Console output examples | **Yes** | Sample output is public |
| Prose before/after code blocks | **Yes** | Normal section rules |

---

---

## 20. SVG Internal Text & Accessibility Rules

### SVG embedded text
All `<text>`, `<title>`, `<desc>` elements inside SVG files must follow Section 4 (labels) and Section 5 (tone) rules, same as body text.

### alt text / ARIA labels

| Context | Required alt text pattern | Prohibited |
|---------|--------------------------|------------|
| Conceptual SVG | "Diagram showing [what it shows]" | "Proof of", "Benchmark" |
| Data visualization SVG | "Visualization of [metric] — single environment" | Absolute claims |
| Demo screenshot | "Sample dashboard — illustrative values" | Concrete numbers as facts |
| Decorative image | `alt=""` | Content description (causes confusion) |

### HTML meta / OGP tags
All `<title>`, `<meta name="description">`, `<meta property="og:title">`, `<meta property="og:description">` must pass Section 5 (tone) and Section 6 (SNS crop test).

---

---

## 21. Image Addition Meta-rule

When adding a new image or SVG:
1. **Must** add a row to Section 12's image table (PR and image commit together)
2. Required columns: File name | Shows | Does NOT show | Required caption if cropped
3. Images classified as `[illustrative]` follow Section 12 demo rules
4. **Committing an image without updating Section 12 is prohibited**

---

---

## 22. Guide Version Management

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

---

## 23. EN/JA Parity Review Unit

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

---

## 24. Deep-Page Cold-Open Rule

Any page that may be opened directly from search, file browser, citation, or social link must be understandable without README context.

### Cold-open minimum
Within the opening block of a deep page, the reader must be able to infer:

1. what this page is about
2. whether it is conceptual / measured / illustrative
3. what larger repository context it belongs to
4. how strong the page's claims are

### Deep-page opening failures
- opening with internal shorthand
- opening with numbers before labels
- opening with unresolved redaction artifacts
- opening with conclusions before scope
- opening with a tone stronger than the repository entry surface

### Rule
A repository whose README is ◎ but whose deep pages still require prior context is capped at ○.

      |## 18.6 Repository-Level Override Rule|

「READMEだけ強くて深部が雑なのに◎になる」事故を防げます。

---

## 25. Rating Model & Baseline Compliance Gate

This guide uses **three ratings**:

- **△** = baseline not met
- **○** = baseline met
- **◎** = ○ + resonance gate met

### Rating definitions

| Rating | Meaning | Release implication |
|--------|---------|---------------------|
| △ | One or more mandatory baseline conditions are violated | Not ready for final public evaluation |
| ○ | All baseline conditions are satisfied. Safe, clear, scoped, professionally acceptable | Public-safe and review-passable |
| ◎ | All baseline conditions satisfied **and** recommendation-worthy: changes reader behavior without hype | Public-safe and high-impact |

### Non-negotiable rule
**◎ must never be awarded for compliance alone.** Passing the checklist means **○**, not ◎.

### Tie-break rule
When unsure between ○ and ◎, assign **○**. Soft ◎ is considered a review failure.

### Baseline compliance checklist (○ gate)

Before any commit:

- [ ] Every number has a label per Section 4 general rule
- [ ] No brackets in titles, UI text, or first-impression zone (Section 9)
- [ ] No "paid tier" / "有料" / "free tier" (Section 10)
- [ ] No universal assertions; tone markers present (Section 5)
- [ ] Evidence labels + tone markers both present for claim sentences (Section 4 composition rule)
- [ ] EN/JA impression symmetry verified per Section 23 units
- [ ] Every image registered in Section 12 (Section 21 meta-rule)
- [ ] All SVG `<text>` elements pass Section 2+3 rules (Section 20)
- [ ] All alt/title/aria text passes Section 5 rules (Section 20)
- [ ] Demo pages have illustrative banners in first viewport
- [ ] No prohibited terms in filenames (Section 18)
- [ ] Code comments checked for Section 5 violations (Section 19)
- [ ] HTML meta/OGP tags pass SNS crop test (Section 20)
- [ ] New expressions checked against Section 17
- [ ] All internal links resolve (no broken links)
- [ ] LICENSE, CITATION.cff, badges, and GitHub About description are consistent with Section 2
- [ ] No TODO, placeholder, "coming soon", or draft markers in public files
- [ ] Badge text follows Section 2 and Section 10 (no "Free tier" in badge labels)

---

---

## 26. Link, Asset & Metadata Integrity

| Check | Rule |
|-------|------|
| Internal markdown links | All internal relative links must resolve to existing files |
| Image references | All image references must point to files listed in Section 12 |
| EN↔JA cross-links | EN file links to JA equivalent must exist, and vice versa |
| LICENSE | Must say MIT, consistent with CITATION.cff `license:` field |
| CITATION.cff | `title`, `authors`, `date-released`, `license` must match repo reality |
| GitHub repo description | Must follow Section 2 (methodology, not product) |
| Badge text | Shields.io URLs must not contain prohibited terms from Section 10 |
| Placeholder artifacts | No `TODO`, `FIXME`, `coming soon`, `placeholder`, `draft` in any public file |

---

---

## 27. Resonance Gate (◎ gate)

A file/repo may be rated ◎ only if it already qualifies for ○ **and** passes the following item-specific resonance conditions.

### 5 items and their two-level criteria

| Item | ○ baseline (must all pass) | ◎ resonance (must all pass) |
|------|-----------------------------|------------------------------|
| 初見3秒理解 | Identity is clear, pain is visible, what-this-is is stated, try-it path exists | A first-time reader feels immediate self-relevance, the first action feels low-risk and worth trying, and the opening is strong enough that the reader may want to forward it to a peer |
| 信頼阻害要因ゼロ | No fatal blockers: no broken links, no unsafe disclosure, no unexplained strong claims, no sales smell, no visible residue | Deep pages can be opened cold without hesitation; the reader never pauses at “what is this?” / “is this a sales page?” / “is this exaggerated?” |
| 公開安全性 | No sensitive information is exposed | Safety is visibly designed: redaction discipline, demo disclaimers, security framing, and public/private boundary handling are legible to the reader |
| OSS受容性 | Standard OSS documents exist and contribution paths are present | The repo makes readers feel “I can participate even without code” or “I want to report an observation / validate this claim” |
| 誤読耐性 | Labels, scope, and tone controls are present | Any isolated title, opening sentence, quoted number, or cropped image still preserves or improves the author’s credibility |

### Additional rules for ◎

A ◎ rating requires all of the following repository-level conditions:

1. **No trust debt hidden in deep pages**  
   ◎ is invalid if the entry pages are strong but deep pages still contain residue, ambiguity, or overshooting language.

2. **No screenshot fragility**  
   ◎ is invalid if a strong number, image, or claim becomes socially risky when isolated.

3. **No recommendation friction**  
   ◎ is invalid if a reader understands the repo but would hesitate to send it to a colleague because it still feels rough, over-claimed, or internally named.

4. **No hype substitution**  
   ◎ is invalid if the “shareability” is created by sensational wording rather than precise, scoped, trustworthy expression.

### Practical interpretation
- **○** = “There is no serious problem.”
- **◎** = “There is no serious problem, and I would feel good sending this to someone.”

The gap is not technical correctness.
The gap is whether the work changes reader behavior **without lowering trust**.


---

## 28. External AI Review Procedure

When sending this repository for external AI review:

1. **Include this file (PUBLIC-EXPRESSION-GUIDE.md) in the zip**
2. **Instruction to reviewer**:  
   "Read PUBLIC-EXPRESSION-GUIDE.md first. It is the single source of truth. Judge each of the 5 items (初見3秒理解, 信頼阻害要因ゼロ, 公開安全性, OSS受容性, 誤読耐性) as △, ○, or ◎ based solely on this guide."

### 18.1 Rating rules for reviewers

- **△**: One or more ○ baseline conditions are violated
- **○**: All ○ baseline conditions are satisfied, but ◎ resonance is not fully satisfied
- **◎**: All ○ baseline conditions and all ◎ resonance conditions are satisfied

### 18.2 Critical reviewer rules

- Do **not** award ◎ for compliance alone
- Do **not** downgrade ○ to △ for reasons outside this guide
- Do **not** upgrade ○ to ◎ because the repo “feels good overall” without satisfying the resonance conditions
- When unsure between ○ and ◎, assign **○**
- A soft or charitable ◎ is considered invalid

### 18.3 Required output structure

For each item, reviewers must output:

```text
## [Item name]: △ / ○ / ◎
○ conditions checked: (a)✅ (b)✅ (c)✅ (d)✅ ...
◎ conditions checked: (r1)✅ (r2)✗ (r3)✅ ...
If △: cite the violated ○ condition, file path, and line
If ○: cite the missing ◎ condition(s), file path(s), and line(s) where the gap is visible
If ◎: cite the concrete file/path evidence that makes it recommendation-worthy, not merely compliant
Proposed fix: [specific text/path-level fix]
Priority: P0 / P1 / P2

      18.4 Meaning of each outcome

  *

    *△* = not yet publicly reliable enough

  *

    *○* = publicly reliable and standards-compliant

  *

    *◎* = publicly reliable, standards-compliant, and recommendation-worthy

      18.5 Additional proposals

Reviewers may add suggestions beyond the current guide, but those must
appear in a separate section called *Additional proposals* and must not
affect the △/○/◎ rating unless this guide explicitly defines them.

      18.6 Five items and their governing sections

| Item | Primary sections | ○ baseline | ◎ resonance |
|------|-----------------|------------|-------------|
| 初見3秒理解 | 2, 3, 6, 7, 27 | Clear identity + pain + try path | Immediate relevance + try desire + forwardability |
| 信頼阻害要因ゼロ | 5, 6, 9, 10, 11, 27 | No fatal blockers | No hesitation anywhere, including deep pages |
| 公開安全性 | 1, 9, 12, 20, 27 | No leakage | Safety design is visible as design |
| OSS受容性 | 2, 10, 15, 27 | Standard OSS acceptability | Participation desire is induced |
| 誤読耐性 | 4, 5, 6, 11, 20, 27 | Proper labels and scope | Cropped/quoted fragments remain reputation-positive |

---

## 29. Repository-Level Override Rule

A repository-level ◎ requires consistency, not isolated excellence.

Even if some entry files are ◎-eligible, the overall repository must not be rated ◎ when any of the following remain:

- repeated trust debt in deep pages
- EN/JA asymmetry that changes claim strength
- cropped-image fragility
- demo pages that are safe but misleading in isolation
- contribution language that exists formally but not credibly
- unresolved residue that makes forwarding risky

### Override rule
If any one of the five review items is only ○ at repository level, the repository overall cannot be ◎.

### Practical meaning
A few excellent pages do not make a ◎ repository.
A ◎ repository is consistently recommendable.

    9. |review_instruction_v3.txt| 側も少しだけ修正した方が良い箇所

いまの |review_instruction_v3.txt| はかなり良いのですが、
|PUBLIC-EXPRESSION-GUIDE.md| を正本に引き上げるなら、レビュー指示書は*判
定定義の競合元*ではなく*運用手順書*に寄せた方が安定します。
つまり、定義は guide、本ファイルは reviewer 向け実行手順、という役割分離
です。

      修正した方が良い文言

        現行

    ◎/○の判定は、セクション3の定義に基づいて行う。定義が判定の軸
    定義 = 判定の床（これを満たせば◎）…

ここは、今後の新設方針と少しずれます。
|これを満たせば◎| ではなく、*これを満たせば○、さらに resonance gate を満
たして◎* に変えるべきです。

      差し替え案

---

## 30. Anti-gaming Rule

This guide is intentionally harder to “game.”

A repository must not be rated ◎ by relying on:
- inflated adjectives
- emotionally manipulative headings
- unexplained bold numbers
- performative professionalism
- aesthetic polish without interpretive safety
- recommendation pressure (“share this”, “must read”, etc.)

A repository earns ◎ only when recommendation value emerges from:
- clarity
- trust
- scoped evidence
- safe cropping behavior
- legitimate reader usefulness

  この修正で何が変わるか

この差し替え後は、現行のように
*「規約を守ったから◎」ではなく、「規約を守ったので○、さらに人に勧めたく
なる設計までできて初めて◎」* になります。
その結果、|PUBLIC-EXPRESSION-GUIDE.md| 側にも |

---

## 31. Pilot Application

Before applying to all 190 files:
1. Apply to 5 representative files (README, 1 achievement EN, 1 achievement JA, 1 demo, 1 framework doc)
2. Have both AIs verify: "Does the pilot match the definitions?"
3. Fix definition ambiguities found during pilot
4. Then apply to remaining files in order: Entry points → Structure files → Demos → Deep content


---

→ [Back to README](README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*

---