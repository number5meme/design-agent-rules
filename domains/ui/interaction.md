# Interaction Process, Motion, and Feedback

Read by task: [Workflow](workflow.md) · [Method](design.md) · [Acceptance](quality.md). For local edits, read only the affected sections.

Read only sections for behaviors being designed, changed, or checked: paging/gestures, scroll behavior, asynchronous feedback/pop-ups, motion, or exported loops. A static layout-only change does not require this file. For a key interaction, also use the definition table below; section links do not require reading the whole file.

Interface design must cover before, during, and after an operation. Motion can explain relationships, preserve context, confirm operations, reveal state, or express brand emotion; do not just add a few transitions after the static pages are done.

Choose motion parameters and scroll behavior by product task and platform; consult official documentation when native behavior is uncertain.

## What to Define for Each Key Interaction

Describe key interactions in the project design record; when cross-file mapping is needed, use stable IDs corresponding to pages, components, and states.

| Field | Must consider |
|---|---|
| User purpose | Why the user acts; what the feedback helps them understand |
| Trigger and preconditions | Click, swipe, scroll, keyboard, data return; available/unavailable conditions |
| Follow-through process | Which elements move, scale, or change opacity/material; which stay fixed; whether content follows the gesture directly |
| End and landing point | Snap/bounce after release, completion conditions, final selection/focus/data state |
| Cancel and interruption | Reverse swipe, threshold not reached, rapid repeated taps, page switch, close, back, system interruption; whether reversible |
| Feedback | Press feedback, processing, result, failure reason and recovery action; in what position and form |
| Implementation parameters | Distance/velocity thresholds, duration/easing or spring, delay, layering, interruptibility; choose initial values before implementing, and maintain effective values after testing |
| Alternatives and degradation | Keyboard/assistive technology, reduced motion, reduced transparency, low performance, unsupported capabilities |
| Verification method | How to reproduce, expected result; link actual evidence to the review record |

Record only applicable items; settle behavior and boundaries first, then adjust initial parameters with actual results; do not invent behavior to fill the table.

## Choose Checks by Actual Interaction

