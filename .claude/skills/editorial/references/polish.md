# Polish

Fix mode. Runs a compressed critique internally, then applies the fixes. The action counterpart to critique — this command edits files.

## When to Use

After critique has identified issues and the user wants them fixed. When you want a one-command "make this better" pass. Before shipping layout work.

## Load These Source References

- `../../editorial-grid/references/grid-construction.md` — construction methods, tables for correct values
- `../../editorial-grid/references/asymmetric-balance.md` — tension and counterweight fixes
- `../../spread-archetypes/references/four-archetypes.md` — archetype-specific corrections
- `../../spread-archetypes/references/whitespace-and-axis.md` — whitespace and axis fixes

## Protocol

### 1. Compressed Critique

Run the critique protocol silently (do not output the full critique report to the user). Collect all findings into an internal work list sorted by severity: P0 → P1 → P2.

### 2. Triage

Classify each finding:

- **Fixable now**: can be corrected by editing CSS, markup, or tokens
- **Needs decision**: requires a design choice (e.g., which archetype to commit to, which scale ratio to adopt)
- **Structural**: requires layout restructuring beyond CSS tweaks

Present findings that need decisions to the user before proceeding. Fix the rest.

### 3. Fix Priority Order

Work through fixes in this order:

1. **Scale and tokens** — Fix the type scale first. If sizes are ad-hoc, establish a coherent scale in the token file. Everything else depends on this.
2. **Line metrics** — Adjust character count (via `max-width` in `ch` or container width), leading, and gutter width.
3. **Baseline grid** — Align vertical spacing to the baseline unit. Fix paragraph spacing, heading spacing, figure heights.
4. **Margins** — Correct margin proportions if the canon is violated (bottom ≥ top, outer ≥ inner).
5. **Whitespace** — Convert residual whitespace to active whitespace. Remove empty regions that serve no function; expand regions that need breathing room.
6. **Asymmetric tension** — If the layout is symmetric by default (not by choice), introduce asymmetric counterweight. Shift elements off-center within the grid.
7. **Archetype alignment** — Fix archetype-specific violations (e.g., figures placed mid-column in a prose spread, decorative color in a data spread).

### 4. Token-First Approach

Prefer fixing values in the token system over fixing them in component styles:
- If the token file has the right value but the component isn't using it → change the component to reference the token
- If the token file is missing a needed value → add it at the correct layer, then reference it
- If the component has a hardcoded override that contradicts the token → remove the override unless there's a stated reason

### 5. Verify After Fixing

After all edits, run the validate checklist against the modified files. Report the before/after score.

### 6. Report

```
## Polish: [target]

### Changes Made
1. [What changed] — [why, naming the rule]
   → [file:line]

### Decisions Deferred
- [Issue that needs user input] — [options]

### Before / After
Grid: [n]/12 → [n]/12
Archetype: [n]/8 → [n]/8

### Remaining Issues
[Anything that couldn't be fixed without structural changes]
```
