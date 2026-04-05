# Verification Skip Checklist

Use before accepting any AI output as "done."

---

## The 5-Set Inspection

Every completed task must pass all 5 checks. If any check fails, the task is not done.

### 1. Preconditions
- [ ] Were all required inputs available before execution?
- [ ] Were dependencies resolved (files exist, APIs reachable, permissions granted)?
- [ ] Was the scope explicitly defined before starting?

### 2. Prohibitions
- [ ] No prohibited operations were performed (destructive commands, scope expansion, unauthorized writes)?
- [ ] No information was fabricated or hallucinated?
- [ ] No verification steps were skipped?

### 3. Execution Observation
- [ ] Each step was observable (not a black box)?
- [ ] Progress was reported at checkpoints?
- [ ] Deviations from plan were flagged and approved?

### 4. PASS Criteria
- [ ] The output matches the original request (not a reinterpretation)?
- [ ] Evidence exists for each claim made?
- [ ] Edge cases and limitations are explicitly stated?

### 5. Rollback
- [ ] If the output is wrong, can it be reverted?
- [ ] Backup was prepared before modification?
- [ ] Rollback procedure is documented?

## Common Verification Skips (Anti-patterns)

| Pattern | What happens | Prevention |
|---------|-------------|-----------|
| "I think it's done" | No evidence provided | Require explicit PASS criteria evidence |
| Scope reduction | AI quietly narrows the request | Compare output scope against original request |
| Representative-only | AI provides examples instead of exhaustive list | Check for "all/every/complete" in original request |
| Declaration without action | AI says "I will do X" instead of doing X | Require evidence of execution, not intent |

---

> Reference: [10-framework/05-quality-system](../../10-framework/ja/05-quality-system.md)
