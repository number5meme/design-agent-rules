# Style Consistency Review

When choosing or updating a style template, check variables, component notes, and screens against the rules the project actually adopts. When only a style direction is specified, do not use the reference's specific colors or layout as acceptance criteria; check explicitly replicated dimensions against the target.

| Check item | Method |
|---|---|
| Typeface and weight | Check against variables and component notes, unifying values for the same semantic role; name different variants separately |
| Background and foreground | Record usage, background, and measured ratio per [Color Pairing](../../standards/defaults.md#color-pairing) |
| Line height and fallback fonts | Specify units and font conditions; check actual wrapping, clipping, and readability |
| Responsive breakpoints | Maintain one breakpoint mapping, check collapse behavior, and check threshold widths |
| Interaction states | Check applicable states by desktop, touch, and keyboard usage scope |
| Reference scope | Distinguish promotional pages from in-app interfaces, and host pages from third-party controls; record observations and inferences separately |
| Variable references | Check names, types, reference targets, and mode-resolved values; handle missing references |

Handle conflicts per [Style Selection](../../standards/workflow.md#style-selection). Check against the project's valid values; do not automatically judge reference differences as defects; save decisions and verification in their respective primary records.

Local materials use valid project paths; remote design sources keep an accessible location, version, and necessary evidence. For structure, see the [Style Template](../../templates/style-template.md).

## Migrating an Existing Theme

Inventory hard-coded theme values at actual usage sites. Map each to an existing semantic role or define a missing role with a clear purpose. Migrate consumers in small component batches. After each batch, render all supported themes and check contrast, hover, focus, disabled states and responsive layouts.
