# Round 2 — Synthesis

**Panel recommendation:** needs revision
**Seats:** clarity (minor polish) · pedagogy (needs revision) · visual (minor polish)

## Since last round

All seven items from the round-001 docket were acted on:

- **Scaffold the live demo** — done: chair case study with three agents now occupies the demo slot
- **Split "when to reach for it" into two slides** — done: two separate `##` units in 02-motivation
- **Convert frameworks sentence to list** — done: frameworks stripped from slide prose in the rewrite; no longer a run-on sentence
- **Task list definition** — done: defined and bolded before first use in § Teams
- **Claude Code grounding sentence** — done: italicised platform note before code block
- **Worked decomposition** — done: "How to decompose a task" slide with four questions and a codebase example
- **Orchestrator/worker diagram** — done: `orchestrator-worker.svg` live in § Orchestrators and workers

Round-001 docket is fully closed. The document has moved significantly. One item carries forward as a new and harder finding: the case study is still not a worked example.

## Consensus

**The case study is a stage direction, not a case study.** Both clarity and pedagogy raised this independently and in the same terms. The section shows an agent table and three "Watch for:" bullets — but no prompt, no output, no conflict, no resolution. The visual reviewer flags it as overflowing a slide; pedagogy calls it the primary gap between what was promised and what was delivered. This is the strongest signal in this docket: the section positioned as the tutorial's climax delivers nothing a reader can learn from without an instructor in the room.

**Attention degradation is named in the spine but absent from the prose.** Both clarity and pedagogy flag `02-motivation.prose.md` independently: the spine lists three hard limits (context window size, attention degradation, serial execution), but only context window size reaches the prose. Attention degradation — the subtler failure, the one that makes output look complete when it is not — is the mechanism behind "silent failure" in the pitfalls table. Without naming it in motivation, the pitfall entry cannot land as a surprise.

**The code block needs follow-through on two fronts.** Clarity flags that the `tools` array has no explanation of what tool scoping means for a subagent's isolation. Pedagogy flags that the snippet shows spawning but not what the orchestrator does with the return value. These are two sentences, both adjacent to the same code block.

## Conflicts

- **Case study depth:** clarity calls for a "minimal resolved excerpt" (two or three turns); pedagogy calls for a "three-beat worked sequence." These are compatible, not conflicting — pedagogy's version is more complete and subsumes clarity's. **Recommendation: take pedagogy's framing.** The case study is the most important teaching moment and deserves the more complete treatment.
- No other conflicts between seats.

## Docket

1. **Split the case study slide first** — `03-content.prose.md` § *Case study: designing a chair with three agents*
   *Raised by:* visual · *Effort:* small · *Prerequisite for item 2*
   The current slide holds a task sentence, a 3-row table, and a 3-item list — visual estimates 14–16 projected lines on a 10–12 line slide. Split into two `##` slides: the first holds the agent-constraint table, the second holds the worked content from item 2. Do this before expanding the content so the expansion lands on the right slide.

2. **Expand the case study into a worked sequence** — `03-content.prose.md` § *Case study* (second slide after split)
   *Raised by:* clarity · pedagogy · *Effort:* medium
   Replace "Watch for:" with a three-beat sequence: (a) each agent's spawn scope in brief (one line each); (b) a concrete conflict — cost agent approves a material, manufacturing agent rejects it — and one sentence showing how it resolves; (c) the sentence where the pattern crossed from subagents to team and why. The chair domain requires no technical background and keeps the example framework-agnostic.

3. **Name attention degradation explicitly** — `02-motivation.prose.md` § *What goes wrong without it*
   *Raised by:* clarity · pedagogy · *Effort:* small
   Add two sentences before or after the figure: (a) a context window does not merely fill — performance on early content degrades as the window lengthens, even before the limit is reached; (b) this is what makes the failure silent. The spine promises this claim; the prose does not deliver it. It also primes "silent failure" in the pitfalls table to land as a recognized pattern rather than a surprise warning.

4. **Follow through on the code block** — `03-content.prose.md` § *Subagents: the basic case*
   *Raised by:* clarity · pedagogy · *Effort:* small
   Two additions after the code block: (a) one sentence explaining that the `tools` list scopes what the subagent can use — enforcing its isolation; (b) one sentence on what the orchestrator receives when the subagent finishes. These are adjacent and can be written as consecutive sentences. Together they close the spawn→result cycle the snippet opens.

5. **Add a task decomposition figure** — `03-content.prose.md` § *How to decompose a task*
   *Raised by:* visual · *Effort:* medium
   A diagram showing the fan-out/parallel/converge structure: one task node at top, arrows fanning to labelled worker nodes, arrows converging back to an Orchestrator node. Place it after the four questions and before the example line. This is the central operational pattern of the tutorial and currently the only major abstraction without a visual.

6. **Add prose anchor to the orchestrators figure slide** — `03-content.prose.md` § *Orchestrators and workers*
   *Raised by:* visual · *Effort:* small
   One or two sentences after the figure: name the two topologies (subagents vs. teams), state which to reach for first, and point forward to § *Subagents vs teams: choosing*. Under 40 words so the slide survives.

7. **Add a topic sentence above each motivation figure** — `02-motivation.prose.md` § *Why a single agent is not enough* and § *What goes wrong without it*
   *Raised by:* visual · *Effort:* small
   One sentence above each figure in the document register — not a caption, prose. Gives a PDF reader something to land on and tells a slide attendee what they are about to see. The slide register is unaffected: the sentence becomes the visible label above the figure.

## Deferred

- **Conclusion closing sentence** (`04-conclusion.prose.md`) — clarity raises it; valid but low urgency relative to the case study gap. Promote next round.
- **Analogy section — cut two, unpack one** (`01-context.prose.md`) — clarity raises it; stylistic improvement, no readiness impact. Promote if the section survives round-003 review unchanged.
- **Teams task list concrete anchor** (`03-content.prose.md` § Teams) — pedagogy raises it; a plain-English queue entry would help, but it is secondary to the case study expansion. Promote next round.
- **Platform note format** (`03-content.prose.md`) — visual raises it; the italic platform note does not survive projection. Convert to a `> **Note:**` blockquote.

## Do next

Take items **1, 2, and 3** this round — in that order.

Item 1 is a prerequisite: split the case study slide before adding content to it. Item 2 is the primary gap: the case study delivers nothing to a reader without an instructor present, and closing it is the direct path from "needs revision" to "minor polish." Item 3 is two sentences that pay off a spine claim the prose has been carrying without delivering since round one. Together, these three items close the consensus findings and move the panel recommendation. Items 4–7 are all small and can follow immediately; item 5 (decomposition figure) takes more effort and should wait until the case study is settled.

## Panel health

- All three seats filed complete reports. No seat reported nothing useful.
- The pedagogy reviewer correctly identified the case study gap as the primary readiness blocker; clarity and visual corroborate it from different angles. The agreement is genuine — three independent reads of the same document arrived at the same failure.
- Nothing to report on missing seats or briefs that need sharpening.
