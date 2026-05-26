---
name: editorial
description: |
  Validate, critique, audit, polish, and construct editorial layouts by composing
  rules from the editorial-grid, spread-archetypes, tufte-viz, and whitespace/axis
  systems. Use this skill when:
  (1) Checking recent layout changes against grid + archetype rules
  (2) Reviewing a page for structural or compositional violations
  (3) Auditing all layouts site-wide for consistency
  (4) Running a focused typography check (scale, line metrics, baseline)
  (5) Fixing layout issues identified by critique
  (6) Building a new layout from scratch with guided decisions
  (7) Designing or critiquing data visualizations (charts, sparklines, dashboards)
  Not for backend tasks.
user-invocable: true
argument-hint: "[validate|critique|audit|typography|dataviz|polish|construct] [target]"
---

# Editorial Toolkit

Composes rules from `editorial-grid`, `spread-archetypes`, and `tufte-viz` into action-oriented commands that check, review, fix, and build editorial layouts and data visualizations.

## Source Skills

This skill does not duplicate its source material. It references:

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
| `validate [target]` | Check | Post-change pass/fail against grid + archetype checklists | [references/validate.md](references/validate.md) |
| `critique [target]` | Evaluate | Design review with named violations and severity | [references/critique.md](references/critique.md) |
| `audit` | Evaluate | Site-wide sweep across all layouts | [references/audit.md](references/audit.md) |
| `typography [target]` | Evaluate | Focused type check: scale, metrics, baseline, rhythm | [references/typography.md](references/typography.md) |
| `dataviz [target]` | Evaluate | Data visualization critique using Tufte principles | [references/dataviz.md](references/dataviz.md) |
| `polish [target]` | Fix | Run critique, then apply fixes | [references/polish.md](references/polish.md) |
| `construct [target]` | Build | Guided new layout: proportion → margins → grid → scale → archetype | [references/construct.md](references/construct.md) |

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
