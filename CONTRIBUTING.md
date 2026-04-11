# Contributing
Language: [日本語版はこちら / Japanese version](ja/CONTRIBUTING-ja.md)

You can fork, adapt, and build freely under MIT. You do not need to submit code to contribute: observation reports, reproduction notes, claim challenges, broken-link fixes, and translation improvements are all first-class contributions. Issues are the primary channel for contributing to the canonical version.

This repository documents a **methodology**, not a software product. Contributions are welcome — and most valuable — through Issues.

## How to Contribute

This project follows an **Issues-first workflow**. Your observations from real environments are the most valuable contribution you can make, because they help validate (or challenge) the methodology against diverse AI models and usage contexts.

### Report an observation

If you applied the Control OS or FM-40 cheatsheet in your environment and observed something — whether it worked, partially worked, or did not work — please open an Issue with:

- Your AI model (Claude, GPT, Copilot, etc.)
- What you tested (Control OS, specific FM observation, etc.)
- What you observed
- Your environment context (if relevant)

### Challenge a claim

Every claim in this repository is intended to be verifiable. If you find a claim that is unsupported, misleading, or contradicted by your observation, please open an Issue. See [PROVE-IT.md](PROVE-IT.md) for the verification protocol.

### Suggest a structural improvement

If you see a way to improve the methodology's structure (not just wording), please describe:

- What structural condition is currently missing or broken
- What change would remove that obstacle
- Why this improves the reader's experience

## What Happens After You Open an Issue

Your Issue goes through the following flow:

1. **Triage** — The author reads the report and labels it (observation / challenge / structural)
2. **Reproduce or boundary-check** — The author attempts to reproduce the observation in their environment, or checks if the claim/boundary in question is correctly stated
3. **Integration decision** — If confirmed, the observation may be folded into one of:
   - **FM taxonomy revision** (new FM item or existing FM refinement)
   - **PROVE-IT clarification** (claim map update or verification status change)
   - **SCOPE-MATRIX boundary clarification** (Public/Phase1/Phase2 scope adjustment)
   - **Template refinement** (Control OS or adoption template improvement)
4. **Close with reference** — The Issue is closed with a link to the updated document, or a written reason for non-integration

Your observation directly improves the methodology for everyone who uses it.

### What We Accept as Pull Requests
- Typo corrections
- Broken link fixes
- Translation improvements (must maintain en/ja mirror integrity)

Methodology core content is author-curated for the canonical version, but validation work is collaborative by design. Documentation fixes, translation improvements, broken-link fixes, and public-safe demo polish are welcome as Pull Requests.

## What We Do Not Accept

- **Pull Requests for content changes**: This is a methodology repository with specific design decisions. Content changes require alignment with the overall structural design. Please propose changes via Issue instead — the author integrates verified improvements.
- **Automated translation corrections**: Translation quality is managed as part of the en/ja mirror process.
- **Feature requests for software**: This repository does not contain executable software.

## Developer Notes

### Language Policy
- **Root-level files**: English is primary (`README.md`). Japanese counterparts use `-ja` suffix (`README-ja.md`)
- **Directory-level**: Each directory's `README.md` is English. Japanese subdirectories (`ja/`) have their own `README.md` in Japanese
- **Content files**: English in `en/` subdirectory, Japanese in `ja/` subdirectory
- **Principle**: A reader who starts in one language should be able to reach all content without switching languages. Links from Japanese files point to Japanese files; links from English files point to English files
- **`[EN]` annotation**: Used only when a Japanese equivalent genuinely does not exist (e.g., release-checklist). Must be explicitly marked

### File Naming
- English-specific files use `-en` suffix (e.g., `control-os-claude-en.md`)
- Japanese-specific files use `-ja` suffix at root level (e.g., `README-ja.md`)
- Files without suffix in `ja/` directories are Japanese-primary
- Files without suffix in root or `en/` directories are English-primary

## License & Workflow

Fork / reuse / derivative work is fully permitted under MIT. This repository maintains an Issues-first workflow for the canonical version: report observations, propose changes via Issue, and the author integrates verified improvements.

## Code of Conduct

Be respectful. Focus on observations, not opinions. Disagree with evidence, not assertions.

---

See also: [Release Checklist](.github/release-checklist.md) — the project applies its own methodology to its release process.


---

→ [Back to README](README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
