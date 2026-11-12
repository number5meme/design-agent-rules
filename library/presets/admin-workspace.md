# Compact Neutral Blue Parameter Preset

See [When to Read a Preset](index.md#when-to-read-a-preset). Record the adopted dimensions and adjusted values per the project; parameters do not dictate page composition, and adaptation follows actual content.

## Color and Size

| Role | Light | Dark |
|---|---|---|
| Page background | #eeeeee | #181818 |
| Main container | #ffffff | #242424 |
| Control surface | #e8e8e8 | #393939 |
| Primary text | #202630 | #f3f5f8 |
| Secondary text | #515b68 | #bac4d1 |
| Action link | #245da8 | #a8cdff |
| Primary button background / text | #245da8 / #ffffff | #a8cdff / #202630 |
| Control border | #828282 | #858585 |
| Subtle divider | #e8e8e8 | #393939 |

- Body text reference 14px, supporting text 12px, larger body 16px; page titles choose 24/28/36px by level. For Chinese, use the project's existing font or a system Chinese font; body line height reference 1.5.
- Common spacing 4/8/16/24/32px; content area padding reference 24px. Control corner radius 3px; containers 6/9/12px.
- Top bar and sidebar brand area height reference 56px, kept aligned; adjustment is allowed when content grows or text is enlarged.
- Map colors as "base palette → semantic role → component state"; define light and dark themes separately, without directly inverting colors. Verify per [Color Pairing](../../standards/defaults.md#color-pairing).

## Status Reference

Adopt the `light / dark` themes in [Shared Status Pairs](status-pairs.json), following [Shared Status Usage](index.md#shared-status-usage). All four status foregrounds meet 4.5:1 on this preset's documented page background, main container, and control surface in each corresponding theme.
