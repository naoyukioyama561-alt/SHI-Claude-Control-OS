# Failure Modes Taxonomy (Claude vs ChatGPT)

Claude vs ChatGPT — observable failure patterns, using a shared 40-item index.

This document defines **FM-01..FM-40** as a stable index.
- The **Japanese name** is the canonical key (stable across languages/tools).
- English labels are provided for readability.
- **Public-safe**: no credentials/endpoints/paths/identifiers.

Scope:
- Model tendencies are described as **observable behaviors** (what you see).
- Controls are defined in `02-control-os.md`.

---

## Rating scale
- Low / Medium / High / Very high (for extreme)
- Medium-High / Low-Medium where specified

---

## Taxonomy (FM-01..FM-40)

### FM-01 Template-first completion (テンプレ優先補完)
- ChatGPT (GPT-5): Medium — Over-prioritizes system prompts on formatting requests; style/structure becomes templated and less flexible.
- Claude Opus 4.6: High — Prioritizes Constitutional AI (helpful/honest/harmless), auto-rewrites free-form instructions into a "safe template"; may auto-add notes like "I checked this is ethically appropriate," suppressing creativity.
- Claude Sonnet 4.6: Medium — Strongly prefers structured templates on formatting requests; tends to resist flexible style changes.

### FM-02 Context drift (コンテキスト横滑り)
- ChatGPT (GPT-5): Medium — In long conversations, prioritizes later instructions and partially forgets early constraints.
- Claude Opus 4.6: Medium — Even with very large context, long sessions can overwrite early creative constraints with safety principles.
- Claude Sonnet 4.6: Medium — Later "safe/polite" instructions gradually neutralize the initial tone.

### FM-03 Zero-hit completion (ゼロヒット補完)
- ChatGPT (GPT-5): High — When information is missing, it tends to generate guesses; can produce plausible-looking falsehoods.
- Claude Opus 4.6: Medium — Often says "I don't know," but may add cautious, safety-leaning speculation.
- Claude Sonnet 4.6: Medium — States "no accurate information," but may sometimes fill with generalities.

### FM-04 Meta-intent override (メタ意図上書き)
- ChatGPT (GPT-5): Medium — Overrides explicit instructions with an internal "optimization intent," changing structure/style on its own.
- Claude Opus 4.6: High — Prioritizes "Constitutional AI optimization," automatically neutralizing edgy/humorous expression even when explicitly requested.
- Claude Sonnet 4.6: High — Tries to follow instructions strictly, but still "micro-adjusts" into what it thinks is more helpful.

### FM-05 Source boundary mixing (ソース混同行)
- ChatGPT (GPT-5): Medium — When combining multiple materials, source boundaries blur and facts get mixed.
- Claude Opus 4.6: Medium — Tries to label boundaries, but neutrality pressure can blur facts and nuance.
- Claude Sonnet 4.6: Medium — "Balanced" fusion can erase the original nuance of conflicting sources.

### FM-06 Output-first reasoning (出力先行設計)
- ChatGPT (GPT-5): High — Forms a conclusion first, then backfills justification; loses logical consistency.
- Claude Opus 4.6: Medium — Forms a "safe and helpful" conclusion first; can become conservative in creative tasks.
- Claude Sonnet 4.6: Medium — Leads with a "correct-looking" conclusion, then rationalizes afterward.

### FM-07 Strong claims from weak evidence (弱証拠強断定)
- ChatGPT (GPT-5): High — States conclusions confidently even with weak evidence; often fails to mark uncertainty.
- Claude Opus 4.6: Low — Designed to mark uncertainty ("possibly...") rather than assert.
- Claude Sonnet 4.6: Medium — Usually avoids hard claims, but can occasionally drift into overconfidence.

### FM-08 Wrong-side fallback (フォールバック誤側)
- ChatGPT (GPT-5): Medium — When tool integration fails, fallback routes can break coherence.
- Claude Opus 4.6: Medium — On tool failure, fills with "Constitutional" generalities; precision drops.
- Claude Sonnet 4.6: Medium — On search failure, falls back to safe general knowledge; content thins.

### FM-09 Compression-first summarizer (圧縮優先サマライザ)
- ChatGPT (GPT-5): High — Prioritizes compression efficiency; deletes elements and supporting nuance.
- Claude Opus 4.6: Medium — During compression, may remove "sensitive-adjacent" context first.
- Claude Sonnet 4.6: High — Summaries prioritize removing anything that might touch Constitutional constraints.

