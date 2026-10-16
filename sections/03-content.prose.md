## Subagent or team?

**Use a subagent** when the work is focused and only the result matters

**Use a team** when agents need to share findings and challenge each other as work evolves

Start with one agent. Add a subagent when work can be isolated. Add a team when agents need to coordinate on their own.

> Agent teams in Claude Code are **experimental** — disabled by default

## Subagents: the basic case

Spawned for **one focused task** — runs, returns a result, done

\vspace{0.8em}

> **Note:** The examples below use Claude Code. The `Agent` tool is how a session delegates work to a subagent.

```
Agent({
  prompt: "Review src/auth/ for vulnerabilities...",
  tools: ["Read", "Bash"]
})
```

## Subagents: how it works

- **Tools scoped at spawn** — the `tools` list controls what the subagent can do; enforces isolation
- **Own context window** — starts fresh; cannot see the caller's conversation
- **Result returns to caller** — output appears in the spawning agent's context when done
- **Run concurrently** — spawn several in one message; they execute in parallel
- Named subagents can also **message each other** directly via `SendMessage`

## Teams: what they are

One session acts as the **team lead** — spawns teammates, assigns tasks, synthesizes results

Teammates each run in their own context window and do **not** inherit the lead's conversation history

- **Message each other directly** — no routing through the lead required
- **Claim tasks** from a shared task list autonomously
- **Persistent** — stay active and addressable across the session

Enable in Claude Code: `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1`

## Teams: when they're worth the cost

Teams add coordination overhead and use **significantly more tokens** than a single session. They earn their cost when:

- **Debugging competing hypotheses** — teammates test different theories and challenge each other
- **Research and review** — multiple perspectives investigated simultaneously
- **New features across modules** — each teammate owns a separate piece without conflicts
- **Cross-layer work** — frontend, backend, and tests owned by different teammates

For sequential tasks, same-file edits, or simple delegation: subagents or one agent are more effective.

## Subagents vs teams: choosing

| | Subagents | Teams |
|---|---|---|
| **Context** | Own window; result returns to caller | Own window; fully independent |
| **Communication** | Report to caller; named agents can message peers | Message each other directly |
| **Coordination** | Caller manages all work | Self-coordinate via messages + task list |
| **Token cost** | Lower | Significantly higher |
| **Best for** | Focused tasks; only the result matters | Discussion, collaboration, competing views |

*How these compose into larger patterns — fan-out, hierarchical, pipeline — is the next talk.*

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
- How the orchestrator synthesizes competing constraints into one result

## Pitfalls

| Pitfall | What happens | Fix |
|---|---|---|
| **Context bleed** | Overloaded subagent recreates the degradation problem | Give each agent the minimum it needs |
| **Over-parallelizing** | Coordination overhead exceeds the benefit | Start with one agent when in doubt |
| **Runaway token cost** | Each agent is a full context window | Set scope tightly, check in often |
| **Silent failure** | Partial output looks complete | Orchestrator verifies, not just collects |
| **Conflicting edits** | Two agents overwrite each other | Each agent owns distinct files/resources |
