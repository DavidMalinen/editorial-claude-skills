# Critique

Design review. "What's wrong with this layout, and why?" Names specific violations, traces each to its tradition, scores severity, and recommends fixes. Does not edit files.

## When to Use

When a layout feels off but you can't name why. When reviewing someone else's layout work. When you want a full diagnosis before deciding what to fix.

## Load These Source References

- `../../editorial-grid/SKILL.md` — grid critique workflow (steps 1–7)
- `../../editorial-grid/references/grid-construction.md` — ratio tables, construction methods
- `../../editorial-grid/references/asymmetric-balance.md` — tension diagnosis, dead-layout checklist
- `../../spread-archetypes/SKILL.md` — archetype critique workflow (steps 1–5)
- `../../spread-archetypes/references/four-archetypes.md` — per-archetype failure modes
- `../../spread-archetypes/references/whitespace-and-axis.md` — active whitespace, axis theory, 1+1=3

## Protocol

### 1. Read the Target Thoroughly

Read all layout, style, and content files. Build a mental model of:
- Which layout system is in use (vault or swiss)
- What design tokens are applied
- What the content structure is (headings, body, figures, annotations)

### 2. Identify the Archetype

Name the archetype the layout is trying to be: data, specimen, Merz, or prose. If unnameable, note this as the first finding — a confused archetype is the most common root cause.

If the layout mixes archetypes, identify the dominant one and assess whether secondary elements support or undermine it.

### 3. Run the Grid Critique

Walk through the editorial-grid critique workflow:

1. **Page proportion** — Can you name it? Does it fit the content's reading mode?
2. **Margin canon** — Bottom largest? Outer > inner? Ratio identifiable?
3. **Modular grid** — Do elements align to consistent divisions? Images sized to integer column widths?
4. **Typographic scale** — List all sizes. Single modular scale with named ratio, or ad-hoc?
5. **Line metrics** — Characters per line within range? Leading ≥ 120%? Gutters adequate?
6. **Baseline alignment** — Shared horizontal rhythm across columns, or independent drift?

### 4. Run the Archetype Critique

Walk through the spread-archetypes critique workflow:

1. **Archetype coherence** — Does the layout honor its archetype's governing rules?
2. **Failure mode check** — Check against the specific failure list for the identified archetype
3. **Whitespace function** — For every empty region: what is it doing? "Nothing" = residual
4. **Lineage check** — Does the spread honor or violate its tradition? Intentional violation is fine; accidental is the most common failure

### 5. Run the Tension Diagnosis

From asymmetric-balance.md:

1. **Symmetric or asymmetric?** Be honest — centered headlines + centered images = symmetric
2. **If symmetric: chosen or inherited?** Could the content support asymmetric arrangement?
3. **If asymmetric: is there tension?** Or just unbalanced — heavy on one side, no force relationship?
4. **Whitespace as counterweight or residue?** Squint at empty regions — are they doing work?
5. **Entry point and path** — Does the eye have a clear way in and through?

### 6. Run the Axis Check

From whitespace-and-axis.md:

1. **Static or dynamic axis posture?** Does it match the content's emotional posture?
2. **If hybrid: is the static base dominant?** Dynamic disruption should be purposeful and local
3. **1+1=3 trap** — Are heavy adjacent elements creating phantom visual elements in the gutters?

### 7. Score and Report

For each finding, assign severity:

- **P0 — Structural**: breaks reading or comprehension (wrong archetype, lines >75 char, no baseline grid, top margin > bottom)
- **P1 — Significant**: weakens the layout (ad-hoc scale, residual whitespace, symmetric by default)
- **P2 — Refinement**: correct but underperforming (gutter slightly narrow, scale present but could be tighter, axis posture unambitious)

Format:

```
## Critique: [target]

### Archetype
[Name] — [whether content type matches]

### Findings

**P0 — Structural**
1. [Finding]: [explanation tracing to specific tradition/rule]
   → [file:line]
   Fix: [specific recommendation]

**P1 — Significant**
...

**P2 — Refinement**
...

### Strengths
- [What the layout does well — name the principle it honors]

### Summary
[1-2 sentences: the core issue and the recommended path forward]
```
