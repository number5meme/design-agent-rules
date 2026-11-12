# Web Style Extraction

For extracting reusable visual rules from an existing web page. First determine the target pages, states, and applicable scope; identify third-party controls on the page separately.

## Observation and Checking

Check color, type, spacing, corner radius, layout, and component states using actual rendering and accessible style information. When style variables exist, check resolved values and where they are used; a value present in a stylesheet is not necessarily the currently visible style.

With screenshots only, mark color, size, and font judgments as estimates, and do not call them precise extraction. Keep unobserved hover, error, dark, or narrow-screen states as unknown; do not generalize site-wide rules from a single local area.

## Organization and Application

Group by semantics into background, text, action, state, and component roles, distinguishing base values, aliases, variants, and local overrides. Merge values that genuinely share a purpose, and keep meaningful differences; record font substitutes and original fonts separately.

For extraction alone, report the observed values, estimates, unknowns, and the pages and states inspected. Deliver the findings in the reply or the requested extraction artifact. Leave project variables and design decisions unchanged.

When the task also calls for adoption, map only the selected rules into the project's variable system or its existing design record. If a record is needed, use the [Style Template](../../templates/style-template.md). Distinguish adopted values and project adjustments from observations. Verify the result on representative project content, components, and viewports per [Style Consistency Review](style-consistency-review.md).
