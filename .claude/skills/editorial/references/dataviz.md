# Dataviz

Design and critique data visualizations within the editorial layout system using Tufte's principles. Bridges the structural grid (editorial-grid) with data-ink integrity (tufte-viz).

## When to Use

Designing a new chart, sparkline, dashboard, or data-dense display. Critiquing an existing visualization that feels cluttered, dishonest, or decorative. Deciding between visualization approaches for a given dataset.

## Load These Source References

- `../../tufte-viz/SKILL.md` — full design + critique workflow, the eraser test, the collision test
- `../../tufte-viz/references/tufte-principles.md` — lie factor, data-ink ratio, chartjunk, small multiples, density, aesthetics
- `../../tufte-viz/references/analytical-design.md` — 6 analytical design principles, sparklines, layering & separation, micro/macro, range-frames, confections
- `../../editorial-grid/references/grid-construction.md` — typographic scale, baseline rhythm (for integrating viz into editorial layouts)
- `../../spread-archetypes/references/four-archetypes.md` — data spread archetype rules and failure modes

## Protocol

### 1. Clarify the Data Story

Before any design decision:

- **What comparisons matter?** ("compared to what?" is the fundamental analytical question)
- **What's the key insight?** One sentence — if you can't state it, the visualization won't communicate it
- **Who reads this?** Scanning a dashboard vs. studying a report vs. reading inline with prose
- **Where does this live?** Standalone page, embedded in editorial prose, dashboard panel, inline sparkline

### 2. Select the Approach

Use Tufte's content-driven selection:

| Data character | Approach | Why |
|---|---|---|
| High comparison need | Small multiples | Same structure, data varies — eye compares effortlessly |
| Dense, many metrics | Data table with sparklines | Highest density per unit area |
| Time-series | Line chart, minimal grid | Shape and trend dominate |
| Part-to-whole | Bar chart or table | Avoid pie charts — angle perception is unreliable |
| Distribution | Dot-dash plot, rug plot | Marginal densities carry data on the axes themselves |
| Multivariate | Parallel coordinates, scatterplot matrix | Show interactions, don't reduce to univariate |

### 3. Design with Data-Ink in Mind

1. Start with the data marks only — no axes, no grid, no labels, no legend
2. Add the minimum structure needed for the data to be readable
3. Every added element must earn its ink — ask "does removing this lose information?"
4. Default to grayscale; add color only when it encodes a variable
5. Use range-frames instead of full axes (axis spans data range, not arbitrary round numbers)
6. Use direct labels instead of legends when feasible

### 4. Integrate with the Editorial Grid

Visualizations don't float outside the layout system:

- **Width**: size to integer column-span widths from the active grid (vault or swiss)
- **Height**: align to baseline grid multiples where possible
- **Typography**: use the same type scale as the surrounding editorial context — don't introduce a parallel scale for chart labels
- **Caption placement**: below the figure, on the grid, sized per editorial convention (2pt smaller than body)
- **Annotation placement**: in vault layout, use the annotation column for figure notes; in swiss, use a dedicated span

### 5. Run the Eraser Test

For every non-data element (label, tick, gridline, border, annotation, legend entry):

- Can it be removed without losing information not conveyed elsewhere?
- Are two elements encoding the same thing? (numeric label + tick position; legend + direct label) Keep one.
- If the element is structural (axis, scale marker): can it be replaced by a data-carrying element (range-frame, rug plot)?

### 6. Run the Collision Test

For every text element in the visualization:

- Draw its bounding box mentally. Does any other element — text, data mark, line — cross that box?
- Standard fixes: move prose to figcaption, relocate band labels to a strip above the plot, push reference labels to the margin, add leader lines for in-plot annotations
- Watch especially: inverted axes, dense scatter, shared-scale small multiples where labels stack near zero

### 7. Run the Integrity Check

| # | Check | Rule |
|---|---|---|
| D1 | Lie Factor ≈ 1.0 | Visual effect size matches data effect size |
| D2 | Baselines honest | Zero baseline for magnitude comparisons; truncation only with clear annotation |
| D3 | No fake dimensions | No 3D on 2D data, no area/volume encoding of linear quantities |
| D4 | Scales consistent | Across small multiples, across panels, across time |
| D5 | Context present | Source, date, units, sample size — documentation enables trust |
| D6 | Comparisons enabled | "Compared to what?" has a visible answer |
| D7 | Causality shown | Mechanism or explanation visible, not just pattern (where relevant) |
| D8 | Multivariate | Interactions shown, not over-reduced to single variable |
| D9 | Words/numbers/images integrated | Labels near data, equations near curves — not segregated |
| D10 | Micro + macro | Rewards both a glance and a close read |
| D11 | Layering correct | Primary data dominates; secondary recedes; grid whispers |
| D12 | Data density appropriate | Could more data fit without losing clarity? |

### 8. Report

For new designs:

```
## Dataviz: [target]

### Data Story
- Comparison: [what's being compared]
- Insight: [one sentence]
- Context: [where it lives in the layout]

### Approach
[Selected visualization type + rationale]

### Grid Integration
- Width: [column span]
- Height: [baseline multiples]
- Type scale: [shared with editorial context? deviations?]

### Tufte Checklist
D1–D12: [PASS/FAIL per item]

### Files Created/Modified
- [file:line]: [what it does]
```

For critiques:

```
## Dataviz Critique: [target]

### Findings

**Integrity**
- [D# FAIL]: [what's wrong, the Tufte principle violated]
  → [file:line]
  Fix: [specific recommendation]

**Data-Ink**
- [Elements to erase]: [what they are, why they're redundant]
- [Elements to convert]: [from decoration to data-carrying]

**Collisions**
- [Text/element overlaps]: [location, fix]

**Grid Integration**
- [Misalignment with editorial grid]: [what to snap to]

### Summary
[1-2 sentences: the core issue and the path forward]
```
