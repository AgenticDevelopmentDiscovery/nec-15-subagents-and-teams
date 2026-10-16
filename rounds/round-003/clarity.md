# Clarity & Exposition — Round 3

**Recommendation:** minor polish
One sentence in §02 introduces a third mode that contradicts the dichotomy the section is building, and a closing claim in §04 lacks a referent; both are single-line fixes.

## Strengths

- The Q&A structure in `03-content.prose.md` is the document's best feature. Each example is self-contained: situation → choice question → answer with a reason → source link. The reader always knows where they are and what they are deciding.
- Definitions in `01-context.prose.md` are crisp and sequenced correctly — subagent before team before orchestrator, each in one sentence. No jargon is used before it is introduced.
- The PR review answer earns its place by explicitly inverting the intuition: "Several perspectives alone do not require an agent team." This is the most instructive single sentence in the document, and it lands at the right moment.
- The failure modes table in `04-conclusion.prose.md` is clean. Each row pairs a named failure with a specific check rather than vague advice.
- The spines are lean. They record decisions, not aspirations, and the open-question lists are short. There is no accumulation of unrealized intentions.

## Weaknesses

- `02-motivation.prose.md` — "Named subagents can also message peers." This sentence appears mid-paragraph under "When a subagent helps" and then vanishes. It implies a third arrangement — subagents that communicate like teammates but are not a team — without defining it, showing it, or resolving how it relates to the delegation/team choice the section is establishing. A reader trying to remember the rule leaves confused about whether peer-messaging subagents are a subcase of delegation, a subcase of teams, or something else entirely.

- `04-conclusion.prose.md` — "Agreement alone does not establish correctness." The referent for "agreement" is unspecified. Agreement between agents? Between the lead and workers? This reads as a warning but the reader cannot act on it because the thing being warned about is unnamed.

- `03-content.prose.md` § "Researching independent modules" — "The main session will compare the reports after all workers finish." The document uses "caller" and "orchestrator" everywhere else for the coordinating agent. "Main session" is a Claude Code implementation term that has not been introduced, and it is not the same concept as "caller." This is a quiet terminology slip that could mislead a reader building a mental model.

- `01-context.prose.md` § "What this tutorial covers" — The roadmap bullet "Common failure modes to avoid" is never flagged again until slide 21 — a gap of roughly 14 slides with no forward reference or reminder. For a 22-slide tutorial this is manageable, but the reader has no signal that failure modes are deferred.

## Actionable

1. `02-motivation.prose.md` § "When a subagent helps" — Delete "Named subagents can also message peers." entirely, or move it after the team/subagent distinction is established with a one-sentence gloss: "Named subagents can message peers without forming a full team — useful when findings need to be shared but ongoing discussion is not required." As written the sentence opens a door the section never walks through. (*Why:* the delegation/team dichotomy is the conceptual load-bearing structure of §02; a third mode dropped without development cracks it.)

2. `04-conclusion.prose.md` § "Failure modes and checks" — Replace "Agreement alone does not establish correctness." with "Agents that converge on a shared wrong assumption are all wrong together — consensus is not a correctness check." (*Why:* the current phrasing has no referent; the replacement makes the specific risk concrete and ties it to the coordination context the table is addressing.)

3. `03-content.prose.md` § "Researching independent modules" — Replace "The main session will compare the reports after all workers finish." with "The caller compares the reports after all workers finish." (*Why:* "main session" is a tool-specific term not introduced in this document; "caller" is the document's own established word for the coordinating agent, and consistency here costs nothing.)

4. `01-context.prose.md` § "What this tutorial covers" — After the "Common failure modes to avoid" bullet, add a parenthetical: "(covered after the examples, slide 21)." (*Why:* the tutorial defers failure modes for 14 slides; without a pointer the reader may expect them sooner, and a brief forward reference resets that expectation at no cost to economy.)
