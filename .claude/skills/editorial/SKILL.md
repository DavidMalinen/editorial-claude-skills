---
name: editorial
description: |
  Validate, critique, audit, polish, and construct editorial layouts by composing
  rules from the editorial-grid, spread-archetypes, tufte-viz, and whitespace/axis
  systems. Use this skill when:
  (1) Naming the argument before designing (elenchus) — the foundation for all
      editorial work that argues rather than displays
  (2) Checking recent layout changes against grid + archetype rules
  (3) Reviewing a page for structural or compositional violations
  (4) Auditing all layouts site-wide for consistency
  (5) Running a focused typography check (scale, line metrics, baseline)
  (6) Fixing layout issues identified by critique
  (7) Building a new layout from scratch with guided decisions
  (8) Designing or critiquing data visualizations (charts, sparklines, dashboards)
  Not for backend tasks.
user-invocable: true
argument-hint: "[elenchus|validate|critique|audit|typography|dataviz|polish|construct] [target]"
---

# Editorial Toolkit

The grid, the archetypes, the Tufte principles — these are the grammar of editorial layout. But grammar without something to say builds correct surfaces that carry no argument. For editorial work that argues — essays, investigations, manifestos, any spread where the form encodes the structure of thought — the grammar needs a named argument underneath it. Elenchus is what names it: question, antinomy, answer, form-assignment. Everything else in this toolkit departs from there.

For content that displays rather than argues (documentation, indexes, data dashboards, utility surfaces), the grammar skills operate directly. No argument needs naming because none is being made.

Composes rules from `elenchus`, `editorial-grid`, `spread-archetypes`, and `tufte-viz` into action-oriented commands that check, review, fix, and build editorial layouts and data visualizations.

## Source Skills

This skill does not duplicate its source material. It references:

- `../elenchus/SKILL.md` — the pre-design method: question, antinomy, answer, form-assignment, refusal-to-design
- `../elenchus/references/hofmann-construction-grid.png` — construction grid reference (the grid is the premise)
- `../elenchus/references/hofmann-exposition-poster.png` — the figure derived from the grid (the conclusion)
- `../editorial-grid/SKILL.md` — grid infrastructure (proportion, margins, modular grid, baseline, scale, metrics)
- `../editorial-grid/references/grid-construction.md` — constructions, ratio tables, character-count tables, baseline math
- `../editorial-grid/references/asymmetric-balance.md` — tension, counterweight, the grid-and-asymmetry pair
- `../spread-archetypes/SKILL.md` — four archetype grammars (data, specimen, Merz, prose)
- `../spread-archetypes/references/four-archetypes.md` — full rules, lineage, failure modes per archetype
- `../spread-archetypes/references/whitespace-and-axis.md` — active whitespace, static/dynamic axis, 1+1=3
- `../tufte-viz/SKILL.md` — Tufte visualization workflow (design + critique), data-ink ratio, chartjunk, small multiples
- `../tufte-viz/references/tufte-principles.md` — core principles: lie factor, data-ink, chartjunk, integrity, density
- `../tufte-viz/references/analytical-design.md` — 6 analytical design principles, sparklines, layering, micro/macro, range-frames

Load the relevant source references when executing each sub-command (specified per-command below).

## Commands

| Command | Category | Description | Reference |
|---|---|---|---|
| `elenchus [target]` | Foundation | Name the argument before designing: question, antinomy, answer, form | [references/elenchus.md](references/elenchus.md) |
| `construct [target]` | Build | Guided new layout — routes through elenchus for argumentative content | [references/construct.md](references/construct.md) |
| `validate [target]` | Check | Post-change pass/fail against grid + archetype + argument checklists | [references/validate.md](references/validate.md) |
| `critique [target]` | Evaluate | Design review: structural violations, argument coherence | [references/critique.md](references/critique.md) |
| `audit` | Evaluate | Site-wide sweep across all layouts | [references/audit.md](references/audit.md) |
| `typography [target]` | Evaluate | Focused type check: scale, metrics, baseline, rhythm | [references/typography.md](references/typography.md) |
| `dataviz [target]` | Evaluate | Data visualization critique using Tufte principles | [references/dataviz.md](references/dataviz.md) |
| `polish [target]` | Fix | Run critique, then apply fixes (preserves argument-form binding) | [references/polish.md](references/polish.md) |

## Routing Rules

1. **No argument**: render the command table above. Ask what the user wants to do.
2. **First word matches a command**: load its reference file and follow its instructions. Everything after the command name is the target.
3. **First word doesn't match**: treat the full argument as a target and run `critique` by default.

## Target Resolution

Resolve the target to a concrete file path before executing any command:

- `"the homepage"` → `src/pages/index.astro` or equivalent
- `"blog layout"` → `src/layouts/BlogPost.astro` or the vault/swiss layout file
- `"this page"` → the file currently under discussion
- A file path → use directly
- No target specified (except `audit`) → ask

For `audit`, no target is needed — it scans all layout and page files.

## Shared Protocol

Every command follows this sequence:

1. **Resolve target** (or scope for audit)
2. **Load source references** (specified per-command)
3. **Read the target's CSS and markup** — identify the design token files, layout files, and component files involved
4. **Execute the command protocol** (per reference file)
5. **Report** with file:line references for every finding

### Argument Awareness

Before executing any command on a layout, determine whether the content *argues* or *displays*:

- **Argues**: personal essays, philosophical writing, investigative articles, manifestos, any spread where the form encodes the structure of thought. These are elenchus territory.
- **Displays**: documentation, indexes, data dashboards, navigation, utility surfaces, transactional flows. These go straight to the grammar skills.

For content that argues:

1. Check whether the elenchus has been done — are the three sentences (question, antinomy, answer) stated? Are the four form-assignments (architecture, tension, prose, construction) present?
2. If elenchus has not been done, recommend running `elenchus` before proceeding. For `construct`, this is mandatory — the protocol departs from elenchus when the content argues. For `critique`, `validate`, and `polish`, note the absence as a structural finding but proceed with the grammar-level review.
3. When the elenchus exists, check argument-form coherence: does the layout's structure still honor the binding between argument parts and their assigned forms? A `polish` that fixes line metrics must not break the tension form's refusal to resolve. A `critique` that names a grid violation must note whether the violation is serving the argument.

For content that displays, skip this section entirely. No argument needs naming because none is being made.

### Design Token Awareness

This project uses a layered token system in `src/styles/vault/vault-tokens.css`:
- Layer 1: primitive palette
- Layer 2: fluid type scale, spacing grid, layout dimensions
- Layer 3: semantic tokens
- Layer 4: theme modes

When checking values, trace them through the token layers. A hardcoded `16px` might be correct if it matches the token system's base; flag it only if it deviates from the declared scale.

### Layout System Awareness

Two layout systems coexist:
- **Vault**: 5-column editorial (`margin | content 40rem | gutter 2rem | annotation 14rem | margin`)
- **Swiss**: 12-column CSS grid with span utilities

Blog posts declare `pageLayout: 'vault' | 'swiss'` in frontmatter. Commands must check against the correct system.
