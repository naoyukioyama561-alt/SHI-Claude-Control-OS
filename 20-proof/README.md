# 20-proof/ — Evidence and Verification
Language: [日本語版はこちら / Japanese version](../ja/20-proof/README-ja.md)

## What the verification levels mean

The verification levels in this repository are defined by **how far a reader can verify using only the public repository**. These levels are defined by the degree of public verifiability: Level A = fully reproducible from public files, Level B = design publicly inspectable but quantitative data outside public repository, Level C = summary public with details outside public repository.

Availability labels below indicate **where the deeper detail lives**, not whether a public page exists. **All 15 achievements have public pages in this repository.** Verification levels indicate the level of public verifiability.

| Level | Definition | What you can do |
|-------|-----------|----------------|
| Level A | Design philosophy is fully public; you can build a similar system in your own environment | try/ to experience -> 10-framework/ to understand -> build in your environment |
| Level B | Design philosophy is public, but quantitative data is provided outside this public repository | You can verify the approach. "How well does it actually work?" is outside this public repository |
| Level C | Concept and partial evidence images only. Detailed design and quantitative data are outside this public repository | You can judge conceptual validity only |

### ★5 (3 items): No.1, No.2, No.12

These three can be understood and applied to your own AI using only the public repository.

- **No.1 Failure Modes Taxonomy**: FM-40 is fully public. You can observe and classify on your own AI
- **No.2 Three-Layer Role Separation**: Complete design philosophy is public. You can design separation in your own environment
- **No.12 Normative Weight Inheritance**: cc_heritage design is public. You can build the inheritance structure in your own environment

> Note: No.12 (Heritage Weight Transfer) is rated ★5 because the complete cc_heritage design is publicly available for replication, though quantitative effect measurements are outside this public repository.

### ★4 (8 items): No.3, 4, 5, 6, 7, 8, 9, 13

Design philosophy is understandable, but quantitative data is provided outside this public repository.

### ★3 (4 items): No.10, 11, 14, 15

Concept is public, but both detailed design and quantitative data are outside this public repository.

## Public / Non-public scope

For per-item scope breakdown, see [achievements/README.md](achievements/README.md).

| Level | Purpose | Includes |
|-------|---------|----------|
| **Public** | Experience + methodology | 40-item [observed: single environment] public FM taxonomy + 15 [observed: single environment] public achievement pages (6 [observed: single environment] full + 9 [observed: single environment] summary) + structural explanations in 10-framework/ + representative SVG diagrams |
| **Phase1** | How to think about building it | 10 [observed: single environment] design documents + FM 60 [observed: single environment] items detailed + diagrams + sample conversations + reason_code table |
| **Phase2** | How to observe structure | All files + all images + all 132 [observed: single environment] FM items + verification logs + source excerpts |
| **Book** | AI governance via SHI theory | All 7 [observed: single environment] chapters + reproduction procedures (no concrete keys) |

Phase1 / Phase2 are listed here only to clarify scope boundaries. The public repository is intended to stand on its own for trial, challenge, and adaptation.

## Notes

- These levels are defined by the degree of public verifiability: Level A = fully reproducible from public files, Level B = design publicly inspectable but quantitative data outside public repository, Level C = summary public with details outside public repository. Independent third-party verification is a future goal
- Your environment may have more advanced implementations. Please let us know via [Issue](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS/issues)
- ★3 means "low public verifiability," not "weak evidence"

## Files

| File | Content |
|------|---------|
| [achievements/](achievements/) | Detailed documentation for each achievement (with images) |
| [timeline.md](timeline.md) | Development timeline of facts |
| [metrics.md](metrics.md) | Publicly safe quantitative data |
| [../images/screenshots/README.md](../images/screenshots/README.md) | Explains why operational screenshots are removed from the public repository and where the safe SVG substitutes live |

---

→ **Next**: [30-adoption/try/](../30-adoption/try/) — try it yourself

→ See also: [10-framework/](../10-framework/) — understand why it works | [Back to README](../README.md)
