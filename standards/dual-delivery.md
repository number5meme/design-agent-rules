# Figma and Frontend Dual Delivery Agreement

Use only when the user has confirmed dual delivery of Figma and frontend.

## Shared Baseline
Reuse the project handoff record to maintain versions and mappings. Pages, states, and components use persistently locatable identifiers or links; prefer existing node and code identifiers, and add numbering only when there is no reliable correspondence. Keep mappings valid after renaming.

- Visual structure, component variants, and design notes are based on the currently selected design file version; record whether it was user-specified or autonomously selected within the authorized scope.
- Executable interactions and adaptive behavior use the accepted frontend version as runtime evidence.
- Business rules follow the current primary scope record and the approved requirements it links.
- When the two conflict, first log the difference and fix it per project decisions; do not assume either side is correct by default.
- Variables such as colors and spacing have a single explicit source of truth, which may be Figma variables, code variables, or an existing machine-readable file; record location and version, and align both sides to it; create exchange files only when file exchange or automatic sync is needed. When tools do not support automatic sync, check manually and record it; do not claim automatic sync.

## Figma Done Criteria
- Accessible file and key node links; pages, components, and states clearly named.
- Main screens built from editable text, layers, and components; screenshots do not replace source files.
- Appropriate auto layout, constraints, component instances, variants, and variables; do not force one-off elements into components for formality.
- Flows, adaptation, scrolling/fixed regions, motion, and exceptions are documented.
- Assets are exportable; fonts and licensing are clear. Permissions meet actual recipients' needs.
- Actually view key nodes, and reopen the final output per [Design File and Export Acceptance](quality.md#design-file-and-export-acceptance); record the version matching the frontend.

## Frontend Done Criteria
- Uses the agreed tech stack with a maintainable structure, including start, build, and check instructions and dependency lock files (where applicable).
- Core paths are actually operable and necessary states are reproducible; mapping to Figma is complete.
- Mock data, mock APIs, real integration boundaries, and pending integrations are clearly stated.
- Target viewports and key edge-case content are tested; interaction errors and console errors have check records.
- Resources are complete; use of images and fonts complies with project licensing terms.
- Demo controls live in a standalone showcase mode or development entry, not mixed into the production UI.

## Alignment Method

Sync affected layout and behavior in the same round. Record remaining differences; incomplete alignment cannot be called dual delivery complete.

Save same-version screenshots in the project's evidence location, suggested names `P01-default-390x844-version-figma.png` and `…-web.png`. Compare side by side after fixing content, viewport, scroll position, and state.

Focus on hierarchy, typography, spacing, image cropping, line breaks, fixed elements, and interaction states. Platform font rendering differences may be recorded as accepted deviations; layout/content differences must be addressed. Screenshot checks do not replace interaction checks.

## Delivery Status
Record Figma, frontend, cross-side consistency, and production integration status separately. Call it "dual delivery complete" only when the first three meet the agreed requirements. Real services, permissions, security, performance, monitoring, and release are scoped and owned by the project; do not claim "ready to go live" without verification.

## Interaction and Motion Mapping
Key interactions reuse locatable identifiers or mappings, numbering them only when missing. Figma records component states, triggers/transitions, and notes; the frontend implements gestures, scrolling, and interruption; the handoff record maintains the cross-side mapping and links the relevant primary records. The design record or its linked parameter source maintains applicable duration/easing, thresholds, snapping, and layering. The review record maintains reproduction steps and actual dynamic evidence. Reuse equivalent project records or corresponding sections of a combined record without copying their contents into the handoff mapping. Clearly mark behavior the tools cannot express equivalently, explain it with actual runtime evidence, and do not claim it is fully identical.
