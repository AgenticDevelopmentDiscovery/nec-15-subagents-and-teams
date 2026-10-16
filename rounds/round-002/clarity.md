# Clarity & Exposition — Round 2

**Recommendation:** minor polish
The through-line is coherent and the prose is lean, but two structural gaps weaken the argument — the context window limit is asserted but never shown to the reader, and the chair case study is staged rather than executed, leaving the most concrete teaching moment empty.

---

## Strengths

- **01-context.prose.md — roadmap bullet list.** The five-item "What this tutorial covers" list maps exactly onto the four prose sections plus the conclusion capabilities. A reader can hold this as a true table of contents. The symmetry with `04-conclusion.prose.md` is clean.
- **02-motivation.prose.md — the when/when-not two-column structure.** Framing both sides of the decision in matched bullets, with the heuristic as a coda, is the right move for a mixed audience. It earns its place because it answers the implicit "so do I always need this?" before the reader asks.
- **03-content.prose.md — pitfalls table.** Five rows, each with a cause and a fix. "Silent failure" and "conflicting edits" are the non-obvious entries; naming them explicitly is more useful than another generic warning about coordination overhead.
- **Spine → prose fidelity.** Every claim listed in the concept spines lands in the corresponding prose section. There is no gap between what was planned and what shipped — a clean bill of health for the planning layer.

---

## Weaknesses

- **`02-motivation.prose.md` — "attention degradation" is claimed but never shown.** The spine lists three hard limits: context window size, attention degradation, and serial execution. The prose collapses all three into one figure caption: *"a single agent drops earlier findings as its context fills."* Attention degradation (the model attending poorly to middle-context material even before the window is full) is the subtler and more alarming limit, and it is the one that makes the failure *silent* rather than obvious. Dropping it from the prose leaves the reader with only "it runs out of room," which undersells the actual danger.

- **`03-content.prose.md` § "Case study" — the case study is a stage direction, not a case study.** Three "Watch for:" bullets describe what the reader *will observe* in a live demo, but no demo content is present in the document. As written, this section delivers nothing to a reader who is not in the room — it reads as a placeholder. If the demo is the vehicle for the most complex content (conflict resolution, the subagent→team tip), then the prose section needs at minimum a worked excerpt or a resolved example, not a preview of one.

- **`03-content.prose.md` § "Subagents: the basic case" — the code block carries unexplained baggage.** The snippet names specific tools (`"Read"`, `"Bash"`) without any prior mention of what tool assignment means for a subagent's capabilities. A reader who does not already know Claude Code will not know whether these are illustrative labels or load-bearing details. The surrounding prose does not clarify.

- **`01-context.prose.md` — the analogy section ("Older than computing") is unanchored.** Three analogies appear — research lab, factory, film crew — but they are listed, not argued. The sentence that follows ("What changed with LLMs: the workers now **reason**, not just execute") does real work, but it would land harder if one analogy were unpacked just enough to make the contrast vivid. As three parallel items with no elaboration, this reads as decoration.

- **`04-conclusion.prose.md` — the conclusion is a restatement, not a close.** The five bullets mirror `01-context.prose.md` exactly (per the spine's explicit instruction). That symmetry is structurally sound, but the section ends without a single forward-pointing sentence. The spine's own open question — "is that the right register?" — is unresolved. A one-sentence bridge connecting back to the course, or naming what the reader can build next with this pattern, would give the section a final beat rather than a trailing list.

---

## Actionable

1. **`02-motivation.prose.md` § "What goes wrong without it" — surface attention degradation as a distinct failure mode.** Add one sentence before the figure that distinguishes two failure modes: (a) the context fills and earlier findings are dropped, and (b) the model attends poorly to middle-context material *before* the window fills — producing output that looks complete but is silently degraded. The second is what makes the failure dangerous. (*Why:* the prose currently supports only "ran out of room"; the harder and more important case — silent degradation under full context — goes unnamed, and the pitfall table in §03 cannot land "silent failure" as a surprise if the reader was never told it happens.)

2. **`03-content.prose.md` § "Case study" — replace the stage-direction bullets with a minimal resolved excerpt.** The "Watch for:" list assumes a live demo that the document cannot deliver on its own. Replace it with a two- or three-turn exchange showing one moment of constraint conflict between agents and how it resolves — enough for a reader working from the document alone to see the pattern execute once. The live demo can then *extend* this rather than being the only version of it. (*Why:* the case study is positioned as the climax of the HOW section; if it delivers nothing without an instructor present, the document's standalone teaching value collapses at its most important moment.)

3. **`03-content.prose.md` § "Subagents: the basic case" — add a one-sentence gloss on what the `tools` array means.** After the code block, add: "The `tools` list is what the subagent is allowed to use — scoping it is how you enforce the agent's isolation." This requires no new concept; it echoes "Worker isolation is a feature, not a limitation" from the spine. (*Why:* the code block is currently the first place a reader encounters the idea that tool access is controlled at spawn; without this gloss, the snippet teaches syntax rather than the design principle it is supposed to illustrate.)

4. **`01-context.prose.md` § "Where this pattern came from" — cut two analogies and unpack one.** Keep one analogy (the research lab is the closest fit for a graduate student audience), drop the other two, and add one sentence of contrast: what the team coordinator in a research lab *cannot* do that an orchestrating agent can. (*Why:* three parallel analogies with no elaboration read as filler; one analogy followed by a precise contrast does the actual rhetorical work of making the "workers now reason" claim feel earned rather than asserted.)

5. **`04-conclusion.prose.md` — add a single closing sentence that points forward.** One sentence after the bullet list, naming what the reader can now compose this pattern *with* — the next module, the next problem type, or the next design decision they will face. (*Why:* the section currently ends mid-air; the spine's own open question confirms this is unresolved, and a list without a closing beat leaves the reader without a sense of arrival.)
