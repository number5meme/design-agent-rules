# Frontend Acceptance

Read by task: [Workflow](workflow.md) · [Method](design.md) · [Acceptance](quality.md). For local edits, read only the affected sections.

## Comparison Verification

With a design baseline, compare the design and the actual page with the same content, state, and viewport; without a separate design, compare against project requirements and current design decisions, locating deviations in structure, typography, resources, and adaptation; then check agreed interactions and affected branches. Apply [Quality and Acceptance](../../standards/quality.md), and maintain the [cross-side mapping](../../standards/dual-delivery.md) only when dual delivery is confirmed.

For design-to-code comparisons:

- Use the in-scope mappings from [Reading and Breakdown](design.md#reading-and-breakdown) to track coverage. Check affected selected/unselected, expanded, filtered, identity-dependent, startup, and refreshed states as applicable; visiting a route alone does not cover its states. Missing reference states remain unknown unless an extension has a valid basis; do not claim direct frame equivalence for inferred designs.
- Before capturing a settled view, confirm the relevant fonts, images, and asynchronous content are ready. Check loading states separately rather than hiding their defects with a delay. Match the viewport, scroll position, and state; do not compare a long design canvas's bottom edge with a shorter browser viewport as if their coordinates were equivalent. Dynamic content differences alone are not defects, but their wrapping, density, and layout impact still need checking.
- Focus on hierarchy, typography, spacing, cropping, line breaks, and interaction states. Platform rendering differences may be accepted with an explanation when they do not impair readability, layout, or behavior. Preserve required accessibility cues, such as keyboard focus indicators, even when absent from the design.
- For review only, report findings in the reply unless the user requests a saved review. For implementation or a requested saved review, use the project review record or the verification section of a combined record. Associate each material discrepancy with its design target, observed result, evidence, and recheck status. Consolidate instances of the same issue and assign severity per [Issue Severity](../../standards/quality.md#issue-severity), retaining affected locations and states and their recheck coverage. Keep layout/asset checks, behavior tests, and visual comparison results distinct. No overflow, passing tests, or successful publication does not establish visual fidelity; limit completion claims to the pages and states actually checked.

Within scope, the following must hold: start and build are reproducible, and core paths and high-risk edges have runtime evidence; apply [Visuals](../ui/quality.md#visuals) and [Adaptation and Accessibility](../ui/quality.md#adaptation-and-accessibility) to the affected interface. Record actual integrations, mock services, and unverified environments separately.

If a browser or runtime cannot start, still run applicable checks that do not depend on it, such as logic tests and contrast calculations. List each applicable check left unverified by name. Any process claimed as completed in delivery records must have matching execution evidence.

Add only triggered UI checks; read linked methods as needed to implement or resolve a check:

- New or redesigned direction: [Product Fit and Design Judgment](../ui/quality.md#product-fit-and-design-judgment).
- Controls, content states, or operations: [Content and Flow](../ui/quality.md#content-and-flow).
- Gestures, scrolling, feedback, pop-ups, or animation: [Interaction Process and Motion](../ui/quality.md#interaction-process-and-motion).
- Component appearance or platform-behavior changes: applicable [Details and Native Environments](../ui/quality.md#details-and-native-environments) checks; web tasks do not require native-runtime verification.
- Charts: [Data Displays](../ui/quality.md#data-displays).
- Specific browser reproduction problems: the relevant [Web UI Review Reference](../../library/references/web-ui-review.md) section.

When a generated preview informed the design, compare the rendered page with the visual decisions actually adopted, rather than reproducing image artifacts or invented content. Verify real text, component wiring, responsive behavior, and required interaction states on the implementation; the preview itself is not acceptance evidence for those checks.

## Browser and Locale Checks

Apply only checks relevant to the page and its supported environments.

- For introduced or changed browser features, verify support against the recorded target browsers and versions. Exercise the affected normal path and any required fallback, checking that core content and operations remain available. Record tested environments and results; label simulated unsupported-feature checks as simulations and unavailable target environments as unverified. One browser's passing result does not establish cross-browser support.
- Where navigation exists, follow a navigation link with the keyboard and open it in a new tab. Use a real link with a destination for navigation and a button for an action.
- Test representative dates, quantities, measurements, and monetary amounts in each supported locale. Format them according to their meaning and use the currency from the transaction data. A language switch must preserve the amount and currency. Display identifiers such as order numbers, model codes, and postal codes in their prescribed form, preserving significant characters and leading zeros.
- In each supported theme, select text, scroll, focus a control by keyboard, and open a native select if present. Check readability and focus against the actual surfaces. Verify that the declared CSS `color-scheme` matches the active theme and that any `theme-color` matches the intended browser surface. Keep native styling when it passes.
- For images on web pages, check the meaning available to assistive technology. Informative images convey their relevant information in text. Decorative `img` elements and those fully described by adjacent text use `alt=""`. When an image is the only content of a link or button, verify that the control's accessible name identifies its destination or action.
- Apply the relevant [web accessibility checks](../../standards/defaults.md#web-content-and-motion) to the rendered page.