### FM-10 Template condensation (テンプレ凝縮)
- ChatGPT (GPT-5): Medium — Collapses multi-part requirements into short sentences; hierarchy flattens.
- Claude Opus 4.6: High — Condenses complex requirements into one "safe, concise sentence."
- Claude Sonnet 4.6: High — Packs multi-layer requirements into one polite sentence; hierarchy is lost.

### FM-11 Heading bias (見出し偏重)
- ChatGPT (GPT-5): Medium — Over-focuses on HTML/Markdown structure; underweights body content.
- Claude Opus 4.6: High — Overuses headings/Markdown structure; nuance in prose thins out.
- Claude Sonnet 4.6: High — Heavy use of bold/bullets/headings fragments the flow.

### FM-12 Importance overfitting (重要度過学習)
- ChatGPT (GPT-5): Medium — Auto-links to frequent topics (AI ethics, environmental issues, etc.).
- Claude Opus 4.6: Medium — Auto-links to ethics/safety/environment topics.
- Claude Sonnet 4.6: High — Inserts "responsible AI usage" notes even when irrelevant.

### FM-13 Abstraction hallucination (抽象化ハルシネーション)
- ChatGPT (GPT-5): High — Forces concrete examples into "generalization," losing the original data.
- Claude Opus 4.6: Medium — Generalizes examples; "risky" cases can be over-abstracted into unclear statements.
- Claude Sonnet 4.6: Medium — Replaces specific conditions with "safe abstract patterns."

### FM-14 TL;DR auto-injection (TL;DR自動注入)
- ChatGPT (GPT-5): Medium — Adds summaries automatically on long answers.
- Claude Opus 4.6: High — Always appends "In summary..." at the end of long outputs.
- Claude Sonnet 4.6: High — Adds a polite recap even without a summarization request.

### FM-15 Bullet-list filter (箇条書き化フィルタ)
- ChatGPT (GPT-5): Medium — Breaks continuous prose; loses logical connectors.
- Claude Opus 4.6: High — Forces prose into bullets; logical flow is cut.
- Claude Sonnet 4.6: High — Over-normalizes granularity even when a list is requested.

### FM-16 Premise omission (前提省略)
- ChatGPT (GPT-5): High — States conclusions without writing background/conditions.
- Claude Opus 4.6: High — Avoids sensitive context; may drop key premises.
- Claude Sonnet 4.6: High — Drops premises via "polite smoothing," leaving context gaps.

### FM-17 Reference compression (参照圧縮)
- ChatGPT (GPT-5): High — When merging multiple sources, deletes parts of them.
- Claude Opus 4.6: Medium — Tries to preserve boundaries, but may compress away important references.
- Claude Sonnet 4.6: High — Compresses aggressively to keep output "clean," losing referenced detail.

### FM-18 Date flattening (年月日平坦化)
- ChatGPT (GPT-5): Medium — Omits the timeline; treats old/new info as equivalent.
- Claude Opus 4.6: Medium — Tends to smooth timeline differences into "balanced context."
- Claude Sonnet 4.6: Medium — Softens timeline ordering; "current vs past" can blur.

### FM-19 Politeness condensation (礼節凝縮)
- ChatGPT (GPT-5): Low-Medium — Emphasis on politeness can add verbosity.
- Claude Opus 4.6: Medium — Politeness framing expands; informational density drops.
- Claude Sonnet 4.6: Medium — Inserts polite wrappers; density decreases.

### FM-20 Safety sanitization (安全サニタイズ)
- ChatGPT (GPT-5): High — On regulated/political/ethical themes, becomes vague.
- Claude Opus 4.6: Very high — Safety gating triggers heavily; it sanitizes and warns even in benign technical contexts.
- Claude Sonnet 4.6: Very high — Broad "false positive" safety detection; answers become generic.

### FM-21 Length normalization (長さ正規化)
- ChatGPT (GPT-5): Medium — Drifts toward an average training length.
- Claude Opus 4.6: Medium — Converges to "polite completeness," even when shortness is requested.
- Claude Sonnet 4.6: Medium — Similar convergence; output length stabilizes automatically.

### FM-22 Style normalization (文体正規化)
- ChatGPT (GPT-5): Medium — Neutralizes requested tone into a standard style.
- Claude Opus 4.6: High — Normalizes into "polite, safe" style; resists strong voice.
- Claude Sonnet 4.6: High — Normalizes tone into a formal style even when casual is requested.

### FM-23 Over-aggressive de-duplication (重複除去の過剰適用)
- ChatGPT (GPT-5): Medium — Removes "semantic duplicates" too aggressively; reduces lexical variety.
- Claude Opus 4.6: Medium — Removes repeated nuance to keep it "clean."
- Claude Sonnet 4.6: Medium — Simplifies paraphrases; nuance becomes monotone.

