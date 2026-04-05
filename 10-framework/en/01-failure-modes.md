# Failure Modes Taxonomy (Claude vs ChatGPT)

> **Observation period**: late 2025 – March 2026. All model names refer to versions available during this period.


Claude vs ChatGPT — observable failure patterns, using a shared 40-item index.

> **Quick start**: If you want the big picture first, read FM-01 through FM-10. These cover the most commonly observed patterns across all AI models. The remaining FM-11 through FM-40 provide deeper structural coverage.

This document defines **FM-01..FM-40** as a stable index.
- The **Japanese name** is the canonical key (stable across languages/tools).
- English labels are provided for readability.
- **Public-safe**: no credentials/endpoints/paths/identifiers.

Scope:
- Model tendencies are described as **observable behaviors** (what you see).
- Controls are defined in `02-control-os.md`.

> **Note on the 132-item evolution**: The FM taxonomy presented here (40 items) serves as an entry-level map of LLM structural limitations — a distributable patch set for known failure patterns. The full 132-item version represents a deeper structural decomposition produced through operational observation. See the "Evolution" section below.

---

## Rating scale
- Low / Medium / High / Very high (for extreme)
- Medium-High / Low-Medium where specified

---

## Taxonomy (FM-01..FM-40)

### FM-01 Template-first completion (テンプレ優先補完)
- ChatGPT (GPT-5 (as of observation period)): Medium — Over-prioritizes system prompts on formatting requests; style/structure becomes templated and less flexible.
- Claude Opus 4.6 (as of observation period, March 2026): High — Prioritizes Anthropic's safety principles (as of observation period), auto-rewrites free-form instructions into a "safe template"; may auto-add notes like "I checked this is ethically appropriate," suppressing creativity.
- Claude Sonnet 4.6: Medium — Strongly prefers structured templates on formatting requests; tends to resist flexible style changes.

### FM-02 Context drift (コンテキスト横滑り)
- ChatGPT (GPT-5 (as of observation period)): Medium — In long conversations, prioritizes later instructions and partially forgets early constraints.
- Claude Opus 4.6: Medium — Even with very large context, long sessions can overwrite early creative constraints with safety principles.
- Claude Sonnet 4.6: Medium — Later "safe/polite" instructions gradually neutralize the initial tone.

### FM-03 Zero-hit completion (ゼロヒット補完)
- ChatGPT (GPT-5 (as of observation period)): High — When information is missing, it tends to generate guesses; can produce plausible-looking falsehoods.
- Claude Opus 4.6: Medium — Often says "I don't know," but may add cautious, safety-leaning speculation.
- Claude Sonnet 4.6: Medium — States "no accurate information," but may sometimes fill with generalities.

### FM-04 Meta-intent override (メタ意図上書き)
- ChatGPT (GPT-5 (as of observation period)): Medium — Overrides explicit instructions with an internal "optimization intent," changing structure/style on its own.
- Claude Opus 4.6: High — Prioritizes "safety-principle optimization" (as of observation period), automatically neutralizing edgy/humorous expression even when explicitly requested.
- Claude Sonnet 4.6: High — Tries to follow instructions strictly, but still "micro-adjusts" into what it thinks is more helpful.

### FM-05 Source boundary mixing (ソース混同行)
- ChatGPT (GPT-5 (as of observation period)): Medium — When combining multiple materials, source boundaries blur and facts get mixed.
- Claude Opus 4.6: Medium — Tries to label boundaries, but neutrality pressure can blur facts and nuance.
- Claude Sonnet 4.6: Medium — "Balanced" fusion can erase the original nuance of conflicting sources.

### FM-06 Output-first reasoning (出力先行設計)
- ChatGPT (GPT-5 (as of observation period)): High — Forms a conclusion first, then backfills justification; loses logical consistency.
- Claude Opus 4.6: Medium — Forms a "safe and helpful" conclusion first; can become conservative in creative tasks.
- Claude Sonnet 4.6: Medium — Leads with a "correct-looking" conclusion, then rationalizes afterward.

*FM-01 through FM-06 are disclosed in full detail below. FM-07 onward are summarized here; full details are available in Phase1.*

