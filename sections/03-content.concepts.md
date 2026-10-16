# Content — spine

## Purpose

Teach the HOW: the mental model first, then subagents, then teams, then how to choose between them, then what goes wrong — so the reader can apply the pattern to cases this tutorial never showed them. The live demo is the centerpiece; the surrounding slides set it up and land it.

## Claims

- The orchestrator owns the problem; workers own the pieces — the orchestrator never does the work itself
- Worker isolation (own context window, no shared state) is a feature, not a limitation
- Information flows down from orchestrator to worker and back up by default; team messaging adds lateral flow deliberately
- Subagents are ephemeral and focused; teammates are persistent and collaborative — this is the primary distinction
- The subagents vs teams table is the decision tool — token cost and communication model are the two axes that matter most
- Every pitfall listed is a real failure mode, not an invented one — context bleed, over-parallelizing, runaway cost, silent failure, conflicting edits

## Decisions

- Put the mental model before any mechanics — a reader who has the model can predict behavior; one who only has the steps cannot
- Used Claude Code as the concrete example throughout — it is the platform the audience uses, the reference docs are accurate, and it makes the demo continuous with the slides
- Kept code snippets minimal and illustrative — audience coding levels vary; the snippet shows the shape, not a complete implementation
- Dedicated a slide to the live demo — it is the primary hands-on moment and deserves its own heading so it is not buried inside another slide
- Five pitfalls, not more — each one is a real failure mode with a symptom and a cause; padding this list weakens it

## Open questions

- Case study slide is intentionally a context-setter, not a worked example. A second presenter delivers a separate cartoon-style demo on a different platform. The slide's "Watch for:" bullets prime the audience before the demo — they are not a substitute for one. Reviewers should not flag the absence of a worked excerpt here; it belongs to the other presenter's material, not this document.

## Not doing

- Showing how to build a framework from scratch — out of scope per topic.md
- Covering cross-session messaging as a third option — real but would dilute the focus; mention it in conclusion as a next step
- Consensus, voting, or agent negotiation patterns — out of scope per topic.md
