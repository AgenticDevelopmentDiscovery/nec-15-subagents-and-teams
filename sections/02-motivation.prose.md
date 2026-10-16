## Why a single agent is not enough

Every agent has three hard limits: a bounded **context window**, **attention that degrades** as that window fills, and **serial execution**.

![A single agent serialises all tasks through one context window — earlier findings get dropped as it fills.](figures/single-agent-limit.svg){width=100%}

## What goes wrong without it

**Task:** audit a codebase for security, performance, and test coverage gaps

A context window does not just fill — the agent's attention on earlier content degrades *before* the limit is reached, making the failure silent rather than obvious. The report looks complete. It isn't.

![Without multi-agent coordination, a single agent drops earlier findings as its context fills. Three subagents each stay focused and return complete results.](figures/failure-mode.svg){width=100%}

## When to use multiple agents

Reach for multiple agents when the task has:

- **Independent parts** that can run in parallel
- **Different domains** requiring separate tools or expertise
- **Scale** too large for one context window
- **Independent perspectives** that add value (review, critique, verification)

> *Heuristic: would you hand this to a team of specialists rather than one person?*

## When one agent is enough

Stick with one agent when:

- Steps are **sequential** — each depends on the previous
- Work touches **shared state** — coordination overhead exceeds the benefit
- Task **fits in one context window** without degrading
- You need the result **fast** and coordination cost is not worth it
