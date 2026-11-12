# General Execution Rules

First determine the deliverable per [Task Scope](task-scope.md), then choose the domain workflow from [Task Routing](../AGENTS.md#task-routing).

For review only, report evidence and findings in the reply unless the user requests a saved review. For implementation work or a requested saved review, reuse the project's review record when available, recording evidence and status only for applicable stages; small revisions may directly record the issue, change, and verification. When stage management is needed and the project has no existing convention, you may use: Not started / In progress / Pending review / Passed / Passed with conditions / Blocked. Passed requires an output link and basis; Passed with conditions requires recording unfinished items and their impact. Stage divisions do not automatically constitute user approval gates.

## 1. Intake and Clarification

- Read requirements, outputs, and brand and engineering materials needed for this task. Distinguish facts, assumptions, and open items. Tailor documentation per [Record Ownership](task-scope.md#record-ownership), without filling documents as a fixed first step.
- Clarify core paths and data/service dependencies for the agreed deliverable. Do not settle unsupported business rules on your own.
- Verify actual tools, permissions, and target files. Distinguish a documented capability, a connected tool, and verified ability to read, write, and export. Check only needed capabilities; validate costly batch routes with the smallest representative sample first.
- If a necessary capability is missing, state the affected deliverable. Do not change its format without user confirmation; continue independent work.
- If interpretations would change the object, business behavior, permissions, flow, or delivered result, explain the difference and recommend an option. Confirm before dependent execution; continue independent work.
- Also confirm an approach that significantly changes experience, cost, or maintenance when there is no basis for choosing. Decide routine technical choices with equivalent effect autonomously.
- Honor an explicit request to discuss first. Do not reconfirm approved items.

Done when: the task and success criteria are clear; key core-path issues are resolved, or user-authorized temporary assumptions have a verification plan.

## Current Basis and Tool Route

For existing projects, first compare the affected object's current requirements, design decisions, and actual implementation. Handle outdated documents, implementation omissions, and new user requirements separately; fix deviations when the basis is sufficient, and confirm when you cannot determine which requirement is valid and it would change the result. Do not assume a file is correct because it is newer.

Among verified-available tools, choose the most direct and reliable way to meet the delivery requirements: prefer suitable file tools, APIs, or connectors for structured reads and writes; use a browser, editor, or other UI tool when you need to operate an interface or verify actual results. Tool choice does not replace result verification, and do not assume the current environment has a capability because a reference mentions it.

Handle necessary dependencies per task authorization, project conventions, and environment permissions; do not install a tool because a reference mentions it. For remote design sources, keep the accessible location, version or node, and necessary evidence, and store locally only the materials needed for the work; record permission gaps, and do not require copying the entire remote project into the workspace.

## Style Selection

Form the approach based on audience, content, brand, and purpose. Read methods to solve a specific problem. For parameters, follow [When to Read a Preset](../library/presets/index.md#when-to-read-a-preset).

Browsing material does not mean adopting it. When borrowing, record only the dimensions taken; when adopting parameters, record the actual effective values and scope; when explicitly replicating, keep the agreed characteristics. Do not add approvals for ordinary aesthetic choices; confirm material ambiguity per the rules above.

Resolve design conflicts per [File Precedence](../AGENTS.md#file-precedence); project variables maintain the actual effective values, and reference updates do not automatically override project decisions.

Judge aesthetic choices by this project's goals. Brand recognition, emotion, and memorability are also design purposes; do not make functional minimalism the goal of every piece.

Visual consistency is limited to the current project and agreed series: unify necessary semantics and components, and allow pages with different content to use different compositions. Do not inherit the previous project's palette or layout by default, and do not vary randomly just to create difference. Accept based on the current project's requirements and actual results; do not substitute resemblance to a reference for quality.

## Style Adjustment

Translate feedback into the specific dimensions to change, distinguishing color, typography, density, composition, assets, and overall expression. Local revisions keep other approved content; after the overall direction is rejected, stop applying the original template's style constraints, and mark its retirement and replacement in the project's current design record.

Re-select information hierarchy and presentation based on goals, audience, content, and the reasons for rejection, keeping independently confirmed business, brand, and delivery requirements. You may form a new direction autonomously or adopt a suitable reference; switching to another template is not required. When comparing color schemes, you may keep the layout; when asked to redesign the overall expression, address the actual reasons for rejection rather than substituting unrelated tweaks. Changes cover the feedback dimensions and the related changes needed to achieve them.

By default, give one well-founded new recommendation and continue within the authorized scope. Offer alternatives only when a direction comparison or major trade-off is needed; when the user requests a stage review or there is material ambiguity, pause the dependent part and follow the clarification rules above.

## Capturing Lessons
Record accepted/rejected designs and reasons in the project record; distill reusable candidates, recording scope and counterexamples. Update related indexes only when there is a new reusable finding, and promote per the knowledge governance rules.

Follow [Record Ownership](task-scope.md#record-ownership) for record responsibilities.

## Async Operations and Retries

After issuing operations such as creating files, generating assets, or exporting, keep the returned object or task identifier, and wait until it is clearly ready before running dependent operations. Independent reading and judgment may continue; not ready or a response timeout does not mean the operation failed; do not create the same deliverable again.

When the result is uncertain, first query the status or read the target to confirm whether it already completed. When a retry is truly needed, use the failure reason and the recovery method the tool supports; when idempotency keys are supported, reuse the key from the same operation. When the tool cannot confirm status and repeating has material cost, state the uncertainty and do not resend blindly. Retry only with new evidence, changed conditions, or a clearly recoverable cause; on persistent failure under the same conditions, preserve the state and report the blocker, wait for the necessary conditions to recover, and continue other independent work.

## Interruption and Resumption

When a long task is interrupted or needs handoff, leave in the existing project records, as needed, the current goal, valid decisions, completed and unverified items, in-flight operation identifiers, blockers, and next step; link existing primary records instead of copying whole history. Small tasks do not need a separate resume document.

When resuming, first locate the current goal, unfinished items, and next step from the existing primary records, then check the actual state of output versions and in-flight operations as needed, and continue the unfinished parts; do not redo completed, unaffected work, and do not reuse stale conclusions directly. When records are insufficient and affect the next step, clarify only the necessary questions.

## Per-Revision Requirements
Feedback → judgment of the underlying need → related changes → actual result → recheck. Identify position, copy, color, behavior, identity conditions, and data scope separately; changes cover the dimensions the user adjusted and the related changes needed to achieve them. Other confirmed conditions remain valid; do not infer permission changes from a single position or copy adjustment.

When a new request arrives during execution, first distinguish a supplement, a correction, and an explicit cancellation or replacement, keeping goals and constraints that remain valid. Check whether completed outputs and in-flight operations are affected; stop advancing dependent work that is no longer valid, cancel stale operations that can be canceled as needed, and check those that cannot be canceled after their results return; do not apply old results directly to the new request. Handle unclear status per the retry rules above; continue independent work, and do not restart the whole task because of a local adjustment.

Proactively check related layout, style, and behavior per [Revisions and Recurring Issues](components.md#revisions-and-recurring-issues), and locate the root cause when an issue recurs. Sync current decisions to the primary record and apply them to the actual screens.

When submitting, state the key changes, basis, verification results, and remaining issues.
