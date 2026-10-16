# Pedagogical Readiness — Round 3

**Recommendation:** minor polish
The tutorial is coherent and structurally sound for its audience, but two gaps — an unexplained figure and an under-prepared question slide — would leave a reader stranded at the moments the material is hardest.

**Audience read against:** Graduate STEM students who have operated single agents but have not designed multi-agent systems; coding backgrounds vary, so code must be followable but is not the primary teaching vehicle.

## Strengths

- The five question-then-answer pattern is well-matched to the declared audience: it activates prior reasoning before confirming, which is appropriate for graduate students who already understand single-agent operation.
- The mixed answer order (subagent, team, team, subagents, subagents) is a genuine pedagogical choice — it prevents the audience from pattern-matching to a rule before they have thought, and the concepts spine documents the intent clearly.
- The failure-modes table in `04-conclusion.prose.md` is concrete and directly actionable; each row pairs a named failure with a named check, which is exactly what a practitioner needs.
- Scope discipline is strong. The tutorial promises five things in `topic.md` and delivers all five without detour. The "not doing" entries in each concepts file are honoured.
- The Claude Code examples are short enough not to overwhelm non-CS readers, and the `login-reviewer` YAML block is the right length to be readable without becoming a setup tutorial.

## Weaknesses

- `sections/02-motivation.prose.md` — The delegation-collaboration figure (`figures/delegation-collaboration.png`) carries the entire conceptual weight of how information flows differently in delegation versus collaboration, yet the only caption is one sentence: "Delegation keeps a bounded investigation separate. Collaboration lets findings change another agent's work." A reader who does not already understand the distinction will stare at the figure without knowing what to look for. This is the hardest conceptual move in the tutorial — the moment a reader must build a mental model — and it receives the least textual scaffolding. A reader without it will reach the question slides unable to apply the distinction.

- `sections/03-content.prose.md` § *A feature across modules* — The answer slide concedes "With a stable contract and independent assignments, subagents could also be sufficient." This is accurate, but it arrives after the audience was just told a team is needed, with no explanation of what changes the calculus. A reader who correctly answered "subagents" on the question slide is now unsure whether they were right or wrong, and why the tutorial chose team. The ambiguity is unresolved, not productively open.

- `sections/03-content.prose.md` § *An unstable login session* (question slide) — The question slide for the login investigation ends with "How should the investigators compare their evidence?" but the situation description establishes that evidence in one area could change what another investigator should test. The question therefore implies the answer before asking for a choice. A reader scanning this will decode "compare evidence → team" before engaging with the reasoning. The question slide for the PR review does this better ("Does having several perspectives require a team?"), and that framing could be applied here.

## Actionable

1. `sections/02-motivation.prose.md` § *Delegation and collaboration* — Add two to three sentences of figure walkthrough before or after the caption: name what is shown in each half of the figure, and state explicitly what the arrow or boundary in each half represents. (*why:* moves from **needs revision** to **minor polish** for the largest conceptual hurdle in the tutorial; no new content required, only narration of what is already drawn)

2. `sections/03-content.prose.md` § *Cross-module feature: an agent team* — Replace the final hedge ("With a stable contract and independent assignments, subagents could also be sufficient") with a conditional that specifies the threshold: e.g., "If the contract were stable before work began, parallel subagents would be sufficient — the team pattern earns its overhead only when contract decisions must propagate mid-task." (*why:* resolves the ambiguity that currently leaves the audience uncertain whether their reasoning was sound; low rewrite cost, high clarity gain)

3. `sections/03-content.prose.md` § *An unstable login session* (question slide) — Reframe the closing question from "How should the investigators compare their evidence?" to something that does not presuppose exchange, e.g., "Do the investigators need to exchange findings while they work, or can they each return a report?" (*why:* removes the answer leak and gives the audience a genuine choice to make, consistent with the pattern the other question slides use)

4. `sections/01-context.prose.md` § *One task, several ways to work* — The sentence "More agents add setup, duplicated context, and integration work" introduces three costs (setup, duplicated context, integration) that are never defined until slide 21's failure table. A reader without that vocabulary will not know what "duplicated context" means when they encounter it for the first time. A parenthetical gloss — "(each agent holds its own copy of project state)" — would cost one line and eliminate a potential early confusion. (*why:* small fix that prevents a terminology stumble before the audience has built the conceptual vocabulary)
