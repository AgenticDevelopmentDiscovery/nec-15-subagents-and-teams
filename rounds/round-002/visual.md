# Visual & Multi-Register Exposition — Round 2

**Recommendation:** minor polish
<one missing figure covers the tutorial's central how-to, one slide overflows, and document-register prose is thin in three sections>

---

## Slide overflow

- `03-content.prose.md` § "Case study: designing a chair with three agents" — overflows because: genuinely dense. One slide must hold: a task sentence, a 3-row agent table, and a 3-item "Watch for" list. Estimated at 14–16 projected lines; a typical slide holds 10–12 comfortably.
- `03-content.prose.md` § "How to decompose a task" — borderline (estimate only). Four numbered questions each carry a sub-clause, followed by a full example paragraph. Dense rather than padded; this can stay on one slide if the font is small, but it is the most text-heavy non-table slide in the deck.

---

## Strengths

- **Figures earn their place, all three.** `single-agent-limit.svg` makes the context-window degradation problem concrete in a way prose alone cannot; `failure-mode.svg` gives the parallel-vs-serial argument a before/after structure that works in all three registers; `orchestrator-worker.svg` externalises the subagent/team structural distinction that is otherwise purely definitional.
- **Captions are self-contained.** All three captions could stand alone if the figure were lifted out of context — correct behaviour for website and presentation registers.
- **Heading scanability is strong (website register).** "When to use multiple agents," "When one agent is enough," "Subagents vs teams: choosing" all work as entry points for a reader arriving mid-document; no heading requires the previous heading to parse.
- **The comparison table in § "Subagents vs teams: choosing" works in all three registers.** Five rows, five columns is dense on a slide but the column headers are short enough that it survives projection without wrapping.

---

## Weaknesses

- `03-content.prose.md` § "Orchestrators and workers" — figure with no surrounding prose. In presentation register this is intentional (full-bleed figure slide). In document register it leaves a blank expanse: the reader cannot tell whether the figure is a preview or a summary, and there is nothing to reference the figure from. The caption does the work alone, which is too much to ask of it.
- `02-motivation.prose.md` § "Why a single agent is not enough" — heading plus figure, nothing else. Sparse is fine for a slide, but in document register the argument lives entirely in the heading and the figure caption; a reader scanning the PDF has no sentence to land on. The same structural thinness appears in § "What goes wrong without it," which is heading + task sentence + figure.
- `03-content.prose.md` — no figure covers **task decomposition**: how a monolithic task fans out into parallel worker streams and converges back at the orchestrator. This is the tutorial's central operational pattern, described only through four abstract questions and a one-line example. It is the single idea that most needs a diagram.
- `01-context.prose.md` — document-register transitions are absent. Sections are lists with headings but no connective tissue. A reader of the PDF moves from "Where this pattern came from" to "What this tutorial covers" with no bridge sentence; the sections read as separate bullets in a slideshow, not as paragraphs in a document.
- `03-content.prose.md` § "Subagents: the basic case" — the italicised platform note (*The examples below use Claude Code…*) is a document-register aside that is invisible on a projected slide (italic small text is the first casualty of projection). Its information is necessary but its format does not survive the presentation register.

---

## Actionable

1. `03-content.prose.md` § "How to decompose a task" — add a figure showing the fan-out / parallel / converge structure: a single task node at top, four arrows fanning to labelled worker nodes (Security / Performance / Coverage / …), then arrows converging back to an Orchestrator node at the bottom. Place it after the four questions and before the example paragraph.
   *(why: document register — this is the core how-to pattern and currently the only major abstraction in the tutorial without a visual; also repairs the dense-slide estimate by letting the prose compress around the figure)*

2. `03-content.prose.md` § "Case study: designing a chair with three agents" — split into two `##` slides: the first holds the agent-constraint table, the second holds "Watch for" with a brief framing sentence. Alternatively, fold "Watch for" into the caption of the figure recommended for item 1 above if that figure appears here instead.
   *(why: slide register — current single slide overflows by ~4 lines)*

3. `03-content.prose.md` § "Orchestrators and workers" — add one or two sentences of prose after the figure: name what the two topologies are, state which to start with, and point forward to § "Subagents vs teams: choosing." Keep it under 40 words so the slide survives.
   *(why: document register — the section is currently heading + figure, with no text anchor; also gives the figure a forward reference from prose, not just a caption)*

4. `02-motivation.prose.md` § "Why a single agent is not enough" and § "What goes wrong without it" — add a single topic sentence above each figure (not a caption — prose). One sentence each is enough: it gives the document reader something to land on and tells the slide attendee what they are about to see.
   *(why: document register; the slide register is unaffected because the sentence becomes the visible label above the figure)*

5. `03-content.prose.md` § "Subagents: the basic case" — convert the italicised platform note into a `> **Note:**` blockquote or a labelled callout. Both render at readable size in presentation mode and signal non-main-flow content in the website register without relying on italic weight.
   *(why: presentation register — italic small text does not project reliably)*
