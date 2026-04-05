# START HERE -- Understand in 3 Minutes

## The Problem

AI coding assistants repeat the same types of failures. They forget context under pressure. They forget pain across sessions. Prompting alone does not fix structural problems.

## The Answer

This project provides a **structural governance methodology** for AI assistants, developed through approximately one month of intensive observation [observed: single environment, single operator] and 132 classified failure modes [observed: single environment, N undisclosed; → metrics](20-proof/metrics.md).

| Component | What it does | Time to try |
|-----------|-------------|-------------|
| [Control OS](30-adoption/try/) | Paste into your AI's system prompt. Suppresses common failure modes. | 30 seconds |
| [FM-40 Cheatsheet](30-adoption/try/fm-40-cheatsheet-en.md) | Identify which failure modes your AI triggers most | 10 minutes |
| [Before/After Demo](30-adoption/try/before-after-demo-en.md) | See the difference with and without Control OS | 5 minutes |

> **Terminology**: Three-layer (role split) ≠ 4+1 (quality stack) ≠ 5-layer (governance cycle). See [GLOSSARY.md](GLOSSARY.md) for definitions.

## What You Get for Free (This GitHub Repository)

- **40 Failure Modes** classified across Claude, GPT, and Copilot
- **Control OS templates** for 3 AI models (copy-paste ready)
- **Framework documents** explaining why the Control OS works
- **15 documented achievements** [→ achievements](20-proof/achievements/README.md): all 15 have public pages in this repository; 6 are full public pages, and the other 9 are public summary pages with clearly labeled evidence boundaries
- **Before/After demonstrations**
- **Transfer templates** for your own environment

## Reading Order

```
You are here: START-HERE.md
  |
  +--> Want to try immediately?     --> 30-adoption/try/
  |
  +--> Want to verify claims?       --> PROVE-IT.md
  |
  +--> Want to understand the why?  --> 10-framework/
  |
  +--> Want to see evidence?        --> 20-proof/
  |
  +--> Want to check scope?         --> SCOPE-MATRIX.md
```

## Public Boundary

This repository is the primary evaluation surface. You can try, challenge, and adapt the methodology using only the public files here. [SCOPE-MATRIX.md](SCOPE-MATRIX.md) exists to show what is intentionally out of public scope, not to gate the core evaluation experience.

<details>
<summary><strong>Who This Is For</strong></summary>

- **AI developers** who want to reduce failure rates in AI-assisted coding
- **Engineering managers** evaluating AI governance approaches
- **Researchers** interested in structural AI failure analysis
- **Anyone** who has experienced AI making the same mistakes repeatedly

</details>

<details>
<summary><strong>Who This Is NOT For</strong></summary>

- Those looking for a plug-and-play product (this is a methodology, not software)
- Those expecting guaranteed results (all effects should be verified in your own environment)

</details>

## The Single Most Important Point

**In this framework, recurrent AI failures are treated as structural, observable, classifiable, and preventable -- when you approach them structurally.**

The 40 Failure Modes in this repository are a starting point. Observe your own AI, classify what you see, and build structural countermeasures. The methodology is intended to be model-agnostic, but should be verified in your own environment.

---

> Next: [Try it now](30-adoption/try/) | [Verify claims](PROVE-IT.md) | [Back to README](README.md)

[日本語版 / Japanese](START-HERE-ja.md)
