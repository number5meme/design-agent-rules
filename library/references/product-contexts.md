# Product Category Judgment Cues

Choose applicable cues by user, task, data, and platform to form design judgments to be verified. Categories not listed can be judged directly from the current task; case and counterexample support is required only when adding category knowledge to the library.

| Attribute | Ask first | Design it may affect | Avoid mechanically applying |
|---|---|---|---|
| Finance / trading / wallet | Is the user discovering opportunities, deciding, or managing assets right now? Is the amount available, total, valuation, or pending settlement? When is the data trustworthy? | Account reachability, number hierarchy/alignment, units and precision, unknown/failed/stale, pre- and post-submission states, privacy controls | Finance does not mean screens full of charts, dark mode, or green; do not show an unknown balance as 0; do not fabricate endorsements to look trustworthy |
| Collectibles / product discovery | How do users identify and compare? Is the main image clear? What identity does it belong to? | Subject proportion, cropping, asset consistency, identity relationships, browsing density and filtering | Do not treat heavy decoration/rarity tags as a sense of collecting; do not copy reference brand assets |
| Content / social | Is the user consuming, expressing, or finding people? Where is the public/private line? | Reading rhythm, author and content hierarchy, interaction feedback, publishing state | Do not automatically add feeds, follows, recommendation algorithms, or growth entry points |
| Tools / collaboration | How often does the user operate, on what objects, and at what cost of error? | Operating efficiency, current context, edit/save state, permissions, batch operations (in scope only) | Do not add panels, data cards, or menus to look "professional" |

## Composite Products

One product can use multiple cues, but assign responsibilities to modules; do not stack every convention of every category onto the home page.

## Library Entry Format

Category / task and scenario / observation and evidence / derived action / applicable conditions / counterexamples / project result. Promote knowledge status from candidate only after real verification; mark user preferences separately and do not treat them as category rules.
