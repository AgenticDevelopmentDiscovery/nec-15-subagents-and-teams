# Topic

## In one sentence

Subagents and teams let you decompose complex problems across multiple independent agents, each with its own context, tools, and role, working in concert toward a shared goal.

## What it is

A subagent handles a delegated assignment and returns a result to its caller. A team coordinates agents with assigned roles toward a shared goal. The orchestrator coordinates and checks the combined result; workers handle the assigned pieces. These arrangements overlap. Claude Code supplies the concrete examples, including reusable subagent definitions and experimental, session-scoped agent teams.

## Why it belongs in this course

In a course about building agentic frameworks, subagents and teams are the unit of composition. A single agent is a starting point; a framework is what you get when you know how to coordinate many. Every agentic pipeline — whether it processes documents, writes code, or evolves a document through critique — eventually needs to delegate, specialize, and parallelize. Subagents and teams are how that happens. Understanding them is what bridges the gap between "I can prompt an agent" and "I can design a system of agents that does real work." They also appear directly in evolutionary AI frameworks: a critique round, for example, is a team of independent reviewers running in parallel, reconciled by an orchestrator — which is exactly the pattern this course is built on.

## What the reader will be able to do

- Explain what subagents and teams are and how they relate to each other
- Identify when a task calls for a single agent versus a multi-agent approach
- Design a multi-agent system by decomposing a complex task into roles and workstreams
- Spawn and coordinate subagents within an agentic framework
- Recognize and avoid common failure modes in multi-agent coordination

## Scope

**In scope**

- What subagents and teams are and how they relate
- The orchestrator/worker pattern and how coordination works
- When to use a multi-agent approach vs a single agent
- Common failure modes in multi-agent systems
- A live demonstration of subagents and teams in action

**Out of scope**

- Building a multi-agent framework from scratch — time constraint; the demo carries the hands-on component
- Deep framework internals — Claude Code provides short, usable configuration examples rather than a full setup tutorial
- Advanced coordination patterns such as consensus mechanisms, voting, or agent negotiation — beyond a 15-18 minute tutorial
- Agent memory and state persistence across sessions — a separate topic that deserves its own tutorial
- Security and trust between agents — important but out of scope here

## Shape

- Slides 1–7: title, Codex definitions, tutorial roadmap, login scenario, delegation picture, when a subagent helps, when a team helps
- Mechanics and comparison are consolidated into slides 6–7 to keep the first example on slide 8
- Slides 8–17: five audience questions, each immediately followed by its answer and approach
- The answer order is deliberately mixed: subagent, team, team, subagents, subagents
- Slides 18–19: reusable Claude Code subagent definition and team startup
- Slide 20: chair-design case study as the separate presenter's demo handoff
- Slide 21: failure modes and checks
- Slide 22: references
- No history slide, appendix, or repeated capability checklist

## Open questions

- When does a task genuinely require multiple agents, and when is a single agent sufficient? Is there a reliable heuristic, or does it always depend on context?
- Do tasks that always need multi-agent solutions share common patterns — and similarly, do tasks that never benefit from it share patterns? Can those be named and taught?
- How do you balance framework complexity, token cost, and time-to-solution? A multi-agent system that takes 10x the tokens to do what one agent could do in a single pass is a regression, not progress.
- Where is the crossover point — the moment a task tips from "one agent with good prompting" to "needs delegation to be tractable"?
