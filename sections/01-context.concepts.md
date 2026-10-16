# Context — spine

## Purpose

Say WHAT subagents and teams are, where the pattern came from, and what this tutorial will deliver — so the reader can hold the concepts before being told why they matter.

## Claims

- A subagent is an agent spawned to handle delegated work independently; it returns a result to its caller
- A team is a structured group of agents with assigned roles coordinating toward a shared goal
- The orchestrator/worker split is the organizing principle of multi-agent systems
- This pattern is not new — it descends directly from distributed systems design; what changed is that the workers now reason
- The same pattern appears across all major agentic frameworks, with different names and mechanics

## Decisions

- Define subagent and team separately before introducing orchestrator/worker — the concepts are easier to hold in sequence than all at once
- Name the frameworks in the definition section, not in their own slide — they are evidence of the pattern's breadth, not the subject
- Keep the history short (one paragraph) — enough to explain why the design is the way it is, not a survey
- Put the capability promise and out-of-scope explicitly in the roadmap slide — this is what the panel checks the conclusion against

## Open questions

- Replaced map-reduce reference with universal analogies (research lab, factory, film crew) — audience is mixed STEM, not all CS

## Not doing

- A taxonomy of all coordination patterns (hierarchical, flat, pipeline, etc.) — too much for context; belongs in 03-content if anywhere
- Framework-specific setup or code — this section is definitions only
