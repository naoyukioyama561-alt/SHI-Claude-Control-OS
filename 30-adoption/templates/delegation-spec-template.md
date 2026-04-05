# Delegation Specification Template

Use this template every time you delegate a task to a sub-agent or helper AI.

---

## 12 Mandatory Items

Fill in all 12 items before delegating. Missing items lead to scope creep, permission violations, and quality degradation.

| # | Item | Value |
|---|------|-------|
| 1 | **Task name** | |
| 2 | **Delegation level** | D1 (Assistant AI) / D2 (MCP) / D3 (Full pipeline) |
| 3 | **Scope** | (Exactly what to do -- no more, no less) |
| 4 | **Scope exclusions** | (Explicitly what NOT to do) |
| 5 | **Preconditions** | (What must be true before starting) |
| 6 | **Permissions** | (Read/Write/Execute -- which files/APIs/commands) |
| 7 | **Permission denials** | (Explicitly what is NOT permitted) |
| 8 | **Expected output** | (Format, content, location) |
| 9 | **Quality criteria** | (How to judge if the output is acceptable) |
| 10 | **Timeout** | (Maximum duration before escalation) |
| 11 | **Rollback condition** | (When to abort and how to undo) |
| 12 | **Report format** | (What to report back and in what structure) |

## Delegation Level Guide

| Level | Use when... | Example |
|-------|------------|---------|
| **D1** | Routine monitoring, simple queries | Log scanning, health checks |
| **D2** | Structured tool use with defined interfaces | MCP-based file operations |
| **D3** | End-to-end task execution | Full pipeline via API Gateway |

## Post-Delegation Verification

- [ ] Output matches expected output specification
- [ ] No permission violations occurred
- [ ] Scope was not expanded beyond specification
- [ ] Quality criteria were met
- [ ] Duration was within timeout

---

> Reference: [Achievement No.11: Delegation Optimization](../../20-proof/achievements/ja/11-delegation-optimization.md)
