# UI Specialized Acceptance

Read by task: [Workflow](workflow.md) · [Method](design.md) · [Acceptance](quality.md). For local edits, read only the affected sections.

Choose checks by the affected pages, states, and behaviors. Read linked methods only when a check needs clarification or reveals an issue, not as a full-file reading list. For evidence, related scope, and delivery checks, see [Quality and Acceptance](../../standards/quality.md).

## Product Fit and Design Judgment
- Did the product category, current task, and usage scenario actually shape the screens, rather than only appearing in the copy?
- Can key decisions be traced from requirements/feedback to specific interface or state evidence?
- Does it resolve the problem behind the user's feedback and related issues, rather than only fixing the named items?
- Do the various needs of a composite product have clear priorities, and were features or information added without basis?
- Are unknown, empty, and invalid data distinguished from a real zero; are mock states explicit?
- Were assets, real content, and edge cases checked proactively; does the recommended option have a basis for its trade-offs?

## Visuals
- Users can first identify the current task, key information, and primary action.
- Type hierarchy, spacing, density, and imagery follow this project's valid rules and the page task; representative samples constrain only selected dimensions and do not require all pages to share one structure. For a detailed check, review real copy's typesetting, grouping and whole-page rhythm, color distribution, and project distinctiveness per the [Visual Judgment Reference](../../library/references/visual-judgment.md).
- Check helper copy beside its heading or control per [Identify the Product and Task](design.md#identify-the-product-and-task). Compare same-role text sizes at the same viewport per [Typesetting and Reading Rhythm](../../library/references/visual-judgment.md#typesetting-and-reading-rhythm).
- Decoration, containers, and copy support informational, brand, or emotional goals; nothing hinders reading or operation, or is added mechanically. Locate visual roughness to specific color, typesetting, proportion, asset, or detail problems; component unification cannot replace aesthetic judgment.
- Styles and position logic of similar actions are stable, and reasonable scenario differences have a basis; check actual shared component wiring, without requiring pages to share one structure. First screens, inner pages, page ends, and action states within scope keep a commensurate level of finish; do not polish only the home page or showcase states.
- For new or redesigned pages, view the actual rendering page by page against this project's design goals and the applicable dimensions of the representative sample; for small shared component revisions, sample per [Related Scope and Evidence](../../standards/quality.md#related-scope-and-evidence) and verify independent branches separately. Record specific deviations.

- Check foreground/background pairing, theme states, and brand/action/state color roles per [Color Semantics and Reference Scope](design.md#color-semantics-and-reference-scope), avoiding extending local styles of promotional pages or third-party controls into general requirements.

## Content and Flow

Apply only rows matching the page's controls, content states, or operations. For primary-flow design reviews, use [UI Critique](../../library/references/ui-critique.md) when a walkthrough is needed.

- With forms, unsaved edits, or truncated labels, test invalid-submit focus, safe navigation, and full-text access per [Submission and Disclosure](controls-and-copy.md#submission-and-disclosure).
- With controls that select, edit, or act, check information type, timing of effect, and predictable object, scope, and result per [Operating Conventions and Expected Results](controls-and-copy.md#operating-conventions-and-expected-results); check whether routine tasks added unnecessary learning cost.
- With fields or placeholder states, check useful hints, persistent field meaning, examples versus actual values, and loading/empty/failure/missing-asset expression. For unresolved cases, see [Input Hints and Placeholder Content](controls-and-copy.md#input-hints-and-placeholder-content).
- With navigation or action entry points, check across affected pages per [Entry Naming and Action Consistency](controls-and-copy.md#entry-naming-and-action-consistency) the same destinations, duplicate exit entry points, icon recognizability, and the objects and result feedback of share/copy; keep differences with a business or platform basis.
- Check whether settings items, menu options, and buttons reasonably use matching icons to aid scanning; icons in the same group are consistent in meaning, size, stroke width, spacing, and state expression, and text and assistive technology names stay clear.
- Each in-scope core business rule has a corresponding implementation in the state table or flow.
- Back, close, repeated taps, cancel, retry, and applicable empty/error/loading states are explicit.
- Operation feedback reflects real results; amounts, quantities, eligibility, and record changes are self-consistent.
- An interactive prototype or frontend runs through at least one agreed main flow and covers this task's high-risk edges; static designs check flow and state expression.

## Interaction Process and Motion

Apply only checks for behavior present or affected: gestures, scrolling, feedback, pop-ups, or motion. Unchanged behavior still needs checking when the edit could affect it.

- With paging, switching, or gestures, check [Category and Page Switching](interaction.md#category-and-page-switching) for the chosen behavior, process, interruption, and recovery; do not add swiping to ordinary switches.
- When scrolling up/down/back to top, do the top-level layering, sticky/compressed state, dividers, and material change as designed, without jumps or jitter?
- Do horizontal and vertical gestures and card taps conflict; are short-drag cancel, edges, reversal, and consecutive operations correct?
- Press, processing, and success/failure are each perceivable; unfinished business is not presented as success, and fixed waits are not used to fabricate confirmation.
- After exiting a pop-up or returning to a page, verify restoration or a suitable new destination per [Buttons, Pop-ups, and Results](interaction.md#buttons-pop-ups-and-results); cover deleted targets or flow advancement when applicable.
- Do floating controls stay readable as different images/content scroll past, and can the last content scroll into an unobstructed area?
- Are reduced motion/transparency, keyboard alternatives, and performance limits handled?
- When runnable interactions need acceptance, key dynamic evidence includes process and interruption; static design files check the corresponding state and behavior notes.
- When motion or dragging is involved, check per [Motion Trade-offs and Continuity](interaction.md#motion-trade-offs-and-continuity) motion priority and feedback intensity, direct reading and operation paths, latency of high-frequency operations, and drag grab point, release hand-off, and post-cancel state.
- When jumps, replays, or stutters are suspected, locate them with slow motion or frame-by-frame, and recheck at normal speed; for performance issues, record actual load and measurements. Suspicious code patterns are leads for investigation, not direct conclusions of experience failure.

For showcase animations and loop exports, also check applicable items per [Showcase Animation and Loop Acceptance](interaction.md#showcase-animation-and-loop-acceptance).

## Adaptation and Accessibility
- Actually check at the project's agreed minimum/mainstream/maximum viewports, and check threshold widths of affected layouts; check whether reading order, title line breaks, image focal points, density, and navigation suit the current size. On mobile, focus on safe areas, keyboard, scrolling, and fixed action areas.
- When a mobile web page involves the address bar, soft keyboard, touch, or zoom, check per [Mobile Web Adaptation](../../library/references/web-ui-review.md#mobile-web-adaptation); record browser emulation and real-device conclusions separately.
- Design and implementation set line-break, truncation, expansion, or scrolling strategies by actual data boundaries, and check with long and short copy, extreme values, empty data, missing images, and applicable multiple languages; key information and actions are not lost to container overflow or truncation.
- Check item by item per [Core Defaults](../../standards/defaults.md) the contrast, target size, zoom, reflow, keyboard, and forms involved in this task; record measured values, environment, and exceptions. When motion is present, check reduced motion per [Motion Quality](interaction.md#motion-quality); a formal conformance claim requires a separate full audit.

## Details and Native Environments

Check components' platform fit and behavioral completeness per [External Implementation Selection](../../standards/components.md#external-implementation-selection); when something is off, fix the cause rather than mechanically replacing it with a native appearance.

Supplementary visual checks: avatar to text-group proportion, baseline and optical centering of digits/letters/currency symbols, changes in count length, different numbers of segments, and spacing and content start after removing fields. Component appearance changes must verify existing behavior has not regressed.

For native targets, record the actual verification environment, distinguishing web approximation, native runtime, and real-device results. Business coverage distinguishes entry point existence, representative states running, and real service integration; interface acceptance does not mean app review approval.

## Data Displays

For a chart, identify the question it answers. Verify units, time range, scale and series labels against the source data. Check that a reader can retrieve key values without hover, including by keyboard or touch when interactive. Check its text equivalent and non-color cues per [Core Defaults](../../standards/defaults.md#web-content-and-motion).
