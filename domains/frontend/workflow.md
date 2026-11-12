# Frontend Implementation Workflow

Read by task: [Workflow](workflow.md) · [Method](design.md) · [Acceptance](quality.md). For local edits, read only the affected sections.

For building new frontends, modifying existing codebases, and design-to-code. Keep the existing tech stack and components; determine delivery scope per [Task Scope](../../standards/task-scope.md); do not add a separate design file or backend by default.

Apply the triggers, timing, and scope in [Component Overview](../../standards/components.md#component-overview). Reuse and update the design team's overview if one exists.

## Choosing a Path by Input

- New build without a design file: determine structure from the user's task and content, form the interface per [Design Judgment](../ui/design.md), and [test the proposed direction](../../library/references/visual-judgment.md#testing-a-proposed-direction) when visual choices are open. Validate representative pages in the implementation; for multiple pages, then expand shared components and necessary states, without requiring another design source first.
- Modifying an existing codebase: locate entry points, shared implementations, current behavior, and task constraints, and modify only the target and necessary linked parts; after verifying within scope, write back to the existing records.
- Existing design file: read and map per the [Implementation Method](design.md), and check actual rendering. Design-to-code by itself does not constitute ongoing dual delivery.

When visual exploration would help, use the [Optional Image Preview Before Implementation](../ui/workflow.md#optional-image-preview-before-implementation) route before coding the representative page. Its selection, continuation, and implementation boundaries apply across the input paths above.

Make explicit the runtime framework, dependencies, and data sources adopted; choose the implementation for new codebases by task complexity, without fixing a tech stack. Keep mock data separate from actual integration; start, build, and required resources are reproducible.

When done, check actual runtime, comparison, and affected branches per [Frontend Acceptance](quality.md).

For theme migrations, use the [theme migration checklist](../../library/references/style-consistency-review.md#migrating-an-existing-theme).
