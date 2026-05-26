# Grid construction — the working manual

This is the operating manual. The SKILL.md gives the decisions; this file gives the constructions, ratios, and tables you actually need at the table.

---

## 1. Page proportions, constructed

### 2:3 (Tschichold's classical preference)

- Width:Height = 1 : 1.5
- Sits in the Fibonacci sequence (2, 3, 5, 8, 13…)
- Approaches but does not equal the golden ratio
- The proportion of the medieval canon and most pre-industrial codex work

### Golden (1 : 1.618)

- φ = (1 + √5) / 2 ≈ 1.6180339887
- Penguin paperback: 4⅜ × 7⅛ inches (≈ 111 × 181 mm)
- Self-similar under removing a square: a golden rectangle minus a square equals a smaller golden rectangle
- Used historically for objects meant to be held and contemplated

### A-series (1 : √2 ≈ 1 : 1.414)

- ISO 216
- A0 = 1 m², each subsequent size is the previous halved along the long edge
- A4 = 210 × 297 mm
- Self-similar under halving — an A4 halved gives two A5s of identical proportion
- Use for: documents that will be folded; multi-format publications; anything where dimensional rigor matters more than classical aesthetics

### When to break the rules

- **Square**: ceremonial, monumental, equalizes horizontal/vertical reading — appropriate for catalogs, art books, content with no inherent reading direction
- **Broadsheet** (wider than tall, e.g., 4:3): newspaper inheritance, scanning rather than reading, content arranged by zone
- **Panoramic** (very wide, e.g., 16:9 or wider): cinematic, sequential, screen-native

Whatever you choose: name it. If you cannot state the ratio, you eyeballed it.

---

## 2. Van de Graaf canon, step by step

The Van de Graaf canon is the most useful page-construction method for 2:3 pages. It produces margins of 2:3:4:6 (inner:top:outer:bottom) without measurement — only diagonal construction.

### Construction (geometric)

1. Draw the full spread (two facing pages).
2. Draw both diagonals across the full spread (corner to corner).
3. Draw both diagonals of the single right page (corner to corner).
4. Where the spread-diagonal and page-diagonal meet on the right page, drop a vertical line to find the top-right corner of the text block.
5. Draw a horizontal line through this corner to the spread-diagonal on the left of the right page; this gives the top-left corner of the text block.
6. The text block now has its top corners; extend lines down parallel to the page edges; the bottom of the text block is determined by the same construction inverted.

### Result (arithmetic)

- Page divided into a 9×9 grid
- Text block occupies fields 2–7 horizontally, 2–7 vertically (a 6×6 block within a 9×9 page)
- Inner margin = 1/9 of page width
- Top margin = 1/9 of page height
- Outer margin = 2/9 of page width
- Bottom margin = 2/9 of page height
- Margin ratio: 1:1:2:2 in raw fractions, but expressed as 2:3:4:6 when accounting for page-ratio relationships

### Tschichold's medieval alternative: 1:1:2:3

Simpler, deeper margins, more austere. Inner:top:outer:bottom = 1:1:2:3 with the bottom margin three times the inner margin. Use for prayer-book-density text, monumental presentation, or when you want the page to feel pre-modern.

### What never changes across canons

- Bottom margin is always the largest (we hold the book by the lower margin — Renner)
- Outer margin exceeds inner (thumb room, prevents claustrophobia at the gutter)
- Top margin is small or medium — never the largest

If a layout has top margin > bottom margin, it feels visually unstable, like the text is sliding off the page. This is the single most common margin failure.

---

## 3. Modular grids — field count and column derivation

| Field count | Best for | Typical columns |
|---|---|---|
| 8 | Posters, simple editorial, decisive single-purpose work | 1, 2, 4 |
| 12 | Editorial default; books, magazines | 1, 2, 3, 4, 6 |
| 16 | Magazines with mixed content, image-heavy work | 1, 2, 4, 8 |
| 20 | Complex editorial with quantitative content | 1, 2, 4, 5, 10 |
| 24 | Multivariate display; specimen pages; data-dense work | 1, 2, 3, 4, 6, 8, 12 |
| 32 | High-density, multi-language, encyclopedic | 1, 2, 4, 8, 16 |

**Field count is not column count.** Field count is the underlying division of the text area; column count is one decision *made on top of* the field grid. A 24-field grid lets you run prose in 3 columns on one page and 4 columns on the next, with everything still aligning to the underlying field divisions.

### Gerstner's morphological grid

A 6×6 module square overlaid with sub-grids of 1, 2, 3, 4 units on a single baseline. From *Designing Programmes* (1963).

- All four sub-grids share the same baseline → vertical rhythm stays consistent
- Each sub-grid offers different column widths → horizontal flexibility
- The "morphological box" lets one layout accommodate radically different content types without breaking rhythm

Use when: one publication must contain prose, data, specimens, and images and stay visually coherent.

---

## 4. Typographic scales

### Classical progression (use as default for bookwork)

6 · 7 · 8 · 9 · 10 · 11 · 12 · 14 · 16 · 18 · 21 · 24 · 36 · 48 · 60 · 72

- Octaves: 6 → 12 → 24 → 48 (each double the last)
- Intermediates follow the fifth root of 2 ≈ 1.1487
- 400+ years of use; deeply legible

### Modular scale ratios (use for screen / contemporary work)

| Ratio | Name | Decimal | Character |
|---|---|---|---|
| 16/15 | Minor second | 1.067 | Close-spaced, subtle hierarchy |
| 9/8 | Major second | 1.125 | Gentle hierarchy |
| 6/5 | Minor third | 1.200 | Moderate |
| 5/4 | Major third | 1.250 | Strong, screen-friendly |
| 4/3 | Perfect fourth | 1.333 | Dramatic, web default |
| √2 | Augmented fourth | 1.414 | Architectural; aligns with A-series geometry |
| 3/2 | Perfect fifth | 1.500 | Bold hierarchy |
| 8/5 | Minor sixth | 1.600 | Approaches φ |
| φ | Golden ratio | 1.618 | Maximum dramatic; classical aesthetic |

