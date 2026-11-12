# Design Judgment and Feedback Reasoning

Read by task: [Workflow](workflow.md) · [Method](design.md) · [Acceptance](quality.md). For local edits, read only the affected sections.

Applies to new designs and modifications; tailor records per [Record Ownership](../../standards/task-scope.md#record-ownership).

## Identify the Product and Task

Read the PRD, existing pages, and related history, and answer:
- Who is the user, and what task does the current page help them complete? Do first and repeat visits differ?
- What attributes does the product have, and which one dominates the current page/module? For example, finance, collecting, content, and collaboration can coexist.
- What information has decision value? What information, if wrong or missing, causes misunderstanding? Group, order, and present by user task; do not lay out API fields flat with equal weight; keep necessary details reachable.
- What states does the data have: unknown, loading, empty, updated, stale, failed? Which are necessary for this round's scope?
- What constraints come from the platform, usage scenarios, business boundaries, existing brand, and asset quality?

Avoid unnecessary secondary labels and descriptions. Let the layout do the explaining. Use grouping, alignment, and proximity to show relationships. Remove copy that merely repeats a heading, field label, or button. Check that the remaining copy still explains required inputs, fees, consequences, and how to recover from errors where applicable. For example, a Pay button needs no instruction to click it, but a nonrefundable charge needs a clear disclosure before payment.

First set the design focus by the current page's purpose: to drive decisions, organize claims, evidence, and action; to complete operations, prioritize scanning, efficiency, and state; to aid understanding, prioritize content structure and reading; to showcase work, make the work itself the subject. For mixed purposes, set priorities by the current task; do not reuse the same density, composition, or expressive intensity just because pages belong to the same product, and do not require filling in an extra classification table.

Categories are a basis for asking questions and forming hypotheses, not style labels or feature lists. When using [Product Category Cues](../../library/references/product-contexts.md), check applicability; for uncertain or changing facts such as external product guidelines and specific platform behavior, consult official sources.

When creating or redesigning a visual direction, or when templated expression needs solving, you may consult the [Product Context and Visual Judgment Reference](../../library/references/visual-judgment.md); small revisions need no extra loading.

## Form the Main Approach Through Explicit Reasoning

When a style system needs recording, you may use the [template structure](../../templates/style-template.md). Reading, selecting, and prioritizing references follows [Style Selection](../../standards/workflow.md#style-selection).

When creating or redesigning a direction, make key design judgments explicit; when they need documenting, you may use the table below; simple modifications record only goal, change, and verification, without design claims or tables.

| Basis: fact/user feedback/category hypothesis | Derived user need | Specific design action | Trade-offs and boundaries | How to check |
|---|---|---|---|---|

Requirements:
- Label facts, explicit user requirements, and Agent inferences separately; do not present inferences as user approval. Confirm ambiguities affecting the operated object, behavior, permissions, or delivery first per [Intake and Clarification](../../standards/workflow.md#1-intake-and-clarification); aesthetic autonomy does not replace requirement confirmation.
- Check hierarchy, content/data, assets, applicable interactions, and visual consistency per task; do not invent changes to pad the count.
- Important design decisions can explain their effect on the task, brand expression, or emotional experience. Color and blur parameters do not replace reasoning.
- You may compare and prototype autonomously during design; by default deliver one recommended option and explain key trade-offs. Provide alternatives when the user requests a comparison or a major trade-off needs explaining.
- Implement reversible designs directly within the authorized scope. Issues affecting amounts, assets, permissions, core flows, and the like require a business basis; do not fill them in by category inference.

## User Feedback Triggers Related Review

Handle feedback and revisions per [Per-Revision Requirements](../../standards/workflow.md#per-revision-requirements); on the design side, focus on identifying which layouts and behaviors changes in copy, position, or appearance will affect, keeping unrelated confirmed decisions.

## Check Issues the User Did Not Name

When viewing real output, proactively check: whether content has credible sources; whether the first screen serves the core task; whether the text hierarchy is monotonous; whether the subject is swallowed by the image background; whether assets in the same group are harmonious; whether numbers are comparable; whether action results are clear; whether long content and edge cases break the layout.

When an issue is found, give a specific fix. When assets are insufficient, prefer reorganizing the display with existing assets; when new assets are needed, state their purpose and produce or obtain them per the relevant skills; do not pass off empty frames as complete. Do not pause independently completable design for "waiting for assets".

## Color Semantics and Reference Scope

- When creating or refining a page, inventory the colors actually used for backgrounds, text, borders, actions, and interaction states. Map them to existing brand and semantic color roles first. Consolidate unexplained differences within the same role, theme, and state. If the palette is incomplete and the project has selected a palette library, use it as a candidate source for missing roles and verify the resulting pairs on the page.
- Check color changes per [Color Pairing](../../standards/defaults.md#color-pairing); do not treat a single value in a palette as a verified component.
- **Brand, action, and state each have their own semantics.** The brand identity color need not equal the primary action color; express errors, warnings, success, and business categories as the task requires, and do not erase necessary distinctions to keep a single accent color. Do not rely on color alone to communicate state. Provide a text, icon, or shape cue as well.
- **Transfer style by page task.** A promotional page's large titles, wide spacing, and few actions do not directly determine an in-app workspace's information density, navigation, or state colors. Judge applicability of a reference's assets, typesetting, and components separately.
- **Extract the product's own design.** Identify third-party controls such as cookie and payment widgets separately from the host page; do not derive site-wide specs directly from their colors or components. Do not expand a locally observed treatment into a site-wide rule; fill in unobserved states per project requirements.

When content organization, layout, or adaptation methods are needed, consult the [Design Method Reference](../../library/styles/index.md); do not read specific parameters by default.

## Controls and Copy

When control selection, entry naming, or input hints are involved, read the corresponding sections of [Controls and Copy](controls-and-copy.md).

## Design Judgment for Dynamic Behavior
When key behavior is being designed or changed, use [What to Define for Each Key Interaction](interaction.md#what-to-define-for-each-key-interaction) and only the sections matching that behavior. For a swipe, specify how the content follows the gesture, when release commits the change, and how a canceled swipe returns to its starting position. How the top bar and bottom bar behave after the page scrolls up is also within the first-round design scope; specific behavior is decided by the task.

## Submit Judgeable Results

Reviews provide the actual screens or interactions, necessary key judgments, and known boundaries; explain the impact on the user's task.

Acceptance must answer all of the following: Is the task easier to complete? Are the visuals more harmonious? Is the problem behind the user's feedback resolved? Which assumptions remain unverified? Do not judge the design complete just because every item on the change list is checked.

## Business Sources and Cross-Platform Migration

Link key design decisions to valid sources, distinguishing requirements, actual observations, platform constraints, and inferences; reference existing records directly. Explicit user revisions may override the original PRD within this project's scope; flag conflicts between platform constraints and business documents rather than choosing silently. Existing prototypes and mock data are not a new business basis.

When migrating across platforms, record only the business meaning, observed differences, target-platform decisions, and basis that affect this design, reusing existing records. Keep business meaning consistent, and adjust entry points, density, and presentation per platform; a feature not observed on the source platform does not mean it does not exist, and cannot override confirmed target-platform requirements. Handle business conflicts per [Task Scope](../../standards/task-scope.md#scope-record).

After deleting or moving information, check affected layout and behavior per [Revisions and Recurring Issues](../../standards/components.md#revisions-and-recurring-issues). Provide guidance in empty states only when the user has a reasonable next action.

Handle component selection per [External Implementation Selection](../../standards/components.md#external-implementation-selection). When claiming native capability, note the actual platform, version, and runtime evidence; a similar appearance does not prove a system implementation. Different item counts and containers may affect component size; choose representative scenarios and check independent branches per [Related Scope and Evidence](../../standards/quality.md#related-scope-and-evidence).
