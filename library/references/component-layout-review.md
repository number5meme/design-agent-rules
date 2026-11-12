# Component and Layout Review

For component composition, mobile layout, variable binding, and design file verification; choose check items by this change.

## Components and Instances

- Before reuse, check component semantics, size constraints, exposed properties, and built-in entry points, to avoid assembling duplicate back buttons, titles, search, or bottom bars.
- Reuse the smallest complete structure that serves the current purpose; do not force a component in just because a search found it. Do not mechanically forbid legitimate reuse of sub-components such as rows and cells.
- Check whether nested text and icons still hold default placeholders, and replace them per real use; repeated items need not have invented content just to differ.
- For shared changes, evaluate the main component first, and use instance overrides for local differences; before changing a main component, confirm the impact on other instances and keep justified exceptions.
- Distinguish content-driven, parent-driven, and fixed sizing, and check clipping and blank space in nested containers; do not fix every overflow by auto-growing.

When reading complex instances, reuse existing property mappings first and dig only into necessary unresolved subtrees; stop expanding once the needed content is obtained. Hide optional slots or switch variants per scenario; do not invent data to keep slots filled.

## Targeted Edits and Comparison

When the user specifies a file or object, locate that target first and read the content, properties, and layout relationships relevant to this change; do not modify other objects based on similar names. Before changing, define the objects, properties, and related scope allowed to change, and choose parents, siblings, or other instances as comparisons by impact; small revisions do not require full snapshots.

After changing, confirm together that the target meets requirements, necessary linked changes respect constraints, and comparison objects have not changed unexpectedly. Text edits causing width, line-break, or container height changes may be reasonable; do not mechanically require every property other than text to stay unchanged. When a main component is updated, instances expected to be affected cannot serve as comparisons that should stay unchanged.

## Diagnostics and Design Intent

Whitespace ratio, out-of-bounds, and alignment warnings are leads for locating problems, not defects in themselves. Judge with the actual screen, reading order, and layout purpose; intentional whitespace, image bleed, and overlays can have a reasonable basis. After finding a problem, fix the cause; do not auto-resize with clearing warnings as the goal, and do not fixedly ignore deviations within some pixel threshold.

## Mobile Layout

- Define the relationship among system areas, content scroll areas, fixed actions, and bottom navigation; safe areas use target platform and actual environment values.
- Let the first screen express the current task, and arrange entry points by frequency and operating scenario; keep similar titles at a consistent semantic level, without forcing the same font size across all pages.
- For ordinary content, prefer clear spacing ownership, avoiding duplicate parent and child padding; full-width images, overlays, and independent scroll areas may use different containers.
- Check bottom bar and fixed CTA occlusion, reachability of the last content, and state restoration after switching pages. Navigation appearance, count, and capitalization are decided by the project.

## Variables, Styles, and Modes

Distinguish variable definitions, node bindings, theme/density modes, and instance overrides. Read actual identifiers and supported types, and check bindings. After theme switching, check resolved values, local overrides, and readability; a variable existing does not mean the node is bound. Register the primary data location and version per the project handoff. Check compatibility of variable types with target properties; set theme modes on a common parent first and check local overrides, and handle switching resolved modes and changing bindings separately. Confirm the precedence of shared styles and local values in the actual tool, avoiding ineffective overrides.

## Verify by Impact

| Change | Applicable checks |
|---|---|
| Structure, size, spacing | Parent/child constraints, overflow, clipping, and scrolling; view the rendering when structural checks cannot explain the screen |
| Copy, type, instance content | Long text wrapping, missing glyphs, default placeholders, button sizes, and data meaning |
| Color, material, mode | Actual rendering, contrast, local overrides, and background changes |
| Full area or page | Review structure and screen together; runnable files additionally verify key behavior |

Consecutive related changes can be reviewed together. When checks pass and nothing new has changed, do not retest; on failure, fix or change approach based on evidence. Screenshots must actually be viewed; when visual inspection is not possible, state that it is unverified.