**Worked example** — base 16px, perfect fourth (1.333):

12 · 16 · 21 · 28 · 38 · 50 · 67

(working down from base: 16 / 1.333 ≈ 12; working up: 16 × 1.333 ≈ 21, ×1.333 ≈ 28, etc.)

### Double-stranded scale

Two base sizes or two ratios interleaved. Produces richer vocabulary for complex layouts.

Example: bases 12 and 16, ratio 1.333:

9 · 12 · 12 · 16 · 16 · 21 · 21 · 28 · 28 · 38

Use when one publication needs distinct hierarchies for body text, display, captions, and quantitative annotation without scale collisions.

---

## 5. Line metrics — the working numbers

### Characters per line

| Configuration | Range | Ideal |
|---|---|---|
| Single column, serif body | 45–75 | **66** |
| Multi-column, serif | 40–50 | 45 |
| Single column, sans-serif | 45–70 | 60 |
| Display / large type | 30–50 | 40 |

**Müller-Brockmann's rule:** approximately 7 words per line at 30–35 cm reading distance.

### Leading

- **120% of type size** = classical default (10pt type → 12pt leading)
- **125–140%** = comfortable for moderate lines
- **150%** = for lines approaching the upper character limit (70+)
- **Below 110%** = lines touch; eye fatigue

### Gutter

- **~2 ems** = standard, proportional to text size
- Minimum: enough to prevent the eye from jumping between columns on line-return
- Too narrow → eye-jumping
- Too wide → columns feel disconnected

### Caption sizing

- **2 points smaller than body text** (Bringhurst convention)
- Often in **contrasting face** — sans against serif body, or vice versa
- Below figures; **above** tables (tables read top-down, figures read body-first)

---

## 6. Baseline rhythm — the math

The baseline grid is a single horizontal rhythm to which all text aligns across all columns.

### Construction

1. Set body-text size and leading. Example: 10/14 (10pt text, 14pt leading).
2. Baseline unit = leading value = 14pt.
3. All other vertical measurements must be integer multiples of 14pt:
   - Paragraph spacing: 14pt (one baseline) or 28pt (two)
   - Headers: 28pt (2 baselines), 42pt (3 baselines), etc.
   - Image heights: 7 × 14 = 98pt, 8 × 14 = 112pt, etc.
   - Margin offsets: integer multiples of 14pt

### Worked example

Body 10/14. Column has 30 lines of body text = 30 × 14 = 420pt.

- A figure placed in this column should be 14pt × n high (where n is an integer)
- A caption block of 3 lines at 8/14 = 42pt total height
- Combined figure + caption + body should still terminate at a baseline-aligned position

### When the baseline breaks

Display type, large images, pull-quotes, and figure spreads will sometimes not fit the baseline neatly. The rule:

- **Announced breakage**: the broken element is separated from body text by clear margin, framed by rules, or otherwise visually distinguished — the eye is told *"this is a different rhythm zone."*
- **Accidental drift**: text in column A is one baseline ahead of text in column B. This is unforgivable and reads as sloppy regardless of how good the rest of the spread is.

Squint test: at low focus, do adjacent columns show a shared horizontal rhythm or do they look like two different documents? If different, the baseline grid is broken.

---

## 7. The screen translation problem

Most of these rules originated in print where the unit (point) and the page (fixed dimension) were stable. Screen translation needs explicit handling.

### Stable across media

- Character-per-line counts (45–75)
- Leading as percentage of type size (120%+)
- Margin proportions (the *ratios* survive; the absolute values don't)
- Scale ratios (1.067, 1.250, 1.333, 1.618)
- Asymmetric balance, baseline alignment

### Needs translation

- **Page proportion** → viewport proportion (variable). Solution: design for a primary breakpoint with proportions explicit, then state how proportions degrade at other widths.
- **Absolute margins** → relative margins (% or em-based). The 2:3:4:6 ratio is what matters; pixel values are not.
- **Field grids** → CSS Grid with named columns. Müller-Brockmann's 12-field grid maps directly to `grid-template-columns: repeat(12, 1fr)`.
- **Baseline grid** → line-height inheritance. Set body line-height as a unit, derive all vertical spacing from multiples of that unit.

### The mid-grid problem

Print grids assume a fixed page. Responsive grids must degrade — a 16-field grid at desktop becomes a 4-field grid on mobile. The rule: **degrade by halving field count**, never by stretching elements. 16 → 8 → 4 → 1 keeps proportional relationships intact; 16 → 12 → 9 → 6 produces accidental geometries.

---

## 8. The consistency test

Before shipping any layout, walk through these:

1. **Name the page proportion.** Can you state it as a ratio? Is the ratio appropriate to the content's reading mode?
2. **Name the margin canon.** Bottom largest? Outer larger than inner?
3. **Identify the modular grid.** Drop a mental overlay — do elements align to the field divisions?
4. **List all type sizes used.** Can they all be expressed as values in one named scale? If not, the scale is broken or absent.
5. **Measure characters per line.** In the 45–75 range (single column) or 40–50 (multi-column)?
6. **Measure leading.** 120% of type size or more?
7. **Check baseline alignment.** Squint at adjacent columns — shared rhythm or independent drift?
8. **Audit grid breakages.** Where the grid is violated, is the violation announced or accidental?

A layout that passes all eight is structurally sound. The archetype, the aesthetic, the surface treatment — those decisions ride on this foundation.
