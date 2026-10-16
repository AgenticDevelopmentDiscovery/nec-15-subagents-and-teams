## Why a single agent is not enough

Every agent has three hard limits: a bounded **context window**, **attention that can degrade** as that window fills, and **serial execution**.

![A single agent serialises all tasks through one context window — earlier findings get dropped as it fills.](figures/single-agent-limit.svg){width=100%}

## What goes wrong without it

**Task:** audit a codebase for security, performance, and test coverage gaps

A context window does not just fill — the agent's attention on earlier content can degrade *before* the limit is reached, making the failure silent rather than obvious. The report looks complete. It isn't.

![Without subagents, a single agent drops earlier findings as its context fills. Three subagents each stay focused and report back independently.](figures/failure-mode.svg){width=100%}

## When a subagent helps

Reach for a subagent when the work has:

- A **clear scope** — bounded inputs, defined output, result can be handed back
- **Different tools or expertise** than the main session needs
- **Independence** — it does not need to see the main conversation
- **Parallelism** — multiple subagents can run at the same time

## When a team helps

Reach for a team when:

- Agents need to **share findings** and build on each other's work
- You want **competing perspectives** — agents challenging each other
- Work **evolves collaboratively** rather than by simple delegation
- The task is too complex to decompose cleanly upfront


## When one agent is enough

Stick with one agent when:

- Steps are **sequential** — each depends on the previous
- Work touches **shared state** — coordination overhead exceeds the benefit
- Task **fits in one context window** without degrading
- You need the result **fast** and the coordination cost is not worth it
