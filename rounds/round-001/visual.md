# Visual & Multi-Register Exposition — Round 1

**Recommendation:** needs revision — no figures exist anywhere in the document, and at least two `##` units materially overflow a projected slide.

## Slide overflow
- `01-context.prose.md` § What subagents and teams are — overflows because: too many ideas (defines subagent, team, orchestrator, and workers, then names seven frameworks with descriptions, all in one slide — the framework paragraph alone is a wall of serial clauses that cannot hold at projection scale)
- `02-motivation.prose.md` § When to reach for it — and when not to — overflows because: padded (two full bulleted lists with framing prose and a closing heuristic; the structure announces a two-sided decision framework but delivers enough content for two slides, not one)
- `04-conclusion.prose.md` § What you can do now — *estimated, borderline* (five capability bullets plus two closing paragraphs that recapitulate rather than close; the list alone likely fits, but the paragraphs following it push the unit past what a slide holds cleanly)

## Strengths
- Document register: transitions between all four sections hold cleanly — each section's opening sentence references the preceding idea without restating it, and the arc from context → motivation → content → conclusion is coherent as a read-through
- Presentation register: `03-content.prose.md` § Pitfalls is well-shaped for a slide — five terms, each defined in one sentence, with a symptom and a cause; a reader who missed the preceding slides can still use this one
- Presentation register: `03-content.prose.md` § Live demo is correctly spare — a dedicated heading with three short bullets gives the demonstration room without competing with it; the decision to give it its own `##` is right
- Website register: most headings are concrete enough to orient a reader arriving mid-document from search; "What goes wrong without it" and "When to reach for it — and when not to" in particular are strong entry points that tell the reader what they are getting before they read it

## Weaknesses
- All four prose files — no figures exist anywhere in the document. The central abstraction of this tutorial — the orchestrator/worker topology, the direction of information flow, the context isolation per worker, and the difference in communication structure between subagents and teams — is explained entirely in prose. This is the most significant gap: these are structural and spatial relationships that prose describes but cannot show, and the teaching value is substantially higher with a diagram than without one.
- `01-context.prose.md` — the frameworks paragraph in § What subagents and teams are lists seven frameworks in a single run-on sentence with no visual differentiation. The concepts.md correctly notes these are "evidence of the pattern's breadth, not the subject," but the prose does not execute that framing — each framework receives equal syntactic weight inside a long serial clause. On a slide this renders as a block of names; on the web it is an undifferentiated sentence that gives no grip.
- `03-content.prose.md` — the subagents vs teams table has no figure companion. The table is a useful decision tool, but the communication topology difference it encodes (subagents report up only; teammates message laterally) is exactly the kind of spatial relationship a diagram makes visible that a table cell cannot. The most important row — Communication — is also the most abstract.
- `03-content.prose.md` § The mental model — the heading is vague for web discovery. A reader who lands here from a search result does not know whether this covers cognitive science, a specific framework concept, or something else. The content is about how orchestrators and workers divide responsibility; the heading should say so.

## Actionable
1. `03-content.prose.md` § The mental model — add a diagram here: an "Orchestrator" box at the top; three "Worker" boxes below it, each enclosed in an "own context window" boundary; downward arrows labeled "instructions + scope"; upward arrows labeled "results"; and in a second panel or annotation, dashed horizontal arrows between workers labeled "direct messages (teams only)." This is the single figure that most benefits the document — it makes three claims visible at once: that flow is directional by default, that each worker is isolated, and that teams add lateral channels. Every subsequent section refers back to this structure.
   (*why:* repairs all three registers — in the document it anchors the section that does the heaviest definitional work; on a slide it gives the most important slide a visual to project; on the web the diagram is findable and shareable as a standalone reference)

2. `02-motivation.prose.md` § When to reach for it — and when not to — split into two `##` slides: "When to use multiple agents" and "When one agent is enough." The decision logic is strong; the problem is that a complete two-sided decision framework is too much for one slide. Each half has its own criteria and its own valence — separating them lets each half stand on its own when projected and removes the overflow.
   (*why:* repairs presentation register — the current unit overflows because it is two ideas at slide grain, formatted as one)

3. `01-context.prose.md` § What subagents and teams are — convert the frameworks run-on sentence to a short bulleted list with each framework name bolded and its one distinguishing mechanic as a brief clause. The content does not change; the rendering does. On a slide, the list becomes scannable rather than a block. On the web, each framework becomes a discrete anchor a reader can locate.
   (*why:* repairs presentation register — the serial sentence is structurally a list and should be formatted as one; this also shortens the slide's prose load and reduces its overflow)

4. `03-content.prose.md` § The mental model — rename to "Orchestrators and workers" or "How work gets divided." The current heading names a pedagogical device rather than the concept being taught.
   (*why:* repairs website register — the current heading does not signal its content to a reader arriving from search, and it is the most important conceptual section in the document)
