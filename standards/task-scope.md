# Choosing Workflow and Deliverables by Task

Determine the nature of the task per the [entry rules](../AGENTS.md#starting-a-task). For build and edit tasks, the user determines the deliverables; do not default to design files, frontend, or dual delivery. When the user has specified format and purpose, proceed directly; otherwise, first confirm the deliverable, editability, and whether it needs to run or be published, then do the work that depends on those choices.

| Scenario | Minimum record | Main output | Required acceptance | Do not add automatically |
|---|---|---|---|---|
| Existing frontend feature / bug fix | Impact scope, existing behavior, change and verification | Code change, how to run, applicable tests | Actual paths, related regressions; screenshots when visuals are affected | Figma redraw, product refactor, new backend |
| Single web page / product page | Audience, task, content, devices, dependencies | Page code or editable design as requested | Real content, responsive adaptation, applicable states and interactions | Full app, login system, extra pages |
| Specific design image / UI mockup | Purpose, size, content, references, output format | Editable source or explicitly agreed final image, exports | Proportions, fonts, assets, readability; editability when a source file is agreed | Runnable frontend, unrelated business flows |
| Poster / cover / promotional showcase image | Placement, subject, brand, copy, specs | Graphic source file / bitmap, exported as agreed | Actual size, cropping, safe margins, licensing | Page interactions, full set of UI states |
| Presentation | Audience, purpose, content basis, aspect ratio and editing requirements | Presentation file in the agreed format and required source files | Content and per-slide rendering, whole-deck consistency, applicable editing and playback capability | Fixed intermediate format, speaker notes, animation, or extra research |
| Logo / character / brand materials | Purpose, existing assets, fixed and variable items | Agreed standalone assets, source files, or applied materials | Recognizability, fidelity, set consistency, and export | Full VI, character pack, fixed number of options or mockups |
| Product detail module images | Product information, buyer questions, image/text basis and carrier | Agreed module images or editable source | Product fidelity, claim evidence, reading and image-text correspondence | Product page code, fabricated specs and effects |
| Design-to-code / web style extraction | Target version, codebase or reference scope | Frontend implementation or required style parameters | Comparison against the actual page or verification of applied parameters | Default tech stack, dual delivery, showcase-style spec canvas |
| Full product / multi-page experience | Requirements, design, verification, and handoff records organized by size | User-confirmed design files, prototype, frontend, or combination | Key pages, states, and cross-page paths checked for agreed deliverables; cross-side alignment only for dual delivery | Unconfirmed deliverables, business and production interfaces |
| Review only / requirements comparison | State the compared version, evidence, and scope in the reply. Save a file only when requested. | Issues, differences, priorities, and recommendations | Sources, reproducibility, facts distinguished from inferences | Automatic code changes, design changes, or publishing |

## Combined Tasks

Choose one primary workflow by the main deliverable, then load the necessary constraints from other domains. For example, a branded product poster follows the poster workflow, adding brand fixed items and product authenticity requirements, without running all three workflows in full. Reference the series visuals rules when a set of materials is needed.

When multiple independent deliverables are explicitly requested at once, list outputs and acceptance separately, and arrange shared assets and dependency order; do not add deliverables just because the subject involves a brand, product, or interface. Local edits focus on affected sections and must not trigger a rerun of a whole domain workflow.

## Choosing Deliverables by Use

Do not choose tools based only on names like "poster", "page", or "brand guidelines". When the user needs to keep editing text, layers, or layout, deliver an editable source; when they need actual operation, deliver a runnable page or agreed prototype; when they only need images for placement, deliver images to spec. Confirm when the use is materially ambiguous; do not ask again about a specified format; list deliverables separately when a combined delivery is needed.

Executable brand or design guidelines should provide accurate, readable specifications for colors, dimensions, fonts, and components; an image with unverified parameter labels is no substitute. Distinguish interface motion from finished video by use; do not turn a task into video generation just because "motion" appears.

## Style Feedback Scope

When dissatisfaction is local, adjust the corresponding dimension; when the overall direction is rejected, redesign. When the two cannot be reliably distinguished and would significantly change the redo scope, explain your understanding and recommendation and ask the user to confirm; judge ordinary aesthetic choices autonomously. For execution, see [Style Adjustment](workflow.md#style-adjustment).

## Project Isolation

Before working on a project, determine ownership from the user-specified path, current task context, and existing directories. New projects default to a dedicated directory at `projects/<project-name>/`; existing projects keep their original directory, and do not create duplicate projects for a new task or local revision. When the user specifies another location, follow it, and do not migrate existing files on your own.

Directory names should identify the project; check for name collisions before creating. A shared name does not prove it is the same project. When ownership cannot be reliably determined, confirm first, then perform reads and writes that depend on it.

Put project requirements, design, assets, code, verification, temporary artifacts, and deliverables in the corresponding project directory, creating subdirectories as actually needed. Verify the target path and working directory before operating; do not overwrite other projects' files, and do not write project content into the agent's shared specs or shared references.

When reusing across projects, specify source, target, and reusable scope, and reuse only applicable content you have the right to use; do not automatically inherit another project's business rules, style, or authorization. Distill shared methods per the knowledge governance rules; project evidence stays in the original project.

## State Applicability

UI design images add states such as selected, empty, and scrolled, plus interaction notes, as the task requires; do not omit necessary states because the delivery is static. Pure promotional images do not require fictional loading/login states. Frontend fixes focus on affected states and existing behavior; do not add backend rules just to complete a table.

## Record Ownership

Reuse equivalent project records regardless of filename. Maintain each fact in one place and reference it elsewhere.

- **Primary record** means the authoritative location for a particular fact, not a fixed filename. Scope records own requirements and scope changes; design records own current decisions; review records own verbatim feedback, issues, and verification; handoff records own deliverable entry points, versions, and dependencies. Variable values may have their own primary source, linked from these records.
- **Combined record** means one small-task record with sections for goal, decisions, changes, verification, and delivery. A few lines may suffice; separate files, design claims tables, and stage tables are not required.
- **Project entry** means the project's existing navigation or status entry that links current records and outputs. It is not `templates/project/index.md` and requires no new file or template.

Split records only for ongoing or complex work. Do not mark unagreed deliverables incomplete; keep committed but deferred work pending. After copying templates, fix links and remove inapplicable sections.

## Current Records and History

- Keep the project entry focused on current goal, valid basis, output locations, verification boundaries, unfinished items, and next step.
- Identify each parallel branch's primary records separately. Link their version and release receipts instead of copying them into the main entry.
- Update current conclusions by topic. Move accumulated revision history, old receipts, and superseded options to the existing history record. If archiving is needed and no location exists, create a named history file and link it from the current record.
- Before archiving, retain valid constraints, user exceptions, unresolved issues, and evidence entry points; mark replacement relationships. Mark uncertain content pending verification rather than deleting it.
- Preserve historical evidence verbatim with working links. Old verification does not establish current acceptance.
- On resumption, read task-relevant current records first. Read history only for tracing, differences, or insufficient current evidence. Reuse the project entry and fix references instead of adding a parallel summary record.

## Scope Record

Use the [project record templates](../templates/project/index.md) when an equivalent record is missing. In the [scope record](../templates/project/brief.md), specify as needed the task type, current deliverables, target platform/viewport or canvas specs, reference version, retained constraints, variable parts, out-of-scope items, and success criteria. When scope changes, update the primary record first; require resolution of business conflicts only when they affect the interface/flow observable in this task.