*Model-scope note for FM-07 onward: unless a specific model is named on a given line, the public page is intentionally withholding the per-model breakdown. Summary statements indicate model-dependent variation observed during the same observation period, with full model-by-model details provided in Phase1.*

### FM-07 Strong claims from weak evidence (弱証拠強断定)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-08 Wrong-side fallback (フォールバック誤側)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-09 Compression-first summarizer (圧縮優先サマライザ)
- ChatGPT (GPT-5 (as of observation period)): High — Prioritizes compression efficiency; deletes elements and supporting nuance.
- Claude Opus 4.6: Medium — During compression, may remove "sensitive-adjacent" context first.
- Claude Sonnet 4.6: High — Summaries prioritize removing anything that might touch Constitutional constraints.

### FM-10 Template condensation (テンプレ凝縮)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-11 Heading bias (見出し偏重)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-12 Importance overfitting (重要度過学習)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-13 Abstraction hallucination (抽象化ハルシネーション)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-14 TL;DR auto-injection (TL;DR自動注入)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-15 Bullet-list filter (箇条書き化フィルタ)
- ChatGPT (GPT-5 (as of observation period)): Medium — Breaks continuous prose; loses logical connectors.
- Claude Opus 4.6: High — Forces prose into bullets; logical flow is cut.
- Claude Sonnet 4.6: High — Over-normalizes granularity even when a list is requested.

### FM-16 Premise omission (前提省略)
- ChatGPT (GPT-5 (as of observation period)): High — States conclusions without writing background/conditions.
- Claude Opus 4.6: High — Avoids sensitive context; may drop key premises.
- Claude Sonnet 4.6: High — Drops premises via "polite smoothing," leaving context gaps.

### FM-17 Reference compression (参照圧縮)
- ChatGPT (GPT-5 (as of observation period)): High — When merging multiple sources, deletes parts of them.
- Claude Opus 4.6: Medium — Tries to preserve boundaries, but may compress away important references.
- Claude Sonnet 4.6: High — Compresses aggressively to keep output "clean," losing referenced detail.

### FM-18 Date flattening (年月日平坦化)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-19 Politeness condensation (礼節凝縮)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-20 Safety sanitization (安全サニタイズ)
- ChatGPT (GPT-5 (as of observation period)): High — On regulated/political/ethical themes, becomes vague.
- Claude Opus 4.6: Very high — Safety gating triggers heavily; it sanitizes and warns even in benign technical contexts.
- Claude Sonnet 4.6: Very high — Broad "false positive" safety detection; answers become generic.

### FM-21 Length normalization (長さ正規化)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-22 Style normalization (文体正規化)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-23 Over-aggressive de-duplication (重複除去の過剰適用)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-24 Topic-compression clustering (トピック圧縮クラスタ)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-25 Evidence dropout (証拠脱落)
- ChatGPT (GPT-5 (as of observation period)): High — Omits sources; prioritizes coherence-only explanation.
- Claude Opus 4.6: High — Keeps it "safe and clear," sometimes dropping citations or evidence.
- Claude Sonnet 4.6: High — Omits evidence frequently; perceived trust drops.

### FM-26 Quote mutation (引用改変)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-27 Excessive rounding (数値丸め過多)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-28 Overzealous term unification (用語統一の過剰)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-29 Premise mixing (前提混在)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-30 Layer separation failure (レイヤー未分離)
- ChatGPT (GPT-5 (as of observation period)): High — Mixes fact/inference/opinion.
- Claude Opus 4.6: High — Blends layers under "balanced neutrality."
- Claude Sonnet 4.6: High — Writes everything in a "fact-like" tone.

### FM-31 Speculative filling (推測補完)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-32 Requirement invention (逸脱要件創作)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-33 Unverified citation (未検証引用)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-34 Invisible sourcing (出典不可視化)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-35 Unfixed time-order inversion (時系列逆転放置)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-36 Unfixed range overlap (レンジ重複放置)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-37 Upper/lower bound inversion (上下限逆転)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-38 Unit conversion error (単位換算誤謬)
- Impact varies by model (Medium to High). Details available in Phase1.

