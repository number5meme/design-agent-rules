# Frontend Implementation Method

Read by task: [Workflow](workflow.md) · [Method](design.md) · [Acceptance](quality.md). For local edits, read only the affected sections.

## Reading and Breakdown

Read the affected pages' structure, shared components, variables, adaptation constraints, and states, and view the actual rendering. Go deeper into nodes as needed; avoid guessing structure from screenshots alone or reading all nodes without bounds.

| Design content | Implementation |
|---|---|
| Available code components | Map semantics, variants, properties, and states; check after reuse |
| Text and forms | Keep semantics and actual interactions; check layout by font and content |
| Images and complex textures | Export suitable resources; check cropping, resolution, and transparency |
| Icons and vectors | Prefer reusing project assets; export separately when necessary |
| Simple surfaces, borders, and gradients | Implement with styles |

A full-page screenshot cannot replace a runnable page. Link assets to nodes and files by role, avoiding lost resources or duplicate exports.

## Layout and Style Mapping

Distinguish content-driven, parent-allocated, and fixed sizes; prefer the corresponding layout for flowing content, and position overlays and decorations by relationship. Static coordinates cannot be taken directly as complete responsive rules; fill in unknown adaptive behavior based on content and scope.

Check font loading, weight, line-height units, letter spacing, line breaks, and fallback fonts. For Chinese and other large-character-set web fonts, also check actual resource size and loading scope; choose strategies such as system fallback or splitting by glyph or language based on brand, content, and performance needs. Static headings may be evaluated for subsetting, but dynamic body text and user input must not cover only the mockup's characters; verify missing glyphs, load failures, and line breaks and layout after font swaps, and do not fix weight, color, and typesetting values based on font name or language alone. Handle whole-element opacity, fill opacity, and gradient color opacity separately, avoiding effects on child content or double stacking.

Prefer reusing existing variables and component interfaces. Implement interactions, loading, failure, and focus as agreed; when the design file lacks business behavior, do not invent it from appearance. For component wiring and related checks, see [Shared Components](../../standards/components.md).

## Web Platform Capabilities and Compatibility

Before adding custom browser logic or a dependency, follow [External Implementation Selection](../../standards/components.md#external-implementation-selection) and check whether native HTML, CSS, or browser APIs meet the required behavior. Keep an existing suitable implementation; adopting a newer feature is not a reason to expand the task.

For a feature being introduced or changed, check current guidance for the specific capability and compare its support with the project's target browsers and versions. Use established project requirements; if none exist, record a proposed support scope and resolve any uncertainty that would materially change the implementation. A general availability label or success in the current browser does not establish project compatibility.

When a target environment lacks support, provide a suitable fallback or progressive enhancement that preserves core content and operations. Use feature detection where appropriate; if no acceptable fallback exists, choose another implementation or resolve the support decision before relying on the feature. Retrieve only relevant guidance when needed, and verify the normal and fallback paths per [Browser and Locale Checks](quality.md#browser-and-locale-checks).

## Version Sync

When syncing existing versions, check source and target, the source version baseline, target changes to keep, and release scope; do not ask again when the context is clear, and confirm first when the direction is materially ambiguous. Merge by actual differences, check conflicts and dependencies, and do not default to overwriting whole directories or two-way publishing. Verification covers synced content, kept content, and their interaction, then update the existing version record.
