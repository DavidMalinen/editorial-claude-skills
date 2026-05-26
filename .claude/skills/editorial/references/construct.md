# Construct

Guided new layout creation. Walks through every structural decision in order: page proportion → margin canon → modular grid → typographic scale → line metrics → baseline grid → archetype selection. Produces a working layout file.

## When to Use

Building a new page or layout from scratch. Setting up a new content type. Creating a variant layout for an existing system.

## Load These Source References

- `../../editorial-grid/SKILL.md` — the full construction workflow (steps 1–7)
- `../../editorial-grid/references/grid-construction.md` — all constructions, ratio tables, worked examples
- `../../spread-archetypes/SKILL.md` — archetype selection workflow
- `../../spread-archetypes/references/four-archetypes.md` — governing rules per archetype

## Protocol

### 1. Clarify the Content

Before any structural decision, establish:

- **What content will this layout hold?** (blog prose, data visualization, specimen display, manifesto/fragment)
- **What is the reading mode?** (sustained reading, scanning, contemplating, deciphering)
- **What is the relationship between text and image?** (text-dominant, image-dominant, integrated, alternating)
- **Which layout system?** (vault or swiss — or does this need a new one?)

If the user hasn't specified, ask. Do not assume.

### 2. Choose Page Proportion

Present the options with context:

| Proportion | Ratio | Best for |
|---|---|---|
| 2:3 | 1 : 1.5 | Classical bookwork, editorial, blog prose |
| Golden | 1 : 1.618 | Objects meant to be held and contemplated |
| A-series | 1 : 1.414 | Documents that fold, dimensional rigor |
| Custom | stated | Only if content demands it |

For screen work: this translates to the primary breakpoint's content-area proportions. State which breakpoint the proportion targets and how it degrades.

**Ask the user to choose, or recommend based on content type.**

### 3. Construct Margins

Based on the chosen proportion, present the margin options:

- **Van de Graaf 2:3:4:6** — default for 2:3 pages. 9×9 grid construction.
- **Medieval 1:1:2:3** — deeper, more austere. Prayer-book density.
- **Custom** — must state which canon it modifies and why.

Translate to CSS: use relative units (%, em, or the token system's spacing scale) to preserve the *ratios*, not absolute values.

Verify: bottom ≥ top, outer ≥ inner. Always.

**Ask the user to choose, or recommend based on content type.**

### 4. Establish the Modular Grid

Choose field count based on content complexity:

| Content complexity | Field count | Typical columns |
|---|---|---|
| Simple, decisive | 8–12 | 1, 2, 3 |
| Mixed editorial | 16–20 | 2, 3, 4 |
| Complex, multivariate | 24–32 | 3, 4, 6+ |

For vault: the existing 5-column system (content + gutter + annotation) is already an opinionated grid. Construct will work within it or propose modifications.

For swiss: map directly to CSS Grid `grid-template-columns`.

**Ask the user to choose, or recommend based on content type.**

### 5. Set the Typographic Scale

Choose a scale approach:

- **Classical progression**: 6·7·8·9·10·11·12·14·16·18·21·24·36·48·60·72 — for traditional editorial
- **Modular scale**: base × ratio — for screen/contemporary. Present the ratio options from grid-construction.md
- **Double-stranded**: two bases or two ratios — for complex multi-hierarchy content

Check against existing vault tokens. If the project already has a fluid type scale in `vault-tokens.css`, propose working within it or extending it. Do not create a parallel scale.

**Ask the user to choose, or recommend based on content type.**

### 6. Set Line Metrics

Calculate and set:

- **Characters per line**: derive `max-width` in `ch` from the target range (45–75 single, 40–50 multi)
- **Leading**: ≥ 120%, increase toward 150% for longer lines
- **Gutter**: ~2 ems, proportional to text size
- **Caption sizing**: 2pt smaller than body, contrasting face

### 7. Establish Baseline Grid

1. Set baseline unit = body line-height
2. Define all vertical spacing as multiples of this unit
3. Document the baseline unit in a comment or token

### 8. Select the Archetype

Based on the content clarification from step 1, recommend the archetype:

| Content type | Archetype |
|---|---|
| Quantitative / comparative | Data spread |
| Proportion, character, specimen | Ratio/specimen |
| Poetic, manifesto, fragment | Fragmented Merz |
| Sustained prose with figures | Multi-column prose |

Load the archetype's governing rules and apply them to the layout structure built in steps 2–7.

### 9. Build

Write the layout file(s):
- Astro layout component
- CSS (scoped or in token file, depending on reuse)
- Add any new tokens to the appropriate layer in `vault-tokens.css`

### 10. Validate

Run the validate checklist against the new layout. All items should pass — if not, fix before reporting.

### 11. Report

```
## Constructed: [target]

### Decisions
- Proportion: [choice + rationale]
- Margins: [canon + CSS translation]
- Grid: [field count + column mapping]
- Scale: [name + base + ratio]
- Metrics: [char/line, leading, gutter]
- Baseline: [unit]
- Archetype: [name + content-type match]

### Files Created/Modified
- [file path]: [what it does]

### Validation
Grid: 12/12
Archetype: 8/8
```
