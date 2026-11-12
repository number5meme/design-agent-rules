# UI Design Workflow

Read by task: [Workflow](workflow.md) · [Method](design.md) · [Acceptance](quality.md). For local edits, read only the affected sections.

For new or redesigned UI pages, multi-page experiences, and new modules in existing projects. Validate a representative sample before expanding when the scope requires expansion; local revisions run only the affected steps. For upfront clarification, capability checks, and revision boundaries, see [General Execution](../../standards/workflow.md).

## 1. Product Judgment, Visual Basis, and Recommended Option
First judge product category, user tasks, and scenarios per [Design Judgment](design.md), map facts and inferences to specific design decisions, and write them into the existing design record. For composite products, define each module's responsibilities.

Apply the triggers, timing, and scope in [Component Overview](../../standards/components.md#component-overview).

When choosing a new visual direction, [test the proposed direction](../../library/references/visual-judgment.md#testing-a-proposed-direction) before building the sample. The [Optional Image Preview Before Implementation](#optional-image-preview-before-implementation) route may support this direction-setting step.

When references are needed, select a small amount of relevant material, and record the dimensions actually adopted and their applicability. References are not only about the look of similar products; also check states, content structure, and asset handling. When a mature brand exists, it leads. For option selection and comparison, follow [Form the Main Approach Through Explicit Reasoning](design.md#form-the-main-approach-through-explicit-reasoning).

The recommended mockup should together resolve in-scope layout, hierarchy, typography, assets, key states, and brand expression. When there are alternatives, use the same core business content, and compare color, layout, density, or interaction per the exploration goal; when comparing only color, keep other conditions fixed, and when comparing structure, show the structural difference. When comparing the feel of operation, switch in a standalone preview with the same size and context; keep comparison controls outside the product UI, and after choosing a direction, wire only the selected implementation into the production pages. Present with actual images or renderable pages, not just style adjectives.

Done when: the actual mockup has a basis, and category needs map to screens/states; the selected direction and reasons are recorded. When the style is rejected, handle it per [Style Adjustment](../../standards/workflow.md#style-adjustment), with execution boundaries following the general rules.

### Optional Image Preview Before Implementation

When visual direction is unresolved or a page needs substantial exploration of composition or visual assets, the Agent may use image generation to preview a representative page before implementing it. Choose this route only when an available tool can reduce the relevant uncertainty; it is not required even for complex pages. For uncertainty about dense tables, forms, dragging, or multi-state behavior, prefer a runnable sample; an image may supplement visual exploration.

Base the preview on the page purpose, real or representative content, information hierarchy, primary actions, existing components, and brand constraints. Inspect the generated image, correct or disregard invented text, data, controls, and impossible layouts, and record only the visual decisions actually adopted in the existing design record. The preview is a visual reference, not proof of implementation feasibility, accurate content, or working interactions.

Within the authorized scope, select the direction and continue implementation without adding a confirmation checkpoint. Pause only for an existing user-requested review, material ambiguity, or a permission boundary. If image generation is unavailable or unhelpful, continue with the design or runnable sample directly.

For code delivery, implement the adopted direction with real text, shared components, responsive layout, and required interaction states; do not use a full-page generated image as the interface. Verify the actual result against the adopted decisions and applicable acceptance items. A generated preview does not satisfy runtime, accessibility, or responsive verification, and does not by itself create a separate design-file or dual-delivery requirement.

## 2. Refine Key Pages
Choose the most representative pages, also covering an information-dense or operation-heavy area. Check real copy, long content, target screens, and core interactions. Validate hard-to-implement layout/motion early.

Express interaction in key pages by delivery type: design files mark states and behavior, interactive prototypes implement the agreed connections, and runnable frontends verify actual gestures, scrolling, and feedback.

Read only interaction sections triggered by the behavior being designed or changed:

- Waiting, feedback, or dismissal: [Buttons, Pop-ups, and Results](interaction.md#buttons-pop-ups-and-results).
- Paging or gestures: [Category and Page Switching](interaction.md#category-and-page-switching).
- Scroll behavior: [Page Scrolling and Top Area Handling](interaction.md#page-scrolling-and-top-area-handling).
- Animation: [Motion Quality](interaction.md#motion-quality).

For a key interaction being defined or changed, use [What to Define for Each Key Interaction](interaction.md#what-to-define-for-each-key-interaction); settle states and interruptions before tuning motion parameters.

Output the applicable selected representative sample, style variables, core component drafts, and actual rendering; add dynamic evidence when runnable interactions need acceptance. Done when: visual direction, readability, and implementation feasibility are specifically checked; note whether it was autonomously selected or user-approved, and do not present autonomous decisions as user approval. After completion, continue in-scope work.

## 3. Expand the Full Experience (Within Current Authorized Scope Only)
Check existing implementations per [Project Shared Components](../../standards/components.md), and extract and wire in missing reused components within this scope. Complete pages, component variants, and applicable states such as normal/empty/loading/error/disabled. Link in-scope core business rules to page or interaction evidence, omitting irrelevant states.

Use real or representative data, including long text, extreme values, and missing content. Confirm asset licensing and font substitution strategy. Put demo controls in a separate review panel.

Done when: agreed pages, states, and core paths are covered with corresponding evidence; open issues are explicitly marked.

## 4. Dual Delivery Alignment (Only When Confirmed by the User)

For confirmed Figma and frontend dual delivery, follow [Figma and Frontend Dual Delivery Agreement](../../standards/dual-delivery.md). Otherwise skip this step.

## 5. Verification and Delivery
Check the applicable sections of [UI Specialized Acceptance](quality.md); use [Quality and Acceptance](../../standards/quality.md) for evidence and delivery checks. Keep evidence of actual execution, and output how to run, versions, service dependencies, and known limitations.

Distinguish "design ready for handoff", "frontend demo runnable", and "production integration complete". Completed design handoff does not automatically mean the product can go live.

