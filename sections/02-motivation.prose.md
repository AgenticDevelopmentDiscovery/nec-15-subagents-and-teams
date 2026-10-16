## Delegation and collaboration

![](figures/delegation-collaboration.png){width=84%}

Delegation keeps a bounded investigation separate. Collaboration lets findings change another agent's work.

## When a subagent helps

- **Clear scope:** bounded inputs and a result the caller can check
- **Specialized work:** different tools or expertise
- **Independent tasks:** workers can run in parallel without ongoing discussion

**How it works:** each worker has its own context and allowed tools, then returns findings to the caller. The caller coordinates and integrates.

Named subagents can also message peers. Simple delegation usually adds less overhead than a team.

## When a team helps

- Agents need to **share findings** and revise each other's work
- **Competing explanations** need discussion and evidence checks
- A feature spans modules with **separate owners** who must coordinate

**How it works:** a lead assigns and integrates work. Teammates have their own context, exchange messages, and use shared tasks when available.

Teams cost more tokens and coordination. Small or tightly dependent tasks can stay with one agent.
