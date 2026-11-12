# Style Template (Optional)

Use only when building or reusing a style system; after copying into the project, delete irrelevant sections; not every task needs to fill it in. For actual selection scope and precedence, see [Style Selection](../standards/workflow.md#style-selection).

Local files use resolvable project paths; remote sources record an accessible location, version, and necessary evidence. After copying this template, fix links for the target directory.

## Scope and Sources

- Name, version, date:
- Applicable products, pages, and platforms; non-applicable scenarios:
- Sources, reference versions, and trust scope (official spec/observation/inference):
- Project selection basis (user-specified or autonomously chosen within scope); adopted dimensions, must-keep items, and changeable items:
- Style thesis: in one paragraph, explain how content, hierarchy, and visuals serve the task.

## Variable Primary Record

When a valid variable source exists, link it and add only semantics and usage conditions, without copying all values. Otherwise record the necessary values here; when implementing, define the single valid source, which may be design tool variables, code variables, or this record.

| Semantic name | Value and unit or primary file reference | Usage | Mode/substitution conditions |
|---|---|---|---|

Cover color, typeface, weight, line height, spacing, corner radius, material, and motion as needed. Note relative versus pixel line heights; a substitute font cannot pass for measurements of the original font.

## Components and States

| Component/main component reference | Structure and content | Variables used | Applicable states and behavior | Non-applicable conditions |
|---|---|---|---|---|

Record only changes relative to the existing design system; consider desktop and touch states per platform. Default, selected, focus, processing, and so on need not all be added, but do not write unobserved as nonexistent.

## Responsive and Assets

| Applicable width/device | Layout changes | Type/image handling | Fixed areas and safe areas |
|---|---|---|---|

Maintain only one set of breakpoints; other notes reference it. For assets, list source, cropping, font substitution, and licensing boundaries; business content is still provided by project requirements.

## Conflicts and Overrides

| Conflict dimension | Source of explicit requirement/template/default | Adopted value and basis | Impact scope |
|---|---|---|---|

Override only conflicting dimensions, keeping other valid settings. For internal template contradictions, check sources first; when reversible and evidence is sufficient, choose autonomously and record it; for major ambiguities requiring a user decision, pause only the dependent parts. An undefined value is not 0; do not assume by default that text descriptions or variables are necessarily more authoritative. When technology does not support something, record the approximation and gap, and do not claim an equivalent implementation.

After the user rejects the overall style, mark this template as retired; keep independently confirmed business, brand, content, and delivery requirements. Re-establish direction per [Style Adjustment](../standards/workflow.md#style-adjustment); the current design record keeps only the effective basis.

## Verification and Known Gaps

Link the representative sample, environment, actual rendering, and applicable interaction evidence in the project review record. List uncovered states, platforms, variables, or assets; when updating sources, assess differences first, without automatically overriding project changes.

## Optional Export Record

Requested format and revision, export location, verification result, and known gaps. See [Exporting DESIGN.md](../standards/design-system-export.md#exporting-designmd).
