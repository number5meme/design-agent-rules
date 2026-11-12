# Quality and Acceptance

Review records use: check item, method/environment, evidence, result, issue, fix status. Results can only be Passed / Failed / Unverified / Not applicable (with reason). Model self-scoring does not replace evidence.

Select domain acceptance via [Task Routing](../AGENTS.md#task-routing). This file defines shared evidence and delivery checks; apply only those relevant to the deliverable.

## Engineering and Delivery
- When component composition, nested placeholders, variable modes, or mobile occlusion need specialized checks, read [Component and Layout Review](../library/references/component-layout-review.md) selectively and decide the recheck method by the actual change.
- Run builds, static checks, and meaningful key-flow tests suited to the project.
- Record browser runtime errors; keep runtime environment and mock service boundaries clear.
- When delivering editable design files, check editability, components/variables, export, and access permissions.
- When dual delivery is agreed, check both sides on the same version of data/state/viewport.
- Asset/font licensing is traceable; assets with unknown licensing cannot be marked ready for launch.

## Conversion and Import

Before batch conversion or import, verify the agreed text editing, layers, components, font substitution, layout constraints, and export with representative objects. Keep the originals first and compare conversion losses; when the route fails, locate the cause first, and do not keep batch-producing the same kind of faulty output. This applies to both single and dual delivery.

Deliverable names identify the object, version, and applicable state; register design sources, exported images, and running code separately as agreed; the tool's internal page organization is decided by project needs.

## Content Completeness and Delivery Sources

When condensing requirements, copy, or notes, keep the object relationships, quantity meanings, applicable conditions, and key exceptions that determine understanding and operation, and delete repeated explanations first; check against valid sources and user-confirmed exceptions whether meaning changed, not just word count.

When compact layout is needed, adjust grouping, repeated labels, emphasis, pagination, font size, or spacing based on the cause of crowding, keeping content complete and readable. When space or page limits conflict with completeness and readability, explain the trade-off and handle it per existing authorization; do not silently delete content or break explicit limits. For document exports, check body text, table content, and actual pagination separately; complete content does not mean the layout passes.

Final generation and export use the currently confirmed content and correspondences. When reusing scripts or re-running, check whether old drafts, empty values, or default content would overwrite confirmed edits; fix the data source when necessary. Mark missing items as pending, check the correspondence between actual content and assets after delivery, and do not substitute format validation for content acceptance.

## Design File and Export Acceptance

- When an editable source is required, actually read or operate representative text, layers, and components to confirm they can be independently located and modified; file extension, layer count, or a screenshot embedded in a container does not by itself prove editability.
- For local edits, check the target, necessary linked changes, and comparison objects per [Targeted Edits and Comparison](../library/references/component-layout-review.md#targeted-edits-and-comparison); judge layout diagnostics together with design intent.
- Reopen the final export in a viewer or editor that supports the target format, and check fonts, line breaks, cropping, transparency, size, and agreed layer, vector, or editable properties. Compare against the same-version source; state inherent format limits, substitute effects, and unverified items.
- Record tool-reported success, file generated, screenshot viewed, visual pass, and editability pass separately; they cannot substitute for each other. When you cannot open or review, state that it is unverified.
- Limit capability conclusions to the actual task, environment, and observed scope: a minimal object experiment does not prove complex pages and multi-page components work; a callable tool does not mean orchestration is reliable, and single-environment results do not prove cross-tool or cross-model equivalence.

## Related Scope and Evidence

- When changing shared components or flows, list affected pages, entry points, identities, states, and layout scope; this may be briefly recorded in the existing review record, without forcing new files or enumerating unrelated combinations.
- Shared implementations may be verified with representative scenarios; independent branches using different containers, parameters, permissions, or state logic are checked separately. Sampled results cannot be described as all pages or all states passing.
- Visual changes check actual rendering, position, and scroll occlusion, and compare against shared components and related content; flow changes check object scope, state transitions, and return context. Syntax checks or unrelated business tests do not replace visual and interaction evidence.
- Distinguish implemented, verified as passing, and unverified; a component existing still requires confirming that relevant pages are wired in. A successful release proves only the release result, not that design or flow acceptance passed.
- The review record links issues, causes, fixes, and recheck results; distinguish requirement changes, execution omissions, and regression defects. New requirements cannot be retroactively treated as old implementation errors, and recurrence cannot simply be attributed to changed user preference.

## Style Feedback Recheck

Check against the user's reasons for rejection whether the new approach improves correspondingly, and whether other approved content was changed by mistake. For a full redesign, verify the original template has been retired from the current basis, and sync related pages, components, or series materials within the affected scope. Conforming to template parameters does not replace acceptance of actual results and feedback.

## Issue Severity
- Blocker: core flow errors, missing/inaccessible deliverables, unreadable key content, failure to run, etc. The corresponding delivery cannot pass until resolved.
- Must fix: obvious inconsistencies, missing important edge cases, major adaptation issues. Fix, or obtain a recorded scope adjustment.
- Improvement: details that do not block use. Record whether it is included in this delivery, avoiding endless polishing.

## Tailoring by Task

First tailor checks by [task type](task-scope.md): static showcase images do not require login states, and pure code fixes do not require a new Figma. Mark each result with its version and verification environment; do not carry an old version's passing conclusion over to a changed component of the same kind.

