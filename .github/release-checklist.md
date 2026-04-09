# Release Checklist (5-Set)
Language: [日本語版はこちら / Japanese version](../ja/.github/release-checklist-ja.md)

This checklist applies the repository's own quality management system
(10-framework/05-quality-system.md) to its own publication process.

> "Apply to yourself what you teach others."
> The existence of this checklist is itself evidence that the Control OS functions.

---

## Preconditions

- [ ] All image paths point to existing files (`grep -rn '!\[' --include='*.md' | grep -oP '\(.*?\)'`)
- [ ] All internal links point to existing files
- [ ] CITATION.cff repository-code points to current repository URL
- [ ] CITATION.cff / README repository URL points to current repository
- [ ] ja/ file structure mirrors en/ file structure where applicable
- [ ] README.md achievement table star ratings match [20-proof/README.md](../20-proof/README.md) definitions

## Prohibitions

- [ ] No internal IPs, hostnames, absolute paths, personal information, secrets, or service fingerprints remain (`grep -rnE '(http://[0-9]|:[0-9]{4,5}\b|127\.0\.0\.1|localhost)' --include='*.md' --include='*.html'`)
- [ ] No unqualified superlatives ("world's first" appears at most once, with caveat)
- [ ] No quantitative claims without basis ("X years ahead", "only person who...")
- [ ] amplify/ folder is not in the repository (.gitignore confirmed)
- [ ] No `<INTERNAL_IP>`, `<VM_HOST>`, `<PROJECT_DIR>` placeholders that were not replaced with `[redacted]`

## Execution Observation

- [ ] README.md previewed on GitHub -- all images display correctly
- [ ] 30-adoption/try/ Control OS files tested by pasting into actual AI
- [ ] 10-framework/ step links verified to point to correct files
- [ ] 20-proof/achievements/ image paths all valid
- [ ] SCOPE-MATRIX.md categories match actual file contents

## PASS Criteria

- [ ] A first-time reader can understand "what this does" and "how to try it" within 30 seconds of reading README
- [ ] 30-adoption/try/ files are immediately usable via copy-paste (no additional setup required)
- [ ] Zero broken links and zero broken images
- [ ] All star ratings have evidence-based justification per [20-proof/README.md](../20-proof/README.md)

## Rollback

- [ ] On issue discovery: hotfix branch -> fix -> merge to main
- [ ] On major structural change needed: Issue -> design -> PR -> review -> merge
- [ ] On rollback needed: `git revert` to previous release


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