Dragging and focus floors follow [Behavior and Verification](../../standards/defaults.md#behavior-and-verification): verify single-pointer alternatives and keyboard alternatives separately; a draggable carousel can have previous/next buttons, and reordering can have a move menu. Do not treat switching to another swipe gesture as a no-drag alternative; judge native browser scrolling and author-controlled scrolling separately.

### Category and Page Switching
- Distinguish horizontal scrolling of a tab bar from horizontal switching of content pages; they are not the same requirement.
- Choose behavior for ordinary tabs, filters, and navigation by task; do not add swipe paging by default. When swipe paging is used, content follows the gesture and the selection indicator follows progress; settle the final selection and assistive technology state after the gesture completes.
- When dragging or horizontal swiping exists, define short-drag bounce-back, edges, rapid switching, and reverse interruption, and check conflicts with vertical lists, card taps, and system back gestures. Supported click and keyboard operations should produce consistent selection results.
- Make an explicit decision about how each category's scroll position, search conditions, and return state are preserved.

### Page Scrolling and Top Area Handling
- Identify the actual scroll container; define the top area's states at initial, compressed/sticky, and back-to-top.
- Which controls such as search and navigation stay and which collapse must be based on the task; do not hide all top bars by default.
- State whether content extends beneath the navigation, when a divider/material appears, text readability, and safe area handling.
- Do not toggle visibility directly on a single incidental scroll direction; avoid jitter at threshold positions, page jumps, and focus loss.
- Do not add features such as pull-to-refresh or auto-hiding bottom bars unless the current scope requires them.

### Buttons, Pop-ups, and Results
Here, a pop-up is a temporary interface surface such as a menu, popover, or dialog. Identify its actual role before choosing focus or dismissal behavior. Distinguish an interactive surface from its backdrop and from a purely visual overlay such as a tint.
- Separate press feedback from business success feedback. Use haptics only where the platform supports them; do not pretend the browser has native haptics.
- Pop-up entry/exit has a clear relationship to its source. On dismissal or return, restore focus, selection, and scroll position when the original objects and context remain valid and the flow calls for returning there. If an object was deleted or the operation advances the flow, choose a reachable destination consistent with the result rather than restoring stale state. Decide supported dismissal gestures by content and risk.
- Operations that require waiting show the actual processing state; never delay the request or simulate confirmation with an animation timer.
- On success, prefer updating the related interface; use toasts as feedback requires, and do not make every operation "animation + pop-up + toast".
- Place errors near where they occur and explain how to recover; clearly separate duplicate-submission protection and cancelable and non-cancelable stages.
- Data updates keep the reading position; for key amounts, prioritize accuracy and stability, avoiding rolling numbers that cause misreading.

For asynchronous actions, acknowledge input promptly. Test fast and slow responses. If a spinner would flicker, choose a reveal delay (150–300 ms is a starting point). Skip it if the request settles first. Once visible, keep its feedback area visible for a minimum interval (start with 300–500 ms from appearance). If the request settles during that interval, replace the spinner with the actual result immediately in the same area. The minimum controls visual persistence only; it must never hold a result, error, input, or navigation. For optimistic updates, test a rejected request: reconcile the visible state with the server result, explain the failure, and preserve retryable input. Offer undo separately when a completed action can be reversed.

## Motion Trade-offs and Continuity

First judge motion's role in understanding, orientation, feedback, or emotional expression, then control amplitude, duration, and delay by usage frequency and task urgency. Feedback appears near the operated object first, with intensity matching the action's importance; brand personality must not hinder recognizing state. High-frequency operations prefer immediate or lightweight feedback; keyboard triggers do not automatically disable animation, but must not delay input, focus, or subsequent operations. When list items appear in sequence, do not make users wait for the last item before they can use it.

The rhythm of entry, scrolling, and transitions jointly organizes attention; avoid multiple unrelated effects competing for focus at once. Expressive motion relates to content or brand and keeps direct paths for reading, navigation, and operation.

Show feedback promptly on press, and commit business actions per control semantics; operations that support move-out-to-cancel should be cancelable, and keyboard and assistive technology still have equivalent entry points. Dragging keeps the grab point's position relative to the content, and after release determines the landing point by distance, direction, and release velocity; use velocity hand-off and edge resistance only for interactions that need inertia.

Interruptions continue from the screen's current state, not replay from the previous target value. When the gesture reverses, keep position continuous, and keep a reasonable velocity change when inertia is needed; clean up drag state after system cancellation, pointer loss, or component unmount. During a single-finger drag, keep ownership with the same pointer, keep tracking as agreed after leaving the element, and do not let extra touch points take over and cause jumps; handle multi-finger gestures per their own design. Feedback may respond immediately but must not bypass business submission safeguards.

Menus and tooltips anchored to a trigger expand from the corresponding position; centered dialogs follow their own layout. The spatial relationship of entry, exit, and return should be understandable; do not force all overlays to use the same origin or trajectory.

Tooltips in the same group may use a first-hover delay to avoid accidental triggers; when the user has opened a tooltip and is viewing adjacent controls in succession, repeated waiting may be reduced, restoring the normal policy after leaving the group. Keyboard focus and dismissal must still work, and touch operations must not depend on hover tooltips for necessary meaning. Check only in interfaces that use such tooltips; do not add tooltips to implement this rule.

## Motion Quality

Each project maintains a small set of semantic parameters (press, switch, pop-up, etc.); do not write different speeds ad hoc everywhere. Tune specific values with feedback from actual devices/browsers; do not treat default durations as industry standards.

Prioritize interruptibility, prompt response, and content stability. With reduced motion, use immediate states or lightweight changes to preserve meaning; with reduced transparency, keep clear layering. For [Web Glass Material](../../library/references/glass-material.md), check glass effects while dynamic backgrounds pass behind controls; static screenshots are not enough to prove readability.

For web implementation, use existing style and motion capabilities first, and do not install a library for simple transitions; evaluate the needed capabilities for complex gestures or layout changes. Specify transition properties explicitly, avoiding `transition: all` pulling in unrelated changes. Prioritize reducing per-frame layout and paint cost; when size changes are needed, keep real layout semantics and measure, and do not assert smoothness or hardware acceleration from property names alone.

## Showcase Animation and Loop Acceptance

When turning a static design into a showcase animation, first distinguish demo choreography from real product interaction. Loading, data changes, and loops in a demo are not evidence that functionality is implemented; rhythm, range of motion, and output format are decided by use, and do not automatically extend to all page elements or extra export formats.

With a static design baseline, first compare against the agreed still or settled frame, then check the motion process. Independently moving content keeps correct relationships with containers, masks, and shadows; check clipping and overflow against design intent, and do not judge originally allowed overflow as an error across the board.

For looping animations, check whether the seam is continuous and whether repeated playback accumulates offset or ghosting; when a reset or return to baseline is needed, check that text, paths, particles, and other dynamic states have all reset. When there are hold or blank phases, check the whole phase; do not pass based only on the first and last frames matching.

Check key phases of the actual exported file and play the full loop at normal speed; use slow motion, frame-by-frame, or controlled time sampling to locate issues as needed. Focus points and changes should remain clear at final size; still-frame matching or numeric difference metrics cannot replace checking the process.

## Dual Delivery

When the user has confirmed dual delivery, maintain the correspondence and differences between the design source and the runtime per [Interaction and Motion Mapping](../../standards/dual-delivery.md#interaction-and-motion-mapping).

## Preserving Behavior When Replacing Appearance

Before implementing, list the old component's existing behaviors; after replacing, compare item by item. Clearly distinguish "scrollable tab bar", "drag the selected capsule", and "swipe content to switch pages"; do not implement only one and report all as supported. A system segmented control and a content paging container need state coordination; do not assume that using the system appearance gives you swiping.

Components of the same kind reuse the same behavior implementation, recording task-based exceptions. Acceptance covers the component's existing behavior and the behavior required this time; check gesture items per [Category and Page Switching](#category-and-page-switching). Static designs annotate states and processes; frontend-only tasks need no extra Figma. Without real-device verification, do not write that native gestures passed.
