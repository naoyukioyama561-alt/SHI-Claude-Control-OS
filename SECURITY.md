# Security Policy

## Reporting

If you discover a security concern in this repository, please report it via [GitHub's built-in security advisory feature](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS/security/advisories/new). This allows private disclosure so the issue can be addressed before public exposure.

## Scope

No server-side code, backend, or auth flow. Contains client-side static HTML/JS (docs/dashboard.html) for conceptual demonstration only. The security surface is limited to content accuracy and metadata integrity.

## Screenshots and Visual Evidence

All original operational screenshots have been removed from the public repository and replaced with SVG conceptual diagrams. This ensures no internal naming conventions, operational labels, or environment-specific information is exposed. The interactive demo (demo/en/ and demo/jp/) provides a safe, static representation of the monitoring system's interface and functionality. If you identify information in any file that you believe poses a security risk, please report it via the security advisory feature above.

## Redacted Items

Certain internal names, service identifiers, and implementation details are redacted throughout the repository. The rationale for each category of redaction is documented in [PROVE-IT.md](PROVE-IT.md).

## Adversarial Considerations

This methodology could theoretically be misused to:
- Create overly restrictive AI systems that suppress useful capabilities
- Use the monitoring framework to surveil human operators rather than AI behavior
- Apply the failure mode taxonomy to identify and exploit weaknesses in others' AI systems

We address these risks through:
- Open publication of the methodology (anyone can audit the approach)
- Clear scope limitation (this is for AI governance, not human surveillance)
- PROVE-IT.md verification protocol (all claims are challengeable)

[日本語版](SECURITY-ja.md)
