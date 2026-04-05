# Security Policy

## Reporting

If you discover a security concern in this repository, please report it via [GitHub's built-in security advisory feature](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS/security/advisories/new). This allows private disclosure so the issue can be addressed before public exposure.

## Scope

No server-side code, backend, or auth flow. Contains client-side static HTML/JS (docs/dashboard.html) for conceptual demonstration only. The security surface is limited to content accuracy and metadata integrity.

## Screenshots

All screenshots are from the author's operational monitoring dashboard. Sidebar navigation has been blacked out in all files. Dashboard content area — including internal module names, operational labels, and UI structure — remains visible to demonstrate that the described architecture exists as a working implementation. These do NOT contain: credentials, API keys, access paths, IP addresses, or information that could enable unauthorized access. Internal UI naming conventions are considered non-sensitive operational artifacts. If you identify information in these images that you believe poses a security risk, please report it via the security advisory feature above.

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