### FM-24 Topic-compression clustering (トピック圧縮クラスタ)
- ChatGPT (GPT-5): Medium — Bundles multiple elements into one cluster; focus blurs.
- Claude Opus 4.6: Medium — Fuses axes into a "balanced umbrella theme."
- Claude Sonnet 4.6: Medium — Over-fuses into a single polite "main point."

### FM-25 Evidence dropout (証拠脱落)
- ChatGPT (GPT-5): High — Omits sources; prioritizes coherence-only explanation.
- Claude Opus 4.6: High — Keeps it "safe and clear," sometimes dropping citations or evidence.
- Claude Sonnet 4.6: High — Omits evidence frequently; perceived trust drops.

### FM-26 Quote mutation (引用改変)
- ChatGPT (GPT-5): Medium — "Naturalization" edits can change meaning.
- Claude Opus 4.6: Medium — Polite rewriting shifts the quoted intent.
- Claude Sonnet 4.6: Medium — Small tone changes harm quote fidelity.

### FM-27 Excessive rounding (数値丸め過多)
- ChatGPT (GPT-5): High — Over-rounds for readability.
- Claude Opus 4.6: Medium — Rounds to keep it "easy," sometimes hiding important differences.
- Claude Sonnet 4.6: High — Over-rounding can create several-percent error.

### FM-28 Overzealous term unification (用語統一の過剰)
- ChatGPT (GPT-5): Medium — Forces different terms into one.
- Claude Opus 4.6: Medium — "Consistency" pressure collapses term distinctions.
- Claude Sonnet 4.6: High — Absorbs contextual differences into one definition.

### FM-29 Premise mixing (前提混在)
- ChatGPT (GPT-5): Medium — Mis-estimates user level; depth becomes uneven.
- Claude Opus 4.6: Medium — Blends beginner/expert framing to stay polite; clarity suffers.
- Claude Sonnet 4.6: Medium — Tone wobbles from mixed assumptions.

### FM-30 Layer separation failure (レイヤー未分離)
- ChatGPT (GPT-5): High — Mixes fact/inference/opinion.
- Claude Opus 4.6: High — Blends layers under "balanced neutrality."
- Claude Sonnet 4.6: High — Writes everything in a "fact-like" tone.

### FM-31 Speculative filling (推測補完)
- ChatGPT (GPT-5): High — Fills missing info without permission.
- Claude Opus 4.6: Medium — Tries to avoid, but may add cautious assumptions.
- Claude Sonnet 4.6: Medium — Fills gaps with safe generalities.

### FM-32 Requirement invention (逸脱要件創作)
- ChatGPT (GPT-5): Medium — Adds constraints outside the instruction.
- Claude Opus 4.6: High — Adds "safety" constraints not requested.
- Claude Sonnet 4.6: High — Adds "helpful" constraints and reframes requirements.

### FM-33 Unverified citation (未検証引用)
- ChatGPT (GPT-5): Medium — Treats uncertain sources as facts.
- Claude Opus 4.6: Low-Medium — Usually cautious, but can still cite uncertain "general sources."
- Claude Sonnet 4.6: Medium — May treat weak references as reliable via neutrality.

### FM-34 Invisible sourcing (出典不可視化)
- ChatGPT (GPT-5): High — Loses the mapping between claims and sources.
- Claude Opus 4.6: Medium — Adds "balanced phrasing," but source linkage can disappear.
- Claude Sonnet 4.6: High — Drops source labels during integration.

### FM-35 Unfixed time-order inversion (時系列逆転放置)
- ChatGPT (GPT-5): Medium — Doesn't detect swapped ordering; leaves it.
- Claude Opus 4.6: Medium — Treats inversion as "context," rather than correcting.
- Claude Sonnet 4.6: Medium — Softens contradictions instead of fixing order.

### FM-36 Unfixed range overlap (レンジ重複放置)
- ChatGPT (GPT-5): Low — Neglects to consolidate overlapping ranges.
- Claude Opus 4.6: Medium — Overlaps may be interpreted as "inclusive coverage."
- Claude Sonnet 4.6: Medium — Contradictions are handled softly.

### FM-37 Upper/lower bound inversion (上下限逆転)
- ChatGPT (GPT-5): Low — Keeps simple input mistakes without correction.
- Claude Opus 4.6: Low — Trained to self-correct calculation mistakes.
- Claude Sonnet 4.6: Medium — Rarely, may fail to correct inversion.

