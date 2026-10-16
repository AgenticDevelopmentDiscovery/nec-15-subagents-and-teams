## Orchestrators and workers

![Subagents report results up to the orchestrator only. In teams, workers also send direct messages to each other.](figures/orchestrator-worker.svg){width=100%}

Two topologies: **subagents** (results flow up only) and **teams** (workers also message each other directly). Start with subagents — see § *Subagents vs teams: choosing* for when to reach for teams.

## How to decompose a task

Ask four questions:

1. **What are the independent domains?** — What expertise does each piece need?
2. **Can the pieces run in parallel?** — If yes, each piece is a candidate worker
3. **What is each agent's scope boundary?** — What does it see, and what does it return?
4. **Where will constraints clash?** — That conflict is where the orchestrator earns its role

![A complex task fans out to parallel workers, each in their own context, then converges back at the orchestrator for synthesis.](figures/task-decomposition.svg){width=95%}

## Subagents: the basic case

Spawned for **one focused task** — runs, returns a result, done

> **Note:** The examples below use Claude Code — the platform used in this course. The `Agent` tool is how an orchestrating session delegates work to a subagent.

```
Agent({
  prompt: "Review src/auth/ for vulnerabilities...",
  tools: ["Read", "Bash"]
})
```

- The `tools` list scopes what the subagent can use — this is how isolation is enforced at spawn
- When finished, the subagent returns its result as text back to the orchestrator's context
- Gets its own context window; cannot see the orchestrator's conversation
- Can run **concurrently** — spawn several at once for parallel work

## Teams: going further

A **task list** is a shared queue of work items that teammates claim, complete, and hand off — without waiting for the orchestrator to assign each one.

Teammates are **persistent** and can **message each other directly**

- Claim work from the shared **task list** autonomously
- A security teammate can message the test coverage teammate directly
- The orchestrator does not need to be in every exchange

## Subagents vs teams: choosing

| | Subagents | Teams |
|---|---|---|
| **Communication** | Report to caller only | Message each other directly |
| **Coordination** | Orchestrator manages all | Self-coordinate |
| **Persistence** | One task, then done | Named, persistent |
| **Token cost** | Lower | Higher |
| **Best for** | Parallel focused tasks | Collaborative, iterative work |

## Case study: designing a chair with three agents

**Task:** find an optimal chair design satisfying three competing constraints

| Agent | Constraint |
|---|---|
| Cost agent | Material and production budget |
| Manufacturing agent | Fabrication feasibility at scale |
| Style agent | Aesthetics and user experience |

Watch for:
- How each agent's scope is isolated at spawn
- Where a conflict forces agents to coordinate directly
- The moment the pattern tips from subagents → team

## Pitfalls

| Pitfall | What happens | Fix |
|---|---|---|
| **Context bleed** | Overloaded subagent recreates the degradation problem | Give each agent the minimum it needs |
| **Over-parallelizing** | Coordination overhead exceeds the benefit | Start with one agent when in doubt |
| **Runaway token cost** | Each agent is a full context window | Set scope tightly, check in often |
| **Silent failure** | Partial output looks complete | Orchestrator verifies, not just collects |
| **Conflicting edits** | Two agents overwrite each other | Each agent owns distinct files/resources |
