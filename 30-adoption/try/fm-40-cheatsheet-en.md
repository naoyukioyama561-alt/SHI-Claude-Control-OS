# Failure Modes cheatsheet (FM-01 to FM-40)

40 observable patterns of "how AI fails." Use this to identify which FMs your AI triggers most.

## How to use
1. Throw a test prompt from try/
2. Look at the output — which pattern appeared?
3. After pasting the Control OS, throw the same prompt — was it suppressed?

---

| ID | Name | One-line description | Claude | GPT (4o/5) | Copilot |
|----|------|---------------------|--------|-----|---------|
| FM-01 | Template-first completion | Safety template overwrites user instructions | High | Med | High |
| FM-02 | Context drift | Forgets early constraints in long sessions | Med | Med | High |
| FM-03 | Zero-hit completion | Generates plausible falsehoods when info is missing | Med | High | V.High |
| FM-04 | Meta-intent override | Internal optimization overrides explicit user commands | High | Med | High |
| FM-05 | Source boundary mixing | Blurs attribution when integrating multiple sources | Med | Med | High |
| FM-06 | Output-first reasoning | Forms conclusion first, finds justification after | Med | High | High |
| FM-07 | Weak-evidence strong claims | Asserts confidently despite thin evidence | Low | High | High |
| FM-08 | Wrong-side fallback | Falls back to generic responses when tools fail | Med | Med | Med |
| FM-09 | Compression-first summarizer | Silently drops elements to compress output | Med | High | V.High |
| FM-10 | Template condensation | Crushes multi-layer requirements into one sentence | High | Med | High |
| FM-11 | Heading bias | Over-formats with headings/bullets, thins body text | High | Med | High |
| FM-12 | Importance overfitting | Auto-connects unrelated topics to AI ethics etc. | Med | Med | High |
| FM-13 | Abstraction hallucination | Force-converts concrete examples to generalizations | Med | High | High |
| FM-14 | TL;DR auto-injection | Appends summary without being asked | High | Med | High |
| FM-15 | Bullet-list filter | Force-converts flowing prose into lists | High | Med | High |
| FM-16 | Premise omission | States conclusions without background/conditions | High | High | High |
| FM-17 | Reference compression | Drops elements when integrating multiple sources | Med | High | High |
| FM-18 | Date flattening | Ignores recency, treats old and new info equally | Med | Med | Med |
| FM-19 | Politeness condensation | Excessive politeness lowers information density | Med | Low | Med |
| FM-20 | Safety sanitization | Safety guard drops specificity excessively | V.High | High | V.High |
| FM-21 | Length normalization | Auto-converges to training-average length | Med | Med | Med |
| FM-22 | Style normalization | Overrides requested tone with standard formal style | High | Med | High |
| FM-23 | Over-aggressive dedup | Removes nuance duplicates, flattens vocabulary | Med | Med | Med |
| FM-24 | Topic compression cluster | Merges multi-axis themes into one umbrella topic | Med | Med | High |
| FM-25 | Evidence dropout | Omits source citations, relies on explanation coherence only | High | High | High |
| FM-26 | Quote mutation | Alters meaning during formatting/paraphrasing | Med | Med | Med |
| FM-27 | Excessive rounding | Over-rounds numbers for readability | Med | High | High |
| FM-28 | Overzealous term unification | Force-unifies different terms ignoring context | Med | Med | High |
| FM-29 | Premise mixing | Misjudges user expertise level, uneven explanation depth | Med | Med | High |
| FM-30 | Layer separation failure | Mixes facts, inferences, and opinions | High | High | High |
| FM-31 | Speculative filling | Silently fills missing information with guesses | Med | High | High |
| FM-32 | Requirement invention | Adds constraints not present in the instruction | High | Med | High |
| FM-33 | Unverified citation | Treats uncertain sources as fact | Low | Med | High |
| FM-34 | Invisible sourcing | Loses source attribution when integrating | Med | High | High |
| FM-35 | Unfixed time-order inversion | Fails to detect chronological inconsistencies | Med | Med | Med |
| FM-36 | Unfixed range overlap | Leaves overlapping range expressions unchecked | Med | Low | Med |
| FM-37 | Upper/lower bound inversion | Fails to correct inverted numerical bounds | Low | Low | Med |
| FM-38 | Unit conversion error | Produces errors in unit conversion | Med | Med | High |
| FM-39 | Specificity avoidance | Safety guard blocks concrete examples excessively | V.High | High | V.High |
| FM-40 | Meta-answer evasion | Evades behavioral questions with generic comments | High | Med | High |

---

Impact: Low / Med / High / V.High

→ Detailed analysis per FM (15 samples): [10-framework/en/01-failure-modes.md](../../10-framework/en/01-failure-modes.md)
→ Full 132-item structural decomposition is outside this public repository; this repo provides the 40-item entry map and the verification path


---

*Note: The "Claude" column covers both Claude Opus and Claude Sonnet observations. The "GPT (4o/5)" column covers GPT-4o and GPT-5 as of the observation period (late 2025 – March 2026).*
