# Elenchus — Pre-Design Method

The compressed protocol for naming the argument before designing. For the full method and its philosophical grounding, see `../../elenchus/SKILL.md`.

## When to invoke

Invoke for content that *argues*: personal essays, philosophical writing, investigative articles, manifestos, any spread where the form is expected to encode the structure of thought rather than merely present it.

Do not invoke for content that *displays*: documentation, indexes, lists, navigation, utility surfaces, data dashboards, transactional flows. Those go straight to `editorial-grid` and `spread-archetypes` without the elenchus front-loaded.

The diagnostic: if you cannot state what the layout is *claiming*, the content argues. If the layout's job is to *show* rather than *claim*, it displays.

## The five moves

### Move 1 — Find the question

One sentence. Interrogative. Specific enough that it can be wrong.

*Why does Orpheus look back when he was told not to?* is a question. *Orpheus and the nature of love* is a topic. The question commits to an answer; the topic does not. A topic can wander for ten thousand words and never arrive. A question either gets answered or visibly fails to, and either is honest.

You cannot draw a grid for a wander. You can draw a grid for a question.

### Move 2 — Find the antinomy

One line, two clauses. The contradiction the question exists to circle.

*He was forbidden to look back. He had to look back.* Both are true. The article is the work of showing how both are true. If you cannot state the contradiction, you do not yet have a question worth writing — you have a question that has not yet revealed why it matters.

### Move 3 — Find the answer

One sentence. Declarative. The shape of the synthesis the article will earn.

*Because the looking back is the love.* This is provisional — the writing may discover it is wrong, and that is fine. But you need a shape to aim at. Without it, the prose drifts.

### Move 4 — Assign form

Each part of the argument binds to one form. These are the bridges into `spread-archetypes` and `editorial-grid`:

| Argument part | Form | Character | Archetype bridge |
|---|---|---|---|
| Question | Architecture | Single sentence at page scale. The reader is enclosed by it. | Ratio/specimen (typographic object at monumental scale) |
| Antinomy | Tension | Two clauses held apart, refusing to resolve. Geometry that does not close. | Fragmented Merz (governed fragmentation, grid intact underneath) |
| Development | Prose | Multi-column body with sidenotes in contrasting face. The long middle. | Multi-column prose (baseline-locked, marginal voice) |
| Synthesis | Construction | A figure built on a visible grid. The grid is the premise; the figure is the conclusion. | Ratio/specimen (modular grid construction, grid must remain visible) |

Reference images for the construction form:
- `../../elenchus/references/hofmann-construction-grid.png` — the grid underneath
- `../../elenchus/references/hofmann-exposition-poster.png` — the figure derived from it

### Move 5 — Refuse to design

Do not open the editor, do not write CSS, do not choose a typeface or set a margin until moves 1–4 are done. The grid is the architecture of an argument that exists; it cannot be the architecture of an argument that does not yet exist.

## Output

When the five moves are complete, you have:

1. **Three sentences** — question, antinomy, answer
2. **Four form-assignments** — architecture, tension, prose, construction, each bound to its archetype bridge

These hand off to `construct` (for building the layout) or inform `critique` / `validate` / `polish` (for reviewing whether the argument-form binding holds).

## The refusal

If the three sentences will not clarify — if the question keeps revising itself, if the antinomy will not name itself, if the answer refuses to take a shape — do not proceed to design. The article is not ready. The wound is still healing or still opening. This is not failure; it is fidelity.
