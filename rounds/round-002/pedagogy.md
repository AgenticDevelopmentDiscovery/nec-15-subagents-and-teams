# Pedagogical Readiness — Round 2

**Recommendation:** needs revision
The document teaches the *what* and *when* convincingly but the case study — the one place where a reader should watch decomposition happen — is a prompt list, not a worked demonstration.

**Audience read against:** Graduate STEM students who have run single agents and understand how one operates; they have not coordinated multiple agents and come with varied coding backgrounds.

---

## Strengths

- **Motivation lands.** The codebase-audit failure mode is concrete, domain-familiar to the audience, and the two-column decision heuristic gives them a portable rule they can apply without memorizing a taxonomy.
- **The comparison table works.** Subagents vs. teams across five dimensions is the clearest moment of the document; a reader finishes that table knowing which tool fits their situation.
- **Scope discipline is real.** Out-of-scope items (consensus, memory, security) never leak in. The tutorial promises five capabilities and the conclusion checks off five. That alignment is rare and genuinely valuable.
- **Pacing is reasonable across 01–02.** Context and motivation each carry one core idea and move on. No section is overloaded.

---

## Weaknesses

- **`03-content.prose.md` § "Case study: designing a chair with three agents" — the case study is an outline, not a worked example.** The audience is told to "watch for" three things — scope isolation, a conflict forcing direct coordination, and the tipping point from subagents to team — but none of those three things is shown. There is no prompt, no agent output, no moment of conflict, no resolution. The reader is handed a table of agent names and left to imagine the story. This is the section that should demonstrate decomposition in action; instead it asserts that decomposition is interesting. For readers who have never coordinated multiple agents, this is the gap that matters most: they leave unable to *do* what the tutorial promised to show them.

- **`03-content.prose.md` § "Teams: going further" — the task list is introduced without grounding.** "A shared queue of work items that teammates claim, complete, and hand off" appears in one sentence with no example of what a queue entry looks like, who populates it, or how claiming works mechanically. The code snippet for subagents (the `Agent({...})` block) gives teams nothing equivalent. A reader who understands subagents from the snippet is left with a verbal description of teams and no anchor.

- **`02-motivation.prose.md` § "What goes wrong without it" — the figure caption carries more explanatory weight than the prose.** The caption describes what happens ("drops earlier findings as context fills"), but the prose section heading and body do not explain *why* context fills or *how* filling causes degradation. The motivation section's spine claims "three hard limits: context window size, attention degradation, and serial execution," but only context window size appears in the prose. Attention degradation — the subtlest and most important of the three for this audience — is never named. A reader who already knows this will nod; a reader who needs it explained will leave without it.

---

## Actionable

1. `03-content.prose.md` § "Case study: designing a chair with three agents" — expand into a three-beat worked sequence: (a) show each agent's spawn prompt (abbreviated, not exhaustive) with its scope boundary explicit; (b) narrate a concrete conflict — cost agent approves a material, manufacturing agent rejects it — and show how the orchestrator or direct message resolves it; (c) identify the sentence where the pattern crossed from subagents to team and why. The chair domain requires no technical background and keeps the example framework-agnostic. *(Why: converts the document's most important "watch for" into a "here is what it looked like" — directly closes the gap between the capability promised and what the reader can actually do after reading.)*

2. `03-content.prose.md` § "Teams: going further" — add one concrete task-list entry and a two-sentence sketch of the claim/complete/hand-off cycle. It does not need to be code; a plain-English queue item ("Task: audit `src/auth/` for SQL injection; Owner: security-agent; Status: claimed") followed by a sentence on how a teammate marks it done and the next teammate picks up is enough. *(Why: gives the teams section the same concrete anchor the subagents section has; the gap between the two currently makes teams feel speculative.)*

3. `02-motivation.prose.md` § "What goes wrong without it" — add two sentences naming attention degradation explicitly: that a context window does not merely fill but that performance on early content degrades as the window lengthens, even before the limit is reached. The spine promises this claim; the prose does not deliver it. *(Why: low-effort rewrite of one paragraph; moves motivation from "the problem is size" to "the problem is size *and* quality" — a more accurate and more motivating picture for an audience that will hit degradation before they hit the hard limit.)*

4. `03-content.prose.md` § "Subagents: the basic case" — add one sentence after the code block noting what the orchestrator does with the return value. The snippet shows how to spawn; it does not show how the result comes back or what form it takes. The audience can follow the spawn but cannot follow the full cycle. *(Why: small addition that closes a loop the current prose opens and leaves dangling.)*
