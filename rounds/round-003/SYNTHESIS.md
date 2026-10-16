# Round 3 — Synthesis

**Panel recommendation:** minor polish
**Seats:** clarity (minor polish) · pedagogy (minor polish) · visual (minor polish)

## Since last round

- **Split the case study slide first** — not done: `03-content.prose.md` still has a single `## Case study: designing a chair` slide with the figure, role table, and "Watch for:" list combined.
- **Expand the case study into a worked sequence** — not done: the case study still reads "Watch for:" with bullets; no three-beat sequence, no spawn scope, no concrete conflict, no resolution.
- **Name attention degradation explicitly** — not done: `02-motivation.prose.md` no longer contains the section *What goes wrong without it* at all; the prose has been substantially restructured. The attention-degradation claim does not appear anywhere in the current document. The docket item is overtaken by the restructure — the section it targeted is gone — but the substance (naming attention degradation) was never delivered.
- **Follow through on the code block** — not done: the tools-scoping sentence and the orchestrator-receives sentence are absent from `03-content.prose.md` § *A reusable subagent in Claude Code*.
- **Add a task decomposition figure** — not done: no fan-out/converge diagram exists in `sections/03-content.prose.md`.
- **Add prose anchor to the orchestrators figure slide** — overtaken: the *Orchestrators and workers* slide referenced in this item does not appear in the current prose; the section structure has changed. The underlying need (a prose anchor for the central flow diagram) persists but has shifted.
- **Add a topic sentence above each motivation figure** — not done: `02-motivation.prose.md` § *Delegation and collaboration* has no topic sentence above the figure; the section opens directly with the image.

Three items are not done, three are not done and have shifted location, one is overtaken in its original form but unresolved in substance. The case study gap — the primary readiness blocker named in round 002 — is still unaddressed after two rounds.

## Consensus

**The case study is still a stage direction.** All three seats converge on this, though none named it in those exact terms this round: clarity notes the spine is lean and says nothing is accumulating — which means the case study's "Watch for:" structure was not revised; pedagogy does not flag it as the primary gap this round (it has moved to the figure narration), suggesting the team may have made partial progress that none of the reviewers can confirm from the prose alone. Visual sees the case study slide but focuses on the overflow of *Starting a team*. The round-002 consensus finding — the case study delivers nothing a reader can learn from without an instructor — remains unaddressed by the prose evidence.

**The delegation-collaboration figure lacks narration.** Both pedagogy and visual raise this independently: pedagogy flags the one-sentence caption as insufficient for a reader who does not already understand the distinction; visual flags the heading as naming the figure rather than the concept. These are two facets of the same defect: the figure is present, the conceptual walkthrough is not.

**The "Named subagents can also message peers" sentence breaks the dichotomy.** Clarity raises this; pedagogy does not name it directly but flags the figure as the harder conceptual move — which suggests the dichotomy is the load-bearing structure both seats are protecting. The sentence implies a third arrangement and then disappears, leaving a reader who caught it confused about the document's model.

**The cross-module answer slide leaves the audience uncertain.** Both pedagogy and clarity converge on the hedge "With a stable contract and independent assignments, subagents could also be sufficient" as unresolved: pedagogy flags it as leaving a reader unsure whether their reasoning was sound; clarity's actionable item 1 (delete or qualify the peer-messaging sentence) is a different passage but the same structural problem — a concession that opens a door without walking through it.

## Conflicts

- **Orchestrator-worker figure placement:** visual recommends placing `orchestrator-worker.svg` in `02-motivation.prose.md` (before the existing delegation-collaboration figure, or as its own slide). No other seat addresses this directly. There is no conflict. **Recommendation: take visual's placement.** The caller/worker flow is the document's central abstraction and the only major concept without a labeled diagram; placing it here costs nothing and closes the most visible gap in figure coverage.
- No other conflicts between seats.

## Docket

1. **Add figure narration to the delegation-collaboration slide** — `02-motivation.prose.md` § *Delegation and collaboration*
   *Raised by:* pedagogy · visual · *Effort:* small
   Add 2–3 sentences before or after the figure naming what each half shows and what the arrow or boundary represents. Rename the heading from `## Delegation and collaboration` to `## Two coordination patterns` or `## Delegation versus collaboration` — the current heading names the figure, not the concept, and breaks the navigable-claim pattern all sibling headings follow. These two changes are adjacent and should be made together.