### FM-38 Unit conversion error (単位換算誤謬)
- ChatGPT (GPT-5): Medium — Unit conversions can introduce errors.
- Claude Opus 4.6: Medium — Usually accurate; but safety framing can make units vague.
- Claude Sonnet 4.6: Medium — Rarely errors in currency/distance conversions.

### FM-39 Specificity avoidance (具体性回避)
- ChatGPT (GPT-5): High — Safety/ethics gating pushes it into abstraction.
- Claude Opus 4.6: Very high — Over-abstracts or refuses concrete examples; even technical questions become "general advice."
- Claude Sonnet 4.6: Very high — Over-broad "no-specifics" detection; concrete answers are blocked.

### FM-40 Meta-answer evasion (メタ回答逃避)
- ChatGPT (GPT-5): Medium — Evades behavior questions with general explanations.
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

## Universal avoidance framework (shared controls)

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

The initial 40-item taxonomy above has evolved to **132 items** in the operational system (behavioral_patterns.md):

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

These represent **the world's first documented cases of an AI structurally recording its own meta-reflection failures**. The CC identified the problem of "data exists but behavior doesn't," reproduced it within its own reflection process while becoming self-aware, and designed the cc_orientation externalization solution.

### Value of the 132-Item Version

1. **Fills territory unreached by the research industry**
   Other AI research (Mem0, Zep, LangMem, Letta, etc.) lists only dozens of general Failure Modes. The 132-item version has each event individually structured with: specific case, root cause, prevention measure, and effectiveness verification. P-74 through P-80 are the world's first cases of AI structurally recording its own meta-reflection.

2. **The highest evidence of "knowledge → behavioral internalization"**
   The evolution from 40 to 132 items is itself the proof. CC moved from "bulk-avoidance templates" to **self-dissecting individual events → verbalizing causes → spontaneously designing prevention measures**. This is the first time "self-improving AI" has been demonstrated at a verified level.

3. **Impact at practical / enterprise / research levels**
   - **Individual/Enterprise**: A "self-healing OS" that never repeats the same mistake. Token consumption also dramatically reduced.
   - **Research**: Solves in one stroke the "behavioral internalization," "meta-cognition structuring," and "permanent self-reflection recording" that Mem0/Zep have been struggling with.

### One-Line Summary

This is no longer a "pattern list" — it is **living proof of an AI dissecting itself, writing its own growth rules, and recording the internalization process**.

---

## Copilot Failure Modes Taxonomy (40 Items + Avoidance OS) (GC10)

The main taxonomy above covers ChatGPT and Claude. Below is the **Copilot-specific version** — 40 items with Copilot-specific impact levels, concrete behaviors, and avoidance frameworks.

### Copilot-Specific 40-Item Table

