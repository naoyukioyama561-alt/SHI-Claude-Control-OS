# SHI-Claude-Control-OS

**Make AI work like a system, not a slot machine.**

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) [![SSRN Preprint](https://img.shields.io/badge/SSRN-6299258-blue.svg)](https://ssrn.com/abstract=6299258)

[日本語版 / Japanese](README-ja.md)

---

*You asked your AI to review code yesterday. Today it makes the same mistake. You explain the rule again. It says "understood" — and breaks it an hour later.*

**Sound familiar?**

This repository exists for that moment — when you realize AI is useful but still too fragile, too forgetful, and too dependent on you remembering everything.

> **What this is**: A structural governance methodology + copy-paste templates + verification guide — for reducing repeated AI failures.
> **What you get free**: 40 classified failure modes, Control OS templates for 3 AI models, a Before/After demo, an interactive dashboard, and a verification protocol.
> **Free tier is sufficient to try, verify, and challenge the methodology.** No installation required — copy, paste, and test.

---

## What changes after adoption

| Before | After |
|--------|-------|
| Same bug, again in active use. AI apologizes, repeats it tomorrow | Failure mode classified, structurally blocked |
| Monday morning: new session. AI forgot everything from Friday | Heritage system preserves context across sessions |
| "I understand the rules" — violates them in the same working cycle | External monitor catches violations before they ship |
| Quality degrades silently as context grows | 4+1 layer quality system maintains standards |
| You return after time away. Context continuity is gone | Successor AI inherits judgment, not just rules |

<p align="center">
  <img src="images/diagrams/before-after-comparison-en.svg" alt="Before/After: AI behavior with and without structural governance" width="720">
</p>

→ [See a real case study](20-proof/public-case-01.md)

---

## Try it right now (30 seconds)

1. **Copy** the [Control OS](30-adoption/try/control-os-claude-en.md) into your AI's system prompt
2. **Test** it with the [Before/After Demo](30-adoption/try/before-after-demo-en.md) (5 minutes)
3. **Verify** claims in [PROVE-IT.md](PROVE-IT.md) (15 minutes)

| Your AI | Control OS template | Time to test |
|---------|-------------------|--------------|
| Claude Code / Claude | [control-os-claude](30-adoption/try/control-os-claude-en.md) | 30 sec |
| ChatGPT (GPT-4o / GPT-5) | [Control OS for GPT](30-adoption/try/control-os-gpt-en.md) | 30 sec |
| GitHub Copilot | [Control OS for Copilot](30-adoption/try/control-os-copilot-en.md) | 30 sec |

Full Japanese versions: [30-adoption/ja/try/](30-adoption/ja/try/)

---

### See the system in action

**[Open the interactive demo (GitHub Pages)](https://naoyukioyama561-alt.github.io/SHI-Claude-Control-OS/demo/en/index.html)**
- English demo: [Click here](https://naoyukioyama561-alt.github.io/SHI-Claude-Control-OS/demo/en/index.html)
- Japanese demo: [Click here](https://naoyukioyama561-alt.github.io/SHI-Claude-Control-OS/demo/jp/index.html)

*This demo is a public-safe static page, completely independent from any live environment. Buttons, search, and filters all work — try them.*

---

## Why this exists

Most AI projects don't fail because the model is weak.
They fail because the **control layer** is weak.

- Instructions live in scattered chats
- Fixes depend on memory instead of structure
- One person becomes the only person who knows how it works
- Small errors quietly become operational debt

**This project breaks that pattern** — not by asking you to trust AI harder, but by giving you a way to define control points, verify behavior, and make the workflow legible to other humans.

---

## Repository map

```
YOU ARE HERE
  |
  |-- "I want to try it"          --> 30-adoption/try/        (30 seconds)
  |-- "I want to see the proof"   --> PROVE-IT.md             (15 minutes)
  |-- "I want to understand why"  --> 10-framework/           (30 minutes)
  |-- "I want the evidence"       --> 20-proof/               (deep dive)
  |-- "I want to build my own"    --> 30-adoption/templates/  (your environment)
  |
  Deeper:
  |-- Heritage & philosophy       --> 40-heritage/
  |-- Scope & editions            --> 50-boundary/
  |-- Detailed scope breakdown    --> SCOPE-MATRIX.md
```

<details>
<summary><strong>Evidence labels & terminology</strong></summary>

`[observed: single environment]` = measured in one environment. `[design target]` = architecture goal, not benchmarked. `[illustrative]` = explanatory, not data. See [GLOSSARY.md](GLOSSARY.md) for full definitions.

Three-layer separation (role split) ≠ 4+1 quality system (quality stack) ≠ 5-layer loop (governance cycle). They describe different dimensions of the same system.
</details>

---

## The research behind it

This methodology is grounded in **Structural Hierarchical Intelligence (SHI)** theory. The framework emerged from approximately one month of full-time observation [observed: single environment, single operator] producing 132 classified failure modes [→ metrics](20-proof/metrics.md) and a governance architecture documented in a research paper.

> Oyama, N. (2025). *Structural Hierarchical Intelligence for AI Governance* (SSRN preprint, posted 2025). Available at SSRN: [https://ssrn.com/abstract=6299258](https://ssrn.com/abstract=6299258). Repository published: 2026.

---

## Quick links

- [START-HERE](START-HERE.md) — 3-minute orientation
- [PROVE-IT](PROVE-IT.md) — verify every claim yourself
- [Interactive Dashboard](docs/dashboard.html) (Download and open in browser, or [enable GitHub Pages](https://docs.github.com/en/pages))
- [SCOPE-MATRIX](SCOPE-MATRIX.md) — free vs. paid breakdown
- [GLOSSARY](GLOSSARY.md) — key terms and definitions
- [CONTRIBUTING](CONTRIBUTING.md) — how to report observations and contribute
- [CITATION](CITATION.cff) — how to cite this work
- [CHANGELOG](CHANGELOG.md) — version history

---

## If this made you think "I want this too"

1. **⭐ Star this repository** — it helps more builders and operators find it
2. **Share it with one person** — send it to the teammate who has already said: *"AI is useful, but I still don't trust the workflow"*

> [Why I built this →](40-heritage/why-i-am-doing-this.md)

---

<sub>

**License**: [MIT](LICENSE) — use, modify, and redistribute freely.

**Disclaimer**: All effects described in this repository were observed in the author's environment. Results may vary depending on AI model, usage context, and configuration. Verify all claims in your own environment before drawing conclusions. This project provides a methodology, not guaranteed outcomes.

**Language**: [日本語版はこちら / Japanese version](README-ja.md)

</sub>
