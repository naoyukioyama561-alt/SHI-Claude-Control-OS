# Three-Layer Separation Starter Kit

A minimal guide to implementing three-layer role separation in your AI workflow.

---

## The Three Layers

| Layer | Role | Load type | Your implementation |
|-------|------|-----------|-------------------|
| **Supervisor** | Judgment, review, meaning-making | Cognitive (high context) | _________________ |
| **Relay** | Routine monitoring, notification forwarding | Mechanical (zero judgment) | _________________ |
| **Worker** | Implementation, modification, task execution | Operational (task-focused) | _________________ |

## Step 1: Identify Your Current Load Mix

List everything your AI currently does in a single session:

- [ ] Judgment/review tasks: _________________
- [ ] Monitoring/checking tasks: _________________
- [ ] Implementation/execution tasks: _________________

If all three types are happening in one AI session, you have a mixed load problem.

## Step 2: Separate by Type

| Separation | From | To |
|-----------|------|-----|
| Monitoring tasks | Main AI session | Lightweight AI (Ollama, local model) or cron job |
| Review/judgment | Main AI session | Separate session with full context for review only |
| Implementation | Main AI session | Dedicated session focused only on execution |

## Step 3: Define Interfaces

| Interface | What flows | What does NOT flow |
|-----------|-----------|-------------------|
| Supervisor -> Worker | Reviewed plans, approved actions | Raw monitoring data |
| Worker -> Relay | Status updates, completion signals | Judgment requests |
| Relay -> Supervisor | Alerts, anomaly reports | Routine status (unless threshold exceeded) |

## Step 4: Verify Separation

- [ ] No single AI instance handles judgment AND monitoring AND execution
- [ ] The relay layer performs ZERO judgment (pure forwarding)
- [ ] The supervisor is freed from context pressure (reviews only)
- [ ] The worker is freed from rule anxiety (executes only)

## Minimum Viable Separation

If full three-layer separation is too complex for your current setup, start with:

1. **Separate monitoring from execution** -- use a cron job or lightweight AI for monitoring
2. Keep judgment and execution in the same session for now
3. Add supervisor separation when the system is stable

---

> Reference: [10-framework/04-three-layer](../../10-framework/en/04-three-layer.md) | [Achievement No.2: Role Separation](../../20-proof/achievements/en/02-role-separation.md)
