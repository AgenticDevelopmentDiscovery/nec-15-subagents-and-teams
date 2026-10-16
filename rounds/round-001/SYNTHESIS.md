# Round 1 — Synthesis

**Panel recommendation:** needs revision
**Seats:** clarity (minor polish) · pedagogy (needs revision) · visual (needs revision)

## Since last round

First round — no prior docket.

## Consensus

Two or more seats raised these independently:

- **The live demo slide is a placeholder, not a teaching moment.** Both clarity and pedagogy flag `03-content.prose.md` § *Live demo* as the most critical gap — three bare bullets with no framing of what the audience will watch, what to notice, or what output demonstrates the subagents-vs-teams distinction. Pedagogy names it the primary path from "needs revision" to "minor polish." Clarity names it the main unrealized spine intention. Agreement between two seats about the same passage is the strongest signal in this docket.

- **The framework sentence in `01-context.prose.md` overflows and reads as a catalogue.** Both clarity (§ *What subagents and teams are*, 97-word run-on) and visual (slide overflow finding) flag the seven-framework sentence as too dense for a slide and undifferentiated as prose. The spine's stated intent — "evidence of breadth, not the subject" — is not realized in the current form. Clarity proposes shortening or restructuring; visual proposes a bulleted list. Both routes produce the same result.

- **"Task list" is defined after it first appears.** Both clarity and pedagogy flag `03-content.prose.md` § *Teams: going further* for introducing the term before its definition lands. The comparison table then uses it without re-establishing it. For an audience encountering this vocabulary for the first time, the table functions as a reference — jargon that lives in the table but not in the surrounding prose breaks the reference.

## Conflicts

- **Live demo: how much scaffolding?** Clarity calls for two framing sentences before the bullets. Pedagogy calls for three to five sentences and treating the bullet list as a run-of-show. These are not incompatible — Pedagogy's version is more complete and subsumes Clarity's. **Recommendation: take Pedagogy's framing.** The demo is the primary teaching moment; three to five sentences is not overwriting it.

- None of the remaining items conflict between seats.

## Docket

1. **Scaffold the live demo** — `03-content.prose.md` § *Live demo*
   *Raised by:* clarity · pedagogy · *Effort:* small
   Replace the italic placeholder and three bullets with a 3–5 sentence framing passage: what task the demo will run, what the audience should watch for (specifically: where the subagents' contexts do not appear in the orchestrator's conversation), and what output demonstrates the subagents-vs-teams distinction. Then keep the bullet outline as the run-of-show. The demo is the primary teaching moment and currently has no instructional content; a presenter handed this document has nothing to work from.

2. **Split "When to reach for it" into two slides** — `02-motivation.prose.md` § *When to reach for it — and when not to*
   *Raised by:* visual · *Effort:* small
   Add a `##` heading to create two slides: "When to use multiple agents" and "When one agent is enough." The decision logic is strong; the problem is that a complete two-sided framework overflows one slide. Each half has its own criteria and its own valence — separating them lets each stand alone when projected and removes the overflow without cutting any content.

3. **Convert the frameworks sentence to a bulleted list** — `01-context.prose.md` § *What subagents and teams are*
   *Raised by:* clarity · visual · *Effort:* small
   Bold each framework name and give it its one distinguishing mechanic as a brief clause. The content does not change; the rendering does. On a slide, the list becomes scannable. On the web, each framework becomes a discrete anchor. The spine correctly identifies these as "evidence of breadth, not the subject" — the list format executes that framing; the current sentence does not.

4. **Move the task list definition earlier and bold it at first use** — `03-content.prose.md` § *Teams: going further*
   *Raised by:* clarity · pedagogy · *Effort:* small
   The term currently appears inside a subordinate clause after an em-dash, after the reader has already seen "share a task list" in the spawn example without a definition. Move the definition one paragraph earlier, bold **task list** at first use, and add a brief back-reference in the comparison table's "Coordination" row for Teams.

5. **Add one grounding sentence before the first code snippet** — `03-content.prose.md` § *Subagents: the basic case*
   *Raised by:* pedagogy · *Effort:* small
   One sentence establishing that the examples run in Claude Code and that the `Agent` tool is how Claude Code's orchestrator delegates work. The declared audience includes non-CS STEM readers; without this sentence the snippet appears as unexplained syntax. One sentence closes the gap for the full audience range without adding load for readers already familiar.

6. **Add a worked decomposition for the "design" capability** — `03-content.prose.md` § *The mental model*
   *Raised by:* pedagogy · *Effort:* medium
   The document promises "Design a multi-agent system by decomposing a complex task into roles and workstreams." The mental model describes structure; it does not supply a method. Add 4–6 sentences showing the reasoning that produces a role split: take the codebase-audit example already in the reader's head and surface the questions the orchestrator asks to produce the security / performance / coverage partition. The capability is restated as delivered in the conclusion, but the prose does not earn it.

7. **Add the orchestrator/worker diagram** — `03-content.prose.md` § *The mental model*
   *Raised by:* visual · *Effort:* medium
   A single diagram: "Orchestrator" box at top; three "Worker" boxes below, each enclosed in an "own context window" boundary; downward arrows labeled "instructions + scope"; upward arrows labeled "results"; a second annotation showing dashed horizontal arrows between workers labeled "direct messages (teams only)." This makes three claims visible at once: flow is directional by default, each worker is isolated, and teams add lateral channels. Repairs all three registers — document, slides, and web. This is the single figure that most benefits the document.

## Deferred

- **Rename "The mental model" heading** (`03-content.prose.md`) — raised by visual; valid finding for web discovery, but low readiness impact compared to the docket items. Promote next round if the heading survives.
- **Forward-reference crossover duplication** (`02-motivation.prose.md` and `04-conclusion.prose.md`) — raised by clarity; the near-verbatim repetition is real but does not break the tutorial for the declared audience. Address after higher-priority items.

## Do next

Take items **1, 2, and 3** this round — in that order.

Item 1 (live demo scaffolding) is the single change that most directly moves the panel recommendation. Items 2 and 3 are small, remove confirmed overflow, and close the consensus findings. Together they constitute less than an hour of editing and buy a full tier of readiness. Items 4 and 5 are also small and can follow immediately; 6 and 7 require more effort and should wait until the fast wins are in and the next round confirms the tier has moved.

## Panel health

- Nothing to report. All three seats filed. The clarity reviewer upgraded the live demo finding from "weakness" to "unrealized spine intention" rather than flagging the spine itself — this is accurate and avoids double-counting. The pedagogy reviewer correctly identified the "design" capability gap that neither other seat named; this is a genuine pedagogical finding and belongs on the docket. Visual's "needs revision" driven primarily by figure absence is a legitimate finding — the document is entirely prose for spatial, structural concepts, and the diagram gap is real.
