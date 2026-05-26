---
name: editorial-grid
description: |
  Construct and critique the structural infrastructure underneath any editorial
  layout: page proportion, margin canon, modular grid, baseline rhythm,
  typographic scale, character/line metrics. This is the grammar that
  archetypes (data, specimen, fragmented, prose) inflect — not the surface
  style. Use this skill when:
  (1) Setting up a new page, spread, or document from scratch
  (2) Critiquing a layout that feels structurally wrong but visually fine
  (3) Choosing page proportions, margins, or column counts
  (4) Establishing a typographic scale or modular system
  (5) Diagnosing why text feels off (line length, leading, baseline drift)
  (6) Translating print-derived grid systems to screen
  Applies principles: Van de Graaf canon, golden-ratio and 2:3 page geometry,
  Müller-Brockmann's 8–32 field grids, Gerstner's morphological grid,
  Bringhurst's character-count rule, classical typographic scale, modular
  scale ratios, baseline grid rhythm, asymmetric balance.
---

# Editorial Grid Construction

The grid is the lawful skeleton underneath every editorial layout. Surface differences between archetypes are real, but they all rest on the same grammar: page proportion, margin canon, modular grid, baseline rhythm, typographic scale. Get this right and the surface can vary; get this wrong and nothing on top of it can rescue the spread.

## Workflow

### For new layouts:

1. **Choose page proportion before anything else**
   - **2:3** — Tschichold's preferred ratio. Sits in the Fibonacci sequence, connects to the golden ratio. Classical bookwork.
   - **Golden (1 : 1.618)** — Aesthetically tuned. Penguin paperback covers at 4⅜ × 7⅛ inches.
   - **A-series (1 : √2 ≈ 1 : 1.414)** — A4 et al. Self-similar under halving (an A4 halved is two A5s). Use for documents that will be folded, halved, or that benefit from dimensional rigor.
   - **Custom** — only if the content demands it (broadsheet, square, panoramic). The custom ratio must be *stated*, not eyeballed.

   The page proportion is the first design decision. Everything else descends from it.

2. **Construct margins using a canon, not intuition**
   - **Van de Graaf canon** (default for 2:3 pages): divide the page into a 9×9 grid; text block starts 1/9 from top and inner edge, 2/9 from outer and bottom edges. Margin ratio **2:3:4:6** (inner:top:outer:bottom).
   - **Tschichold's medieval framework**: margin ratio **1:1:2:3** (inner:top:outer:bottom).
   - **Custom**: must state which canon it modifies and why.

   Two universal rules across canons:
   - Bottom margin is always largest (we hold the book by the lower margin — Paul Renner)
   - Outer margin exceeds inner (thumb room, visual breathing, prevents claustrophobic gutter)

3. **Establish the modular grid**
   - **Müller-Brockmann range: 8 to 32 fields.** Number of fields determines flexibility:
     - 8–12 fields: simple, decisive, fewer compositional options
     - 16–20 fields: balanced flexibility; the editorial default
     - 24–32 fields: high flexibility for complex multivariate content (data-heavy, image-dense, multi-language)
   - **Karl Gerstner's morphological approach**: a square of 6×6 modules can be overlaid by sub-grids of 1, 2, 3, and 4 units on a single baseline — compound flexibility within strict order. Use when one layout must accommodate radically different content types.
   - **Column count** descends from field count, not the other way around. 12-field grid permits 1, 2, 3, 4, 6 columns; 16-field permits 1, 2, 4, 8.

4. **Set the typographic scale**
   - **Classical progression** (400 years of use): 6, 7, 8, 9, 10, 11, 12, 14, 16, 18, 21, 24, 36, 48, 60, 72. Octaves double (6→12→24→48); intermediates follow the fifth root of 2 (≈1.1487). Use for traditional bookwork.
   - **Modular scale ratios**:
     - 1.067 (minor second) — close-spaced, subtle hierarchy
     - 1.250 (major third) — moderate hierarchy
     - 1.333 (perfect fourth) — strong hierarchy
     - 1.618 (golden ratio) — dramatic hierarchy
   - **Double-stranded scale**: two starting numbers or two ratios produce richer measurement vocabularies. Use for specimen layouts or multivariate displays.
   - **Bringhurst's directive**: *"Don't compose without a scale."* Ad-hoc sizing is the most common failure.

