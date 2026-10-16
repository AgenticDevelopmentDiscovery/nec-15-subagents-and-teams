# Motivation — spine

## Purpose

Say WHY the topic matters for agentic development — the hard limits of a single agent, what concretely breaks without multi-agent coordination, and where the line is between "one agent is fine" and "you need more."

## Claims

- Every agent has three hard limits: context window size, attention degradation, and serial execution
- These limits do not matter for small tasks; they become walls for large, complex, or parallel work
- The unit of intelligence is one context window — when the problem is bigger, you need more than one agent
- The codebase audit failure is concrete and silent — the agent produces output that looks complete but is degraded
- Multi-agent coordination adds real overhead; the question is always whether the benefit justifies the cost
- The "team of specialists" heuristic is the most portable decision rule for a mixed audience

## Decisions

- Used codebase audit as the failure example — it is concrete, recognizable across CS and engineering backgrounds, and the failure mode (silent degradation) is genuinely surprising and worth showing
- Framed "when to reach for it" as a two-column decision rather than a rule — because the open question from topic.md (where is the crossover?) does not have a clean answer; the heuristic is more honest than a threshold
- Kept token cost in the "when not to" list — this is one of our stated open questions and the audience should hear it named honestly rather than have it smoothed over

## Open questions

- None — both candidate questions resolved: one example is enough, and context window size does not need a number here

## Not doing

- A formula or scoring rubric for the make-or-break decision — does not exist reliably; naming it as an open question is more honest
- Benchmarks or token cost numbers — too framework-specific and likely to go stale
