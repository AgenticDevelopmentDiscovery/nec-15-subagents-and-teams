# Topic

## In one sentence

Subagents and teams let you decompose complex problems across multiple independent agents, each with its own context, tools, and role, working in concert toward a shared goal.

## What it is

A subagent is an agent that is spawned by another agent to handle a delegated piece of work. It operates independently — with its own context, tools, and scope — and returns its result to the agent that created it. A team is a structured group of agents, each with an assigned role, that coordinate to solve a problem no single agent could handle alone. The agent that coordinates the others is called an orchestrator; the agents that carry out the work are workers. This pattern appears across many modern agentic frameworks — CrewAI organizes agents into crews with defined roles and goals, AutoGen lets agents converse and delegate tasks to one another, LangGraph models agent coordination as a graph of nodes and edges, OpenAI Swarm focuses on lightweight handoffs between agents, Microsoft Semantic Kernel provides orchestration across AI services and plugins, AWS multi-agent patterns enable agent collaboration inside cloud-native pipelines, and Claude Code lets an orchestrating session spawn subagents for parallel tasks while its teams feature defines named persistent collaborators available across sessions.

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
- Deep dives into any specific framework — CrewAI, AutoGen, LangGraph, Claude Code are referenced as examples, not taught
- Advanced coordination patterns such as consensus mechanisms, voting, or agent negotiation — beyond a 15-18 minute tutorial
- Agent memory and state persistence across sessions — a separate topic that deserves its own tutorial
- Security and trust between agents — important but out of scope here

## Shape

- **01-context** carries the definitions — what a subagent is, what a team is, the orchestrator/worker relationship, and a brief origin of where these patterns came from. Light and fast, sets up everything after it.
- **02-motivation** makes the case — why a single agent is not enough, what breaks without multi-agent coordination, and when to reach for it vs when not to. Concrete failure examples do the work here.
- **03-content** carries the weight — the mental model first, then the coordination patterns, then pitfalls. The live demonstration lands here and should be the centerpiece. This section will need the most `##` units.
- **04-conclusion** closes the loop — what the reader can now do, pointers to specific frameworks for going deeper, and what is still unsettled in this space.
- The live demo sits inside `03-content` and is the primary hands-on moment. Keep the surrounding slides tight so the demo has room.

## Open questions

- When does a task genuinely require multiple agents, and when is a single agent sufficient? Is there a reliable heuristic, or does it always depend on context?
- Do tasks that always need multi-agent solutions share common patterns — and similarly, do tasks that never benefit from it share patterns? Can those be named and taught?
- How do you balance framework complexity, token cost, and time-to-solution? A multi-agent system that takes 10x the tokens to do what one agent could do in a single pass is a regression, not progress.
- Where is the crossover point — the moment a task tips from "one agent with good prompting" to "needs delegation to be tractable"?