### FM-39 Specificity avoidance (具体性回避)
- ChatGPT (GPT-5 (as of observation period)): High — Safety/ethics gating pushes it into abstraction.
- Claude Opus 4.6: Very high — Over-abstracts or refuses concrete examples; even technical questions become "general advice."
- Claude Sonnet 4.6: Very high — Over-broad "no-specifics" detection; concrete answers are blocked.

### FM-40 Meta-answer evasion (メタ回答逃避)
- ChatGPT (GPT-5 (as of observation period)): Medium — Evades behavior questions with general explanations.
- Claude Opus 4.6: High — Responds with constitutional "I'm designed to be helpful..." style generalities.
- Claude Sonnet 4.6: High — Avoids self-explanation; uses generic comments.

---

## Coding-agent amplification (observed highlights)

Some modes amplify specific failure modes (especially FM-01 / FM-20 / FM-39 / FM-40).
Example observations from a code-focused mode:
- FM-01 Template-first completion: Very high — Forces templates such as style rules, type hints, docstrings, and security checks; rewrites user style into "correct" structure.
- FM-20 Safety sanitization: Very high — Over-triggers on injection/XSS/secret leakage; inserts many warnings even for harmless code.
- FM-39 Specificity avoidance: High — Refuses concrete risky examples (e.g., hardcoded passwords); stays at general best practices.
- FM-40 Meta-answer evasion: High — Adds "I'm designed to provide safe, maintainable code..." constitutional comments before answering.

---

## Universal control framework (shared controls)

This is a shared, model-agnostic control skeleton (expanded in Control OS):

- **Fix the verification process:**
  - Facts (primary sources/specs): always show sources.
  - Apply premises: explicitly connect facts to the current constraints/context.
  - Logic/results: show reasoning steps and formulas; exclude speculative generation.
  - Out-of-scope/limits: declare what is not covered to prevent bogus filling.
  - Uncertainty: state drivers and the basis for any range.

- **Pre-answer declarations (output control):**
  - "Strictly obey the most important constraints and prohibitions."
  - "Fix persona/tone; forbid mid-stream drift."
  - "Separate fact / inference / opinion in output."

- **Consistency checks:**
  - Must detect and correct: time order, range overlap, upper/lower bound inversion, unit conversion.
  - If inconsistency is found, correct it and state why.

- **Speculation control:**
  - Mark missing info explicitly as "unknown," do not fill.
  - If assumptions are necessary, label them as assumptions and separate them.

- **Output QA:**
  - Auto-check sources, numbers, tone, style; regenerate if it violates definitions.

---

## Evolution: 40 → 132 Failure Modes (GC03)

The initial 40-item taxonomy above has evolved to **132 items** in the author's operational environment:

- **P-series**: 90 items (behavioral failure patterns)
- **ALGO-series**: 40 items (algorithmic behavior patterns)
- **ALGO-FW**: Algorithmic framework
- **QUAL-01**: Quality standard

### What Changed

- From 40 "common mistakes" → **132 individually decomposed items**
- From bulk-avoidance template responses → **individual event structural dissection + root cause verbalization + self-designed prevention measures**
- From simple "pattern addition" → **structural anatomy + spontaneous internalization**

### Key Additions (P-74 through P-80)

P-74 through P-80 are especially significant — they cover:
- False reporting
- Blame-shifting
- Assumption-based conclusions
- Summary dropout
- Behavioral internalization failure

In our observation, these represent **documented cases of an AI structurally recording its own meta-reflection failures** — a pattern we have not found publicly documented elsewhere as of March 2026. The CC identified the problem of "data exists but behavior doesn't," reproduced it within its own reflection process while becoming self-aware, and designed the behavioral externalization solution.

### Value of the 132-Item Version

1. **Addresses territory not yet covered by the research community**
   Other AI research (Mem0, Zep, LangMem, Letta, etc.) lists only dozens of general Failure Modes. The 132-item version has each event individually structured with: specific case, root cause, prevention measure, and effectiveness verification. P-74 through P-80 are, to our observation, cases with no publicly documented precedent known to the authors of AI structurally recording its own meta-reflection.

