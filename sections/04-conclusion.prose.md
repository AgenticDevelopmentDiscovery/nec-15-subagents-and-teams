## Benefits and limitations

| | Subagents | Agent teams |
|---|---|---|
| **Benefits** | Focused context; restricted tools | Direct messaging; shared tasks |
| **Limitations** | Caller synthesizes; starts without caller history | Experimental/off by default; in-process resume and task-status issues |
| **Trade-offs** | Lower relative token use; useful for focused work; review still required | Higher token use; may reduce elapsed time when work is independent; no quality guarantee |

## References: sources

**Claude Code documentation**, accessed October 16, 2026

- [Create custom subagents](https://code.claude.com/docs/en/sub-agents)
- [Orchestrate agent teams](https://code.claude.com/docs/en/agent-teams)
- [Manage costs effectively](https://code.claude.com/docs/en/costs#agent-team-token-costs)

## References: evidence notes

- **Subagents:** isolated context; focused delegation; restricted tools; caller synthesis; fresh context; and lower-cost model routing are documented in *Create custom subagents*.
- **Agent teams:** direct messaging, shared tasks, parallel review, competing hypotheses, coordination overhead, experimental status, and resumption/task-status limitations are documented in *Orchestrate agent teams*.
- **Token cost:** team usage scales with teammate count and runtime; the cost guide reports approximately 7x more tokens than standard sessions in plan mode.

The documentation describes tendencies and suitable use cases, not guarantees that teams are faster, cheaper, or more accurate. The quality comparison is therefore a design inference: teams can add coverage and challenge, while coordination can also add failure points.