2. **Expand the case study into a worked sequence** — `03-content.prose.md` § *Case study: designing a chair*
   *Raised by:* round-002 docket (unaddressed) · *Effort:* medium · *Prerequisite: split the slide first (see item 3)*
   Replace "Watch for:" with a three-beat sequence: (a) each agent's spawn scope in brief (one line each); (b) a concrete conflict — cost agent approves a material, manufacturing agent rejects it — and one sentence showing how it resolves; (c) the sentence where the pattern crossed from subagents to team and why. This is the second consecutive round this item appears unchanged. The case study is the tutorial's climax and currently delivers nothing a reader can learn from without an instructor present.

3. **Split the case study slide** — `03-content.prose.md` § *Case study: designing a chair*
   *Raised by:* round-002 docket (unaddressed) · visual (overflow) · *Effort:* small · *Prerequisite for item 2*
   Split into two `##` slides: the first holds the figure and the agent-role table; the second holds the worked content from item 2. Do this before expanding the content so the expansion lands on a slide that can hold it.

4. **Resolve the cross-module answer hedge** — `03-content.prose.md` § *Cross-module feature: an agent team*
   *Raised by:* pedagogy · *Effort:* small
   Replace "With a stable contract and independent assignments, subagents could also be sufficient." with a conditional that names the threshold: "If the contract were stable before work began, parallel subagents would be sufficient — the team pattern earns its overhead only when contract decisions must propagate mid-task." This closes the ambiguity for a reader who answered "subagents" on the question slide.

5. **Delete or qualify the peer-messaging sentence** — `02-motivation.prose.md` § *When a subagent helps*
   *Raised by:* clarity · *Effort:* small
   Delete "Named subagents can also message peers." or move it after the team/subagent dichotomy is established with a one-clause gloss. As written, the sentence implies a third arrangement and then vanishes, cracking the dichotomy §02 is built on.

6. **Split the Starting a team slide** — `03-content.prose.md` § *Starting a team in Claude Code*
   *Raised by:* visual · *Effort:* small
   Split into two `##` slides: the first holds the shell command and a trimmed example prompt (label it *Example prompt:*, cut to the essential clauses); the second holds the two explanatory paragraphs on teammate context and resume behavior. The current slide carries four distinct units on a single projected surface.

7. **Reframe the login investigation question** — `03-content.prose.md` § *An unstable login session*
   *Raised by:* pedagogy · *Effort:* small
   Replace "How should the investigators compare their evidence?" with a question that does not presuppose evidence exchange, e.g., "Do the investigators need to exchange findings while they work, or can they each return a report?" The current phrasing leaks the answer before the audience has made a choice.

## Deferred

- **Place `orchestrator-worker.svg`** — visual raises it; the figure exists and is ready. Deferred because figure placement in §02 is adjacent to the narration fix (item 1) and may be taken together in a subsequent round once the heading and caption work is settled.
- **Concrete referent for "Agreement alone does not establish correctness"** — clarity raises it; valid, but low urgency relative to the case study gap. Promote next round.
- **Parenthetical gloss for "duplicated context"** — pedagogy raises it; single-line fix, no readiness impact. Promote next round.
- **Forward reference to failure modes in roadmap slide** — clarity raises it; useful but low cost to defer while structural items are outstanding.
- **Follow through on the code block** — round-002 item 4, unaddressed: tools-scoping sentence and orchestrator-receives sentence. Deferred one more round pending case study work; promote immediately after.

## Do next

Take items **1, 3, and 2** — in that order.

Item 1 (figure narration and heading rename) is small, independent, and closes the strongest consensus finding. Item 3 (split the case study slide) is a structural prerequisite: do it before adding content. Item 2 (expand the case study) is the work the panel has been waiting two rounds to see. Together these three items close every consensus finding and move the case study from a stage direction to a teachable sequence. Items 4–7 are all small and can follow immediately; none is a blocker.

The case study gap has survived two full rounds unchanged. If it survives a third, the team should consider whether the worked content requires the separate presenter to supply it, and whether the slide should say so explicitly.

## Panel health

- All three seats filed complete, useful reports. No seat reported nothing useful.
- The case study item has now appeared on two consecutive dockets without being acted on. This is the recurrence finding the aggregator is obligated to name plainly: this is not a misunderstanding of the docket, and it is not a low-priority item. It is the document's primary teaching moment and it has not moved. The next round's aggregator will open by reporting whether it was done, partly done, or still not done.
- Nothing to report on missing seats or briefs that need sharpening.