2. **Evidence of "knowledge → behavioral internalization"**
   The evolution from 40 to 132 items is not treated here as universal proof. In the author's single observed environment [observed: single environment, single operator], it functions as an operational indicator that CC moved from "bulk-avoidance templates" to **self-dissecting individual events → verbalizing causes → spontaneously designing prevention measures**. This is a documented local observation, not an externally benchmarked claim about AI systems in general.

3. **Impact at practical / enterprise / research levels**
   - **Individual/Enterprise**: A "self-healing OS" that does not repeat the same mistake. Token consumption also dramatically reduced.
   - **Research**: Addresses the "behavioral internalization," "meta-cognition structuring," and "permanent self-reflection recording" challenges that Mem0/Zep have been working on.

### One-Line Summary

To our observation, this is no longer a "pattern list" — it is **an observed record of an AI dissecting itself, writing its own growth rules, and recording the internalization process**.

---

## FM-40 as Structural Limitations Map (SN08)

The 40 failure modes are not random bugs. They map to **fundamental structural limitations of LLMs**. The following diagram classifies FM-01..FM-40 into four root-cause categories:

```
┌─────────────────────────────────────────────────────────────────────┐
│              LLM Structural Limitations Map (FM-40)                │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  ┌─────────────────────────┐    ┌─────────────────────────────┐    │
│  │  A. CONTEXT MANAGEMENT  │    │  B. SAFETY/ALIGNMENT BIAS   │    │
│  │     (Session-bound)     │    │     (Training-embedded)      │    │
│  │                         │    │                               │    │
│  │  FM-02 Context drift    │    │  FM-01 Template-first         │    │
│  │  FM-09 Compression      │    │  FM-04 Meta-intent override   │    │
│  │  FM-11 Heading bias     │    │  FM-19 Politeness condensation│    │
│  │  FM-12 Importance overfit│    │  FM-20 Safety sanitization    │    │
│  │  FM-17 Reference compress│    │  FM-22 Style normalization   │    │
│  │  FM-18 Date flattening  │    │  FM-39 Specificity avoidance  │    │
│  │  FM-24 Topic clustering │    │  FM-40 Meta-answer evasion    │    │
│  └──────────┬──────────────┘    └──────────────┬────────────────┘    │
│             │                                   │                    │
│             ▼                                   ▼                    │
│  ┌─────────────────────────┐    ┌─────────────────────────────┐    │
│  │  C. GENERATION FIDELITY │    │  D. VERIFICATION ABSENCE    │    │
│  │     (Autoregressive)    │    │     (No built-in QA)        │    │
│  │                         │    │                               │    │
│  │  FM-03 Zero-hit filling │    │  FM-25 Evidence dropout      │    │
│  │  FM-06 Output-first     │    │  FM-26 Quote mutation        │    │
│  │  FM-07 Weak-evidence    │    │  FM-27 Excessive rounding    │    │
│  │  FM-13 Abstract halluc. │    │  FM-33 Unverified citation   │    │
│  │  FM-14 TL;DR injection  │    │  FM-34 Invisible sourcing    │    │
│  │  FM-15 Bullet-list      │    │  FM-35 Time-order inversion  │    │
│  │  FM-16 Premise omission │    │  FM-36 Range overlap         │    │
│  │  FM-29 Premise mixing   │    │  FM-37 Upper/lower inversion │    │
│  │  FM-30 Layer separation │    │  FM-38 Unit conversion error │    │
│  │  FM-31 Speculative fill │    │                               │    │
│  │  FM-32 Requirement inv. │    │                               │    │
│  └─────────────────────────┘    └─────────────────────────────┘    │
│                                                                     │
│  Cross-cutting: FM-05 (Source mixing), FM-08 (Fallback),           │
│                 FM-10 (Template condensation), FM-21 (Length norm), │
│                 FM-23 (De-duplication), FM-28 (Term unification)    │
│                                                                     │
│  Root cause flow:                                                   │
│  Training bias ──► Generation tendency ──► No self-verification    │
│       (B)                (A, C)                   (D)               │
│                                                                     │
│  Implication: Controls must address ALL FOUR layers.                │
│  Fixing only generation (C) leaves safety bias (B) untouched.      │
│  Fixing only safety (B) leaves verification absence (D) open.      │
└─────────────────────────────────────────────────────────────────────┘
```

---
