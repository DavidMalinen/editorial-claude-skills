# Editorial Skills for Claude Code

A composable set of [Claude Code skills](https://docs.anthropic.com/en/docs/claude-code/skills) for editorial design — grids, typography, layout archetypes, and data visualization. Rooted in the traditions of Tschichold, Muller-Brockmann, Bringhurst, and Tufte.

## What These Skills Do

Claude Code skills are structured instructions that give Claude domain expertise it wouldn't otherwise have. These skills teach Claude how to construct, critique, and fix editorial layouts using named principles from graphic design history rather than vague aesthetic intuition.

When you invoke a skill, Claude loads the relevant reference material and follows a defined protocol — checking your layout against specific rules (Van de Graaf margins, Bringhurst line metrics, Tufte's data-ink ratio) and reporting findings with file:line references.

## Skills Included

### `editorial` (orchestrator)

The main entry point. Composes the three specialist skills below into action-oriented commands:

| Command | What it does |
|---|---|
| `validate [target]` | Post-change pass/fail against grid + archetype checklists |
| `critique [target]` | Design review with named violations, severity scores, and fixes |
| `audit` | Site-wide sweep across all layout and page files |
| `typography [target]` | Focused type check: scale coherence, line metrics, baseline grid |
| `dataviz [target]` | Data visualization critique using Tufte principles |
| `polish [target]` | Run critique, then apply fixes automatically |
| `construct [target]` | Guided new layout: proportion, margins, grid, scale, archetype |

### `editorial-grid` (structural infrastructure)

The grammar underneath every layout: page proportion, margin canon, modular grid, baseline rhythm, typographic scale, character/line metrics. Draws from:

- **Van de Graaf canon** — 2:3:4:6 margin construction
- **Muller-Brockmann** — 8-32 field modular grids
- **Gerstner** — morphological compound grids
- **Bringhurst** — 45-75 character line measure, classical type scale
- **Tschichold** — medieval margin framework, 2:3 page geometry

### `spread-archetypes` (compositional grammar)

Four canonical archetypes, each with its own lineage, governing rules, and failure modes:

- **Data spread** — Isotype + Swiss + Tufte. Quantitative information made visually honest.
- **Ratio/specimen spread** — Bodoni + Tschichold + Weingart + Bill. Proportion and type as aesthetic objects.
- **Fragmented Merz spread** — Schwitters + Dada + Lissitzky + Bauhaus. Typography as autonomous composition.
- **Multi-column prose spread** — Medieval canon + Tschichold + Muller-Brockmann + Bringhurst. Sustained reading at scale.

Includes cross-cutting systems for active whitespace, static/dynamic axis theory, and the 1+1=3 effect.

### `tufte-viz` (data visualization)

Applies Edward Tufte's principles to design and critique data visualizations:

- **Data-ink ratio** — maximize information per unit of ink
- **Graphical integrity** — lie factor, honest baselines, proportional representation
- **Chartjunk elimination** — remove decoration that doesn't carry data
- **Small multiples** — same structure, data varies, comparison effortless
- **Analytical design** — the 6 principles from *Beautiful Evidence*
- **Sparklines** — word-sized, data-intense inline graphics
- **Layering & separation** — visual hierarchy without spatial segregation

## Installation

### 1. Copy the skills directory

Copy the `.claude/skills/` directory into your project:

```bash
# From your project root
cp -r path/to/editorial-skills/.claude/skills/ .claude/skills/
```

Your project should end up with:

```
.claude/
  skills/
    editorial/
      SKILL.md
      references/
        validate.md
        critique.md
        audit.md
        typography.md
        dataviz.md
        polish.md
        construct.md
    editorial-grid/
      SKILL.md
      references/
        grid-construction.md
        asymmetric-balance.md
    spread-archetypes/
      SKILL.md
      references/
        four-archetypes.md
        whitespace-and-axis.md
    tufte-viz/
      SKILL.md
      references/
        tufte-principles.md
        analytical-design.md
```

### 2. Use the skills

In Claude Code, invoke the editorial skill with a command:

```
/editorial critique src/layouts/BlogPost.astro
/editorial typography src/pages/index.astro
/editorial dataviz src/components/Chart.astro
/editorial audit
/editorial construct new-landing-page
```

Or invoke the specialist skills directly:

```
/editorial-grid           # Grid construction and critique
/spread-archetypes        # Archetype selection and critique
/tufte-viz                # Data visualization design and critique
```

## Adapting to Your Project

The skills reference project-specific paths and layout systems in `editorial/SKILL.md` (the "Design Token Awareness" and "Layout System Awareness" sections). Update these to match your project's token file locations, layout systems, and naming conventions.

The specialist skills (`editorial-grid`, `spread-archetypes`, `tufte-viz`) are project-agnostic — they encode design principles, not file paths.

## Principles, Not Rules

These skills encode traditions, not laws. They name the principle being violated so you can decide whether the violation is intentional and earned, or accidental and costly. A layout that breaks Van de Graaf's margin canon deliberately reads as modern; one that breaks it accidentally reads as amateur.

## License

MIT
