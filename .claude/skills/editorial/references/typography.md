# Typography

Focused typographic audit. Deep check on scale coherence, line metrics, baseline grid alignment, and rhythm. The subset of editorial-grid that deals exclusively with type.

## When to Use

When text "feels off" but the grid seems fine. When establishing or auditing a type system. When adding new type sizes or adjusting line metrics. After font changes.

## Load These Source References

- `../../editorial-grid/references/grid-construction.md` — sections 4 (typographic scales), 5 (line metrics), 6 (baseline rhythm)

Also read the project's design token file: `src/styles/vault/vault-tokens.css` (Layer 2 contains the fluid type scale).

## Protocol

### 1. Extract the Type Inventory

From the target file(s) and their imported styles, list every type size, weight, line-height, and letter-spacing value in use. Include:

- CSS custom properties (from vault tokens)
- Inline/scoped styles
- Utility classes
- Computed values from `clamp()` expressions (evaluate at primary breakpoint ~1200px)

Format as a table:

```
| Element | Size | Weight | Line-height | Letter-spacing | Source |
|---|---|---|---|---|---|
| h1 | clamp(2.25rem, ...) | 700 | 1.1 | -0.02em | vault-tokens.css:L42 |
| body | 1.125rem | 400 | 1.65 | normal | vault-tokens.css:L38 |
...
```

### 2. Derive the Scale

From the inventory, attempt to express all sizes as a single modular scale:

1. Identify the base size (usually body text)
2. Calculate the ratio between each step
3. Check if the ratios are consistent (within 5% tolerance)
4. Name the scale if it matches a known ratio:
   - 1.067 = minor second
   - 1.125 = major second
   - 1.200 = minor third
   - 1.250 = major third
   - 1.333 = perfect fourth
   - 1.414 = augmented fourth
   - 1.500 = perfect fifth
   - 1.618 = golden ratio

If sizes don't fit a single scale, flag the outliers and suggest which scale they should snap to.

### 3. Check Line Metrics

For each text context (main content, annotations, captions, headings):

| Metric | Rule | How to check |
|---|---|---|
| Characters per line | 45–75 single, 40–50 multi | `max-width` in `ch` units, or calculate from container width ÷ average character width |
| Leading | ≥ 120% of type size | `line-height` as ratio of `font-size` |
| Leading for long lines | 150% if chars > 70 | Increase leading as line length approaches upper limit |
| Gutter | ≥ 2 ems | Gap between columns, proportional to text size |
| Caption sizing | ~2pt smaller than body | Bringhurst convention |

### 4. Check Baseline Grid

1. Identify the baseline unit (should derive from body line-height)
2. Check that vertical spacing values are integer multiples of the baseline unit:
   - Paragraph spacing
   - Heading spacing (above and below)
   - Figure heights
   - Margin offsets
   - Section gaps
3. Flag any values that don't align to the baseline rhythm
4. Check adjacent-column alignment — shared horizontal rhythm or independent drift?

### 5. Check Hierarchy Contrast

Between adjacent scale steps:
- Size ratio ≥ 1.2 (anything less reads as the same size at scanning speed)
- Weight contrast meaningful (400→700 is clear; 400→500 is subtle)
- Combined contrast (size + weight + color) sufficient to establish clear visual hierarchy

### 6. Report

```
## Typography: [target]

### Scale
Name: [ratio name or "no coherent scale"]
Base: [base size]
Steps: [list with ratios between each]
Outliers: [sizes that break the scale]

### Line Metrics
| Context | Chars/line | Leading | Status |
|---|---|---|---|
| Main content | 62 | 165% | PASS |
| Annotation | 28 | 140% | FAIL — too narrow for comfortable reading |
...

### Baseline Grid
Unit: [value]
Aligned: [list of values that are integer multiples]
Misaligned: [list with file:line references]

### Hierarchy
| Step | From → To | Size ratio | Weight contrast | Verdict |
|---|---|---|---|---|
| body → h3 | 18 → 21 | 1.17 | 400→600 | WEAK — ratio below 1.2 |
...

### Summary
[1–2 sentences: is the type system coherent, and what's the single most impactful fix?]
```
