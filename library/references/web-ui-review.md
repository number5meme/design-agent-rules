# Web UI Review Reference

## When to Consult

When a web implementation or review involves the issues in the table below, choose only the relevant rows. Static designs can check expression, but cannot be used to claim keyboard, performance, or assistive technology tests passed.

## Check Methods

| Focus | Verification |
|---|---|
| Semantics and names | Check semantics of action/navigation elements, icon button names, and form labels; perform actual operations with the keyboard |
| Focus | Walk the affected path; check focus is visible and not obscured by overlays, and returns to a reasonable position after closing a pop-up |
| Forms | Try filling, pasting, and submitting invalid data; check input types, autofill, error location, and recovery |
| Motion | Enable reduced motion, and operate again mid-transition; check response and final state |
| Images and long content | Simulate slow loading, long text, and empty content; watch for jumps, overflow, and reading order |
| Performance and state | When stutter appears, measure before locating; when back navigation or sharing is involved, check state restoration and link behavior |

Distinguish code inspection, browser observation, and device testing in the evidence. For review only, report it in the reply unless the user requests a saved review. For implementation work, use the existing project record.

## Mobile Web Adaptation

Choose checks by symptom; do not uniformly override browser behavior:

| Focus | Implementation and verification |
|---|---|
| Hover and press | Enable hover effects by input capability, and keep press feedback on touch; check that states recover when touch and mouse are mixed, and do not guess input method from screen width |
| Visible height | Evaluate dynamic viewport units for containers that should follow browser bar changes, and small viewport units for areas that need a stable first screen; test with the address bar expanded and collapsed, and do not mechanically replace all heights |
| Soft keyboard and safe areas | Check that after focusing an input the field, error message, and submit entry are visible, and the layout recovers after the keyboard closes; do not double-count spacing for safe areas and fixed action areas |
| Zoom and text | Keep user zoom; when input focus causes unexpected zoom-in, check the actual font size and target browsers, and do not mask the problem by disabling zoom |
| Scrolling and gestures | Set touch handling on the actual gesture area and keep needed vertical scrolling; restrict scroll chaining or pull-to-refresh only when the business requires it and it is verified to have no side effects |
| Selection and tap feedback | Keep body text selectable, and handle long-press selection on controls as needed; ensure clear alternative feedback before removing the browser tap highlight |

On real devices, check the browser bars, keyboard, gestures, and orientation changes relevant to this task. Without devices, state what code inspection and emulation covered, and list device behavior as unverified.

## Applicable Boundaries

Do not write all state into the URL, do not force virtualization by a fixed list length, do not uniformly disable autofill, and do not uniformly set title capitalization. Specific techniques, copy, and optimization depend on the project, language, browser, and measurements; native apps do not directly apply web properties. Accept per the current task; do not unnecessarily expand test infrastructure or install tools just to complete a checklist; handle necessary dependencies per the [Current Basis and Tool Route](../../standards/workflow.md#current-basis-and-tool-route).

Full accessibility conformance requires a separate audit.
