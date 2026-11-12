# Frontend Acceptance

Read by task: [Workflow](workflow.md) · [Method](design.md) · [Acceptance](quality.md). For local edits, read only the affected sections.

## Comparison Verification

With a design baseline, compare the design and the actual page with the same content, state, and viewport; without a separate design, compare against project requirements and current design decisions, locating deviations in structure, typography, resources, and adaptation; then check agreed interactions and affected branches. Apply [Quality and Acceptance](../../standards/quality.md), and maintain the [cross-side mapping](../../standards/dual-delivery.md) only when dual delivery is confirmed.

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
- For each date, number or amount the page displays, test a representative value in the supported locale or locales. Use locale-aware formatters and the currency from the transaction data. If language switching is supported, a language change must preserve the amount and currency.
- In each supported theme, select text, scroll, focus a control by keyboard, and open a native select if present. Check readability and focus against the actual surfaces. Verify that the declared CSS `color-scheme` matches the active theme and that any `theme-color` matches the intended browser surface. Keep native styling when it passes.
- Apply the relevant [web accessibility checks](../../standards/defaults.md#web-content-and-motion) to the rendered page.
