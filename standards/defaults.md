# Core Defaults and Check Baselines

This file defines readability baselines for UI, frontend, and static visuals; it does not prescribe brand aesthetics, nor require posters or videos to be interactive. The Web part covers common WCAG 2.2 AA checks; this table alone cannot support a claim of full conformance; static visuals use the explicit workspace check baselines below. Domain rules must not lower the floors; the standard's built-in exceptions require evidence, and other deviations require the user's explicit decision, obtained and recorded per [File Precedence](../AGENTS.md#file-precedence). Anything that does not meet the original standard cannot be marked as passed or conformant. Judge starting points such as font size separately from mandatory floors.

## Color Pairing

Record the actual foreground, adjacent background, purpose, theme, and state; composite transparent colors against the actual background first, and check the least favorable position on images or gradients. When changing a background, recheck text, icons, necessary boundaries, and focus. Do not default to white text on colored backgrounds. Judge ratios by unrounded values.

| Check | Criterion | Boundaries and evidence |
|---|---|---|
| Normal text, input hints | Contrast ≥ 4.5:1 | Record the color pair and computed result; apply WCAG 2.2 criterion 1.4.3 exceptions for incidental text and logotypes |
| Large text | Contrast ≥ 3:1 | At least 24 CSS px, or bold at least 18⅔ CSS px; when the large-text condition is not met, use the normal-text threshold |
| Required controls and graphical information | Contrast ≥ 3:1 against adjacent colors | Only information required to identify controls, states, or understand graphics; do not apply mechanically to decorative dividers; disabled controls excepted |
| State expression | Error, warning, success, selected, etc. have text, icon, or shape cues | Color must not be the only information; check states actually present in this task |

## Static Visuals

Posters, covers, slides, brand materials, product images, and other static exported images use the workspace readability baseline: normal informational text at least 4.5:1 against the background, and graphical cues required to understand the content at least 3:1; logos and pure decoration are not checked as informational text. For background images, gradients, and transparent overlays, use the least-favorable-position pairing method above.

For on-screen delivery, a title may use 3:1 only when the final display size can be verified to meet the large-text condition above; do not determine this directly from editing-canvas font size or source-file pixels. When print or projection cannot be reliably converted, check informational text at 4.5:1 by default, and recheck at actual size, viewing distance, and paper or projection environment; digital color value calculations do not replace proofs or on-site readability. Record output environments that could not be verified as unverified. This is a cross-media workspace baseline and does not mean printed materials or presentations have passed a full WCAG audit.

## Size and Adaptation

| Check | Criterion | Boundaries and evidence |
|---|---|---|
| Web pointer targets | Clickable area at least 24×24 CSS px | WCAG AA; spacing, equivalent, inline, user agent, or essential exceptions may apply; record the reason for each. The spacing exception is met when a 24 CSS px diameter circle centered on the target does not intersect another target or another undersized target's circle |
| Default touch targets | Mobile Web preferred 44×44 CSS px; iOS projects default 44×44 pt; Android default 48×48 dp | Workspace touch design starting points, not to be conflated with the Web AA minimum; check the actual hit area, platform, and adjacent targets, and do not treat icon size as the hit area |
| Text resize | No loss of content or functionality when zoomed to 200% | Web: check controls, labels, pop-ups; WCAG 2.2 criterion 1.4.4 excludes captions and images of text |
| Reflow | No loss of content/functionality and no two-dimensional scrolling for vertical content at 320 CSS px width and horizontal content at 256 CSS px height | Parts that truly need two-dimensional layout, such as maps and data tables, may be excepted; not every page must scroll only vertically |
| Font size starting points | Absent a project decision, body 16 CSS px and secondary text 14 CSS px; optional compact preset body 14 CSS px and secondary text no smaller than 12 CSS px | Workspace starting points, not WCAG minimum font sizes; do not solve overflow by shrinking key text; after adopting, check actual language, zoom, and reading |

When platform defaults conflict with specific component constraints, check the target platform's current official guidelines.

## Behavior and Verification

| Check | Criterion | Verification |
|---|---|---|
| Keyboard and focus | In-scope operations can be completed by keyboard; focus is visible, there are no unexpected traps, and focus goes somewhere reasonable after a pop-up closes | Actually operate item by item and record the environment; exceptions for inherently path-dependent operations such as freehand drawing are checked per the applicable standard |
| Dragging alternative (2.5.7) | Dragging functionality also offers a single-pointer method that does not require dragging, such as clicking previous/next, select then move, or entering a value | Completable independently by mouse click or touch tap; a keyboard equivalent does not substitute for this. Exceptions when dragging is essential or the function is a user agent feature not modified by the author; record the basis |
| Focus not obscured (2.4.11) | When a component receives keyboard focus, it is not entirely hidden by author-created content | Check sticky headers, bottom bars, overlays, and post-scroll states; AA allows partial obscuring, the workspace prefers fully visible. For movable content, check the initial position; if user-opened content can reveal the target without advancing focus, judge per the standard's exception |
| Form meaning and feedback | Fields remain identifiable after input; errors identify the object and how to recover; success messages come from actual results | Check applicable states: empty, filled, error, and after submission |
| Main flow | Run through at least one agreed main flow, plus this task's high-risk edges | Static designs verify only state and behavior descriptions; do not mark them as passing at runtime |
| Acceptance conclusion | Passed / Failed / Unverified / Not applicable (with reason) | For evidence and recording, see [Quality and Acceptance](quality.md); do not write passed without measurement |

For interaction details, see [Interaction Process, Motion, and Feedback](../domains/ui/interaction.md); this table does not replace a full accessibility audit for the target platform.

## Web Content and Motion

| Check | Acceptance action |
|---|---|
| Flashing (WCAG 2.3.1) | Prefer no more than three flashes in any one-second period. If exceeded, verify the general flash and red flash thresholds before accepting. Check the actual animation, including loops in animated artwork. |
| Moving content (2.2.2) | For nonessential motion, blinking or scrolling that starts automatically, lasts more than five seconds and appears alongside other content, verify a working pause, stop or hide control. For auto-updating content that starts automatically alongside other content, also allow control over update frequency or pausing, stopping or hiding it, regardless of duration, unless essential. Check the actual carousel or playback surface. |
| Status messages (4.1.3) | Trigger a status update such as a save result and verify that assistive technology announces it without moving focus. |
| Page structure | Verify that the document language and descriptive page title match the content. Distinguish pages by title. Check meaningful landmarks and heading nesting, avoiding skipped levels when introducing subsections. |
| Forced colors | In a supported forced-colors environment, verify that text, focus, selected states, controls and essential graphical cues remain distinguishable. Record the environment or mark the check unverified. |
| Informative charts | Provide a text equivalent conveying the key comparison or trend and access to values needed for the task. Distinguish series with labels, shapes or patterns as well as color. |

Heading order and forced-colors testing are workspace review checks. Apply Web conformance criteria to the actual delivery surface.