5. **Set line metrics**
   - **45–75 characters per line** for single-column serif body text (Bringhurst). **66 characters including spaces** is the ideal.
   - **40–50 characters** for multi-column work.
   - **~7 words per line** at 30–35 cm reading distance (Müller-Brockmann).
   - **Leading: 120% of type size** as baseline (10/12 is classical). **150%** for longer lines.
   - **Gutter: ~2 ems**, proportional to text size. Must prevent eye-jumping between columns.

6. **Establish the baseline grid**
   - All text aligns to a single baseline rhythm across all columns.
   - Baseline unit derives from body-text leading (typically 12pt for 10pt text).
   - All other vertical measurements — paragraph spacing, image heights, margin offsets — are integer multiples of the baseline unit.
   - Where the baseline grid breaks down (figure heights that don't fit, display type), the breakage must be *intentional and announced* — captioned, framed, separated from the body rhythm. Drift kills.

7. **Apply the consistency test before shipping** — see `references/grid-construction.md`

### For critiquing layouts:

1. **Identify the page proportion**
   - Can you name it (2:3, golden, A-series)? If not, it was probably eyeballed.
   - Does the proportion fit the content's reading mode (codex vs. broadsheet vs. document)?

2. **Identify the margin canon**
   - Is the bottom margin actually the largest?
   - Is the outer margin larger than the inner?
   - Can you reverse-engineer the ratio? (2:3:4:6? 1:1:2:3?)
   - If margins look symmetric or top-heavy, the canon is broken or absent.

3. **Identify the modular grid**
   - Drop a grid overlay mentally. Do elements align to consistent vertical and horizontal divisions?
   - Are images sized to integer-multiple column widths?
   - Where elements break the grid, is the breakage announced or accidental?

4. **Check the scale**
   - List all type sizes used. Can they be expressed as a single modular scale (with named ratio)?
   - If sizes are ad-hoc (12, 13.5, 15, 22), there's no scale — there's only intuition.

5. **Check line metrics**
   - Count characters per line in body text. Outside 45–75 (or 40–50 multi-column)?
   - Is leading visibly tight (under 120%) or loose (over 150% without long lines justifying it)?
   - Do gutters prevent eye-jumping?

6. **Check baseline alignment**
   - Squint at the spread. Does text in adjacent columns sit on a shared horizontal rhythm?
   - Or does each column drift independently?

7. **Suggest improvements** by naming the specific canon, ratio, or rule being violated.

## Key Principles Reference

- `references/grid-construction.md` — full constructions: Van de Graaf step-by-step, modular scale tables, character-count tables, baseline rhythm math, the screen translation problem. Load when actually constructing or auditing a grid.
- `references/asymmetric-balance.md` — the deeper principle underneath grid choice: why asymmetric arrangement is the default and what makes symmetric layouts feel ceremonial vs. timid. Load when composition feels structurally correct but emotionally wrong.

## Quick checklist

- [ ] Page proportion named (2:3, golden, A-series, or custom-with-rationale)
- [ ] Margin canon named (Van de Graaf 2:3:4:6, medieval 1:1:2:3, or stated alternative)
- [ ] Bottom margin > top margin
- [ ] Outer margin > inner margin
- [ ] Modular grid field count chosen for content complexity (8–32)
- [ ] Typographic scale named (classical, modular ratio, or stated)
- [ ] All type sizes derivable from the named scale
- [ ] Body text 45–75 char/line (single) or 40–50 (multi)
- [ ] Leading ≥ 120% of type size
- [ ] All text aligns to a baseline grid across columns
- [ ] Grid breakage (where present) is intentional and announced
- [ ] Gutters wide enough to prevent eye-jumping (~2 ems)
