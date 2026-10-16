## Subagents and teams

**Subagent:** an agent another agent invokes for a delegated task.

**Team:** agents with assigned roles collaborating toward a shared goal.

**Orchestrator:** coordinates assignments and checks the combined result. Workers investigate or implement their assigned pieces.

These arrangements overlap. A team can also delegate work to subagents.

## What this tutorial covers

- What **subagents** are and how to use them
- What **teams** are and how they differ from subagents
- When each is the right tool
- Common failure modes to avoid


## One task, several ways to work

**Scenario:** users lose their login session after a recent change.

- One agent can fix a small, reproducible defect
- A subagent can inspect authentication code and return evidence
- A team can investigate competing explanations and exchange findings

We will use Claude Code examples in the following slides.

More agents add setup, duplicated context, and integration work. Their value depends on the task.
