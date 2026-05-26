# Validate

Post-change verification. "I just built or modified this layout — does it pass?" Binary pass/fail per rule, with file:line references for every failure.

## When to Use

After applying editorial-grid or spread-archetypes guidance. After any layout CSS or markup change. Before committing layout work.

## Load These Source References

- `../../editorial-grid/references/grid-construction.md` — ratio tables, character-count tables, baseline math
- `../../spread-archetypes/references/four-archetypes.md` — archetype rules and failure modes

## Protocol

### 1. Read the Target

Read all CSS and markup files involved in the target layout. Identify:
- The layout file (Astro layout, page template)
- The style files (vault tokens, component styles, scoped styles)
- The content file if applicable (frontmatter, pageLayout field)

### 2. Run the Grid Checklist

For each item, report **PASS** or **FAIL [reason] at file:line**.

| # | Check | Rule |
|---|---|---|
| G1 | Page proportion named | Ratio must be stated (2:3, golden, A-series, or custom with rationale) |
| G2 | Margin canon named | Van de Graaf 2:3:4:6, medieval 1:1:2:3, or stated alternative |
| G3 | Bottom margin ≥ top margin | Universal across all canons |
| G4 | Outer margin ≥ inner margin | Thumb room, prevents gutter claustrophobia |
| G5 | Modular grid field count | 8–32 fields, appropriate to content complexity |
| G6 | Typographic scale named | Classical, modular ratio, or stated — all sizes must derive from it |
| G7 | All type sizes on scale | List every size found; flag any that don't fit the named scale |
| G8 | Body text 45–75 char/line | Single column. 40–50 for multi-column. Measure at primary breakpoint |
| G9 | Leading ≥ 120% | Of type size. Flag anything below 120% |
| G10 | Baseline grid present | All text aligns to a shared horizontal rhythm across columns |
| G11 | Grid breakage intentional | Where grid is violated, is the violation announced (framed, separated)? |
| G12 | Gutters ≥ 2 ems | Proportional to text size. Must prevent eye-jumping |

### 3. Run the Archetype Checklist

First, identify which archetype the layout is trying to be. If it cannot be named, flag as **FAIL A0: archetype unidentifiable**.

| # | Check | Rule |
|---|---|---|
| A0 | Archetype identified | Data, specimen, Merz, or prose — content type must match |
| A1 | Governing rules satisfied | Per-archetype rules from four-archetypes.md |
| A2 | Whitespace doing identifiable work | Every empty region has a named function |
| A3 | Words/numbers/images integrated | Within their eye-frame, not segregated into zones |
| A4 | No covert archetype mixing | If mixed, dominant archetype must be clear |
| A5 | Typographic scale present | Not arbitrary sizing |
| A6 | Figures placed by grid logic | Not eyeballed |
| A7 | Reading rhythm matches content | Slowed for poetry, sustained for prose |

### 4. Report

Format:

```
## Validation: [target]

### Grid Infrastructure
G1  PASS  Page proportion: 2:3 (vault layout)
G2  FAIL  Margin canon not stated — margins appear eyeballed
         → src/styles/vault/vault-tokens.css:42
...

### Archetype Coherence
A0  PASS  Multi-column prose spread
A1  PASS  Line length, leading, margin proportions all within range
A2  FAIL  Annotation column whitespace is residual — no clear function
         → src/layouts/BlogPost.astro:87
...

### Summary
Grid: 10/12 passed
Archetype: 6/8 passed
Status: [PASS | NEEDS WORK | FAIL]
```

A target passes overall only if zero FAIL results. "NEEDS WORK" if 1–3 failures. "FAIL" if 4+.