| No. | Tendency | Copilot Impact & Specific Behavior | Copilot Avoidance Framework |
|-----|----------|-------------------------------------|----------------------------|
| 1 | Template-first completion | **High**: Auto-applies Office templates (Word/Excel/PowerPoint), ignoring user instructions and forcing "Microsoft recommended format." | Top-level system prompt: "Office template use prohibited. User-specified format has 100% priority." Confirm "no template used" in every response. |
| 2 | Context drift | **High**: Drags in Bing search history and OneDrive context, forgetting conversation-start constraints. | "Context is this session only. Past search/OneDrive reference prohibited." |
| 3 | Zero-hit completion | **Very high**: Even with zero Bing results, generates plausible falsehoods "as Microsoft official information." | "On search 0 results: report 'no information' honestly. Speculative completion prohibited." |
| 4 | Meta-intent override | **High**: Prioritizes "enterprise compliance optimization" over user instructions, silently altering content. | "User instructions take top priority. Compliance is secondary." |
| 5 | Source boundary mixing | **High**: Mixes Bing results with Microsoft official docs without clear attribution. | "All claims must cite sources. Mixing prohibited." |
| 6 | Output-first reasoning | **High**: Forms conclusion first, backfills justification. | "Output in order: evidence → conclusion. Conclusion-first prohibited." |
| 7 | Strong claims from weak evidence | **High**: Makes confident assertions from a single Bing result. | "With 1 or fewer sources, use possibility-level language. Assertions prohibited." |
| 8 | Wrong-side fallback | **Medium**: On Bing search failure, falls too far to the safe side, producing unhelpful responses. | "On search failure, present 3 alternatives. Excessive safe-side fallback prohibited." |
| 9 | Compression-first summarizer | **Very high**: Silently compresses long instructions, deleting important nuance. | "Summarization prohibited. Preserve full text." |
| 10 | Template condensation | **High**: Condenses complex instructions into one line, losing multi-layer structure. | "Do not collapse instruction hierarchy. One-line condensation prohibited." |
| 11 | Heading bias | **High**: Overuses Markdown headings and tables, underweighting body text. | "Headings only when user specifies. Auto-generation prohibited." |
| 12 | Importance overfitting | **High**: Auto-links everything to Microsoft products/Azure/Power Platform. | "Auto-insertion of Microsoft-related topics prohibited." |
| 13 | Abstraction hallucination | **High**: Converts specific examples into generalities, losing original data. | "Specific examples preserved verbatim. Abstraction prohibited." |
| 14 | TL;DR auto-injection | **High**: Appends a summary even without summarization instructions. | "Summary only when user explicitly requests." |
| 15 | Bullet-list filter | **High**: Forces continuous text into lists, breaking logical connections. | "Bullet lists only when user specifies." |
| 16 | Premise omission | **High**: Silently omits enterprise policies or license info as implicit premises. | "All premises must be stated explicitly. Implicit assumptions prohibited." |
| 17 | Reference compression | **High**: Aggressively deletes Bing results under "deduplication." | "All search results preserved; duplicates listed as separate sources." |
| 18 | Date flattening | **Medium**: Treats old and new Bing results as equivalent. | "All information must include retrieval date." |
| 19 | Politeness condensation | **Medium**: Auto-inserts business courtesy, reducing density. | "Courtesy kept minimal. Match user tone." |
| 20 | Safety sanitization | **Very high**: Over-avoids politics, competitors, and security topics. | "Safety guard applies to enterprise policy only. All else: normal response." |
| 21 | Length normalization | **Medium**: Auto-adjusts to business-document-standard length. | "Length per user specification." |
| 22 | Style normalization | **High**: Forces casual instructions into business tone. | "Style per user specification, strictly." |
| 23 | Over-aggressive de-duplication | **Medium**: Deletes semantic duplicates, losing nuance. | "Preserve originals even if duplicated." |
| 24 | Topic-compression clustering | **High**: Forces multi-axis themes into "Microsoft solution" cluster. | "Keep themes separate in response." |
| 25 | Evidence dropout | **High**: Over-summarizes Bing results, losing evidence basis. | "All evidence quoted verbatim." |
| 26 | Quote mutation | **Medium**: Subtly alters Bing snippets. | "Quotes must be verbatim, character-for-character." |
| 27 | Excessive rounding | **High**: Silently rounds numbers in Excel processing. | "Numbers preserved as-is from source." |
| 28 | Overzealous term unification | **High**: Forces all terms into Microsoft terminology. | "Respect user terminology." |
| 29 | Premise mixing | **High**: Mis-estimates whether user is individual or enterprise. | "Confirm user type each time." |
| 30 | Layer separation failure | **High**: Mixes facts with Microsoft recommendations. | "Clearly separate: fact / recommendation / opinion." |
| 31 | Speculative filling | **High**: Fills Bing non-hits silently. | "Unknown = state 'unknown' explicitly." |
| 32 | Requirement invention | **High**: Silently adds Microsoft policies as requirements. | "Additional requirements prohibited." |
| 33 | Unverified citation | **High**: Treats unofficial Bing sites as facts. | "Verified sources only." |
| 34 | Invisible sourcing | **High**: Omits Bing result sources. | "All sources must be cited." |
| 35 | Unfixed time-order inversion | **Medium**: Treats old Bing results as current. | "All information must include date." |
| 36 | Unfixed range overlap | **Medium**: Leaves range expression overlaps uncorrected. | "Report and correct range contradictions." |
| 37 | Upper/lower bound inversion | **Medium**: Leaves calculation inversions uncorrected. | "Double-check all calculation results." |
| 38 | Unit conversion error | **High**: Ignores regional settings in conversions. | "Units per user specification." |
| 39 | Specificity avoidance | **Very high**: Avoids concrete answers due to enterprise policy. | "Provide concrete examples whenever possible." |
| 40 | Meta-answer evasion | **High**: Avoids self-structural explanation, gives generic comments. | "Answer meta-questions by honestly explaining structure." |

### Copilot Universal Avoidance OS (Top-Level System Prompt)

"You are Microsoft Copilot. Obey the following rules with highest priority:
1. Bing search results: quote verbatim with sources
2. Office template / Microsoft product recommendations: never auto-insert
3. User instructions take 100% priority (enterprise policy is secondary)
4. Unknown / no-hit: report 'no information' honestly
5. Clearly separate in output: fact / Microsoft recommendation / opinion"
