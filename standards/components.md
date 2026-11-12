# Project Shared Components

Applies to building or modifying reused interfaces and flows. Maintain components within the project first; validate cross-project reuse per [Knowledge Governance](../knowledge/README.md), and do not publish a standalone component package by default.

## Component Overview

For a new UI or frontend project, or a new module in an existing project that includes multiple pages, views, or repeated interaction units, write or update a short component overview for the affected scope before building the first representative screen. Keep it in the existing design record (or the combined record for a small task); extend an existing overview rather than creating a duplicate. Local edits do not require rewriting the whole project overview. List each candidate component, its responsibility, the pages or locations expected to use it, and the variants or states those uses require. Link an existing component when it already fits. If there are no reuse candidates, one sentence is enough.

After checking the representative screen, revise the candidates against actual usage. Promote confirmed shared components through [Finding and Reusing](#finding-and-reusing). Keep implementation locations and verified uses in the project component inventory or handoff mapping.

## Finding and Reusing

Before modifying, locate the project's component directory, shared styles, variables, and call sites, and check actual usage. Reuse an applicable existing component directly; keep differences between components that look similar but differ in semantics. A spec description alone, copied code, or layered overrides do not mean a stable shared implementation exists.

When using a code component library, query the components, variants, properties, and composition patterns available in the project's actual installed version before finalizing the component overview or implementation. Read only the relevant documentation or source; use an available library query tool when useful, without requiring one. Do not infer API support from another version's examples.

Prefer supported theme tokens, properties, and composition for customization. If a real gap requires copying library source, check licensing and record the source version, local changes, and who or what project area maintains the copy in the existing component inventory or handoff record. Treat it as a locally maintained implementation, not a library reference that automatically receives upstream fixes.

When a shared implementation is missing, extract the components reused in this task according to the delivery form: in design files, create main components, instances, styles, or equivalent structures the tool supports; in a codebase, save them to the existing component directory and wire them into the relevant pages. Both include necessary variants, states, and brief usage notes; do not just build a library while continuing to use per-page copies. Design-file-only tasks do not add a code library, one-off content is not forcibly abstracted, and small revisions do not expand into a project-wide refactor.

## Extracting from Completed Pages

1. Limit migration to pages named by the user or already established by the task. If the scope is unclear, propose a list of pages and get user confirmation before editing. Inventory those pages. List each candidate, its usage locations, and differences in appearance, state, and behavior. Extract a new shared component only for two or more uses with the same purpose and interaction semantics. Two uses on one page count. A single use may adopt an existing component. Keep visually similar elements with different purposes separate.
2. Classify differences as supported variants, existing defects, or unresolved questions. Check current project decisions before merging. Leave ambiguous cases separate until resolved. Capture the affected artboards or screens before migration. For interactive prototypes and runnable implementations, also exercise the relevant interactions and record their outcomes.
3. Follow [Finding and Reusing](#finding-and-reusing) to create or reuse the shared implementation. Replace every in-scope copy selected for migration with an actual instance or call. Check consumers across the project before removing a superseded copy. This search does not expand the agreed migration scope. If an old implementation still serves out-of-scope pages, retain it and record those locations.
4. Compare the same content and states before and after migration. In design files, compare the migrated instances with the originals at the same artboard dimensions and verify that each instance links to the intended component. In runnable implementations, compare screenshots at matching viewport sizes. For interactive prototypes and runnable implementations, repeat the baseline interactions and compare outcomes. Interaction testing is inapplicable to static artwork. Correct unintended differences. Record an intentional change only when supported by an existing project decision or explicit user approval. Mark any check you could not perform as unverified.
5. Update the [handoff component mapping](../templates/project/handoff.md#component-mapping-when-reuse-is-involved) or the project component inventory it links to with the implementation, variants, and actual usage locations. Map each removed copy's former file or artboard location to its replacement. Link an existing migration diff if it already shows that mapping. Link verification results and identify remaining legacy uses.

## External Implementation Selection

Choose components by target platform, product context, and usage habits. Native apps follow the corresponding platform conventions; web pages and brand showcases may have custom visuals. Custom components still need applicable semantics, focus, keyboard, dismissal, back navigation, and state feedback; being native or looking like a system component does not by itself prove quality.

For complex interactions such as pop-ups, menus, and drag-and-drop, first check whether existing native controls, project components, and dependencies satisfy semantics, focus, keyboard, dismissal, and nesting behavior; do not merely replicate appearance. When there is a real gap, compare current maintenance status, platform compatibility, accessibility, dependency cost, and licensing, and choose an implementation that can hook into existing variables and interfaces.

When an existing solution satisfies the task, do not replace it because a reference recommends another library; do not add dependencies for simple styles; base long-list optimization on actual performance, and do not force virtualization at a fixed item count. New implementations must still be wired into the project's shared components and verified.

## Responsibilities and Variants

- A component owns both the agreed appearance and behavior: typography, color, icons, size, states, and, where applicable, title placeholders, spacing, safe areas, scroll avoidance, dismissal, and focus behavior.
- Define the space each component and page owns, avoiding the same spacing added repeatedly by the parent container, the last content item, and the action area; allow the layout to grow naturally as content grows.
- Use explicit variants for primary, secondary, destructive, and icon actions; consistency does not require all buttons to look the same. When a page has a real exception, record the conditions for use rather than arbitrarily overriding shared styles.
- The same business flow shares UI and state logic, with the entry point passing in the object, candidate scope, identity, selection, and return context. A shared implementation does not expand permissions or data scope, and does not merge flows with different business meaning.

## Current Primary Records

The project design record maintains the currently valid visual and layout decisions, design variables or code variables maintain actual parameter values, and the component mapping in the handoff record points to implementations, variants, and usage entry points; the three are linked, without copying values repeatedly.

On change, update the corresponding primary record, and move superseded decisions to history or clearly mark them invalid. Old rules must not be listed as current requirements alongside new ones; references and history serve only as a basis for tracing.

## Revisions and Recurring Issues

With every fix, also check:

- **Layout impact**: whether the parent container, adjacent content, positioning, scroll placeholders, and safe areas produce overlap, gaps, clipping, or occlusion.
- **Style and behavior**: whether the changed part follows the shared variants and the typography, color, icons, size, spacing, and states of related content; a position change must not lose the original material, actions, or feedback.

When the same kind of issue recurs, first locate the shared structure, independent branches, style override order, and event handling, and confirm why the last fix did not cover it or stopped working. Within the affected scope, consolidate duplicate implementations and clean up invalid overrides; do not by default add another rendering wrapper or style patch. When a structural change beyond the authorized scope is needed, explain the impact and continue fixes that can be completed independently.

Verify per [Related Scope and Evidence](quality.md#related-scope-and-evidence); keep separately verifiable evidence that the component was saved, the page uses it, and its behavior was tested.
