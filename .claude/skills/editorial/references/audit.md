# Audit

Site-wide sweep. Scans all layout and page files for grid infrastructure and archetype violations. Produces a ranked report across the entire project.

## When to Use

Periodic health check. Before a major release. When establishing a baseline for editorial quality. When onboarding to an unfamiliar codebase.

## Load These Source References

- `../../editorial-grid/references/grid-construction.md` — ratio tables, construction methods
- `../../spread-archetypes/references/four-archetypes.md` — per-archetype failure modes
- `../../spread-archetypes/references/whitespace-and-axis.md` — whitespace and axis checks

## Scope

Scan all files that define layout structure:

1. **Layout files**: `src/layouts/*.astro`, `src/layouts/**/*.astro`
2. **Page files**: `src/pages/**/*.astro`
3. **Layout components**: `src/components/vault/*.astro`, `src/components/swiss/*.astro`
4. **Style files**: `src/styles/vault/*.css`, any component-scoped `<style>` blocks
5. **Content frontmatter**: `src/content/blog/*.{md,mdx}` — check `pageLayout` field assignment

Exclude `src/layouts/archived/` and `src/archived/` unless explicitly asked.

## Protocol

### 1. Inventory

List every layout-defining file found. Group by layout system (vault vs swiss). Note any files that don't clearly belong to either system.

### 2. Per-File Quick Check

For each file, run a compressed version of the validate checklist. Not the full critique — just the structural essentials:

| Check | What to verify |
|---|---|
| Layout system | Vault or swiss — is it declared and consistent? |
| Proportion | Named or eyeballed? |
| Margin behavior | Bottom ≥ top, outer ≥ inner |
| Scale coherence | All type sizes derivable from one named scale |
| Line length | Body text 45–75 char (single) or 40–50 (multi) |
| Leading | ≥ 120% of type size |
| Archetype | Identifiable? Content type matches? |
| Whitespace | Active or residual? |

### 3. Cross-File Consistency

Check for systemic issues that only appear when comparing files:

- **Token drift**: Are all layouts using the same token layer, or have some diverged to hardcoded values?
- **Scale fragmentation**: Is the same modular scale used across all layouts, or does each file pick its own sizes?
- **Margin inconsistency**: Do vault and swiss layouts share a coherent margin philosophy?
- **Archetype confusion**: Are pages using archetypes that don't match their content type?
- **Baseline rhythm**: Is the baseline unit consistent across layouts that share a reading context?

### 4. Report

```
## Editorial Audit

### Inventory
| File | System | Archetype | Status |
|---|---|---|---|
| src/layouts/BlogPost.astro | vault | prose | 7/8 |
| src/pages/index.astro | swiss | specimen | 5/8 |
...

### Systemic Issues
1. [Issue]: [explanation]
   Affected files: [list]
   Severity: P0/P1/P2

### Per-File Findings
[Only files with failures — skip clean files]

#### [file path]
- [finding] → [line reference]
...

### Health Summary
- Files scanned: [n]
- Clean: [n]
- Needs work: [n] (1–3 failures)
- Failing: [n] (4+ failures)
- Top systemic issue: [one-line summary]
```

### 5. Prioritize

Rank all findings by impact:
1. Systemic issues first (affect multiple files)
2. P0 structural issues per-file
3. P1 significant issues per-file
4. P2 refinements last

Suggest which files to fix first based on: visibility (homepage > deep pages), severity, and cascading benefit (fixing a shared token fixes all consumers).
