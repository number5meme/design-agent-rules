# Series Visual Consistency

For matching images and materials of the same brand, character, product, or theme. Handle independent concept exploration and series extension separately: the former compares directions; the latter maintains identity and the visual system and produces the agreed quantity.

## Baseline and Variable Items

Use the currently selected actual assets and necessary style notes as the baseline. When the baseline is not yet set, complete a representative sample first; when the user has authorized autonomous choice, you may select and continue without adding an approval gate.

Record fixed items and variable items per task: a character's proportions and features, a product's structure and materials, a logo's shape and wordmark, a series' colors and graphic language; action, viewpoint, content, cropping, or carrier may vary as agreed. Aspect ratio is determined by each item's purpose; consistency does not require all materials to be the same size.

For series that scale through element combinations, first determine which elements can be swapped independently and which must be produced together, and check compatibility of pose, occlusion, proportion, and content pairing. After validating with representative samples, calculate quantity and production gaps from actually usable combinations, excluding conflicts and meaningless repetition; the theoretical number of permutations does not equal the number of acceptable finished pieces. Maintain only the pairing rules the current task needs.

## Production and Referencing

- Link actual files and their purposes by semantic names such as key visual, side view, or structural close-up; do not guess content ownership from the order a tool returns results.
- Reuse source objects, components, assets, or generation reference images according to the production method. When fidelity is required, text descriptions cannot replace existing assets; using a reference image in generation does not mean fidelity has passed.
- When there are multiple references, state each one's purpose and check whether the tool can accept them together. Adjust the production plan when this exceeds capability; do not silently drop references that affect the result.
- When derived content depends on the baseline, wait until it is ready; independent content may proceed. Task status and retries follow the [Workflow](workflow.md#async-operations-and-retries).
- Across turns, first verify that assets are still accessible and are still the currently selected version. Handle style changes per [Style Adjustment](workflow.md#style-adjustment), then register the new baseline and affected scope.

## Set Checks

Compare item by item against the fixed items, then check color, typography, proportion, material, and rhythm side by side. Each item should fulfill its own purpose, avoiding meaningless repetition; intentional reuse of the same asset may stay, and do not redo work just to create difference.

Record per-piece status and whole-set coverage separately: partial success may deliver completed content, but the whole set cannot be called complete. Record missing, distorted, and unverified items per [Quality and Acceptance](quality.md).
