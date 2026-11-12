# Optional Parameter Presets

## When to Read a Preset

Read the corresponding file only when the user specifies a preset, explicit replication needs its parameters, or the task has agreed to use a ready-made starting point. A style name, product type, or "free rein" alone does not trigger this folder; do not read every preset to pick a style.

| Preset | Content |
|---|---|
| [Compact Neutral Blue](admin-workspace.md) | Light and dark surfaces, compact text and control sizes |
| [Bright Rounded Showcase](product-commerce.md) | Light surfaces, image-and-text and purchase control sizes |
| [Graphite Mint](dark-content.md) | Dark surfaces, accent color, and browsing control sizes |
| [Deep Gray Lavender](dark-software.md) | Dark showcase, heading and panel sizes |
| [Neutral Surfaces with Blue Actions](neutral-web.tokens.json) | Machine-readable type, component, material, and responsive parameters |

## Reading and Combining Parameters

Project variables are the primary record of actually adopted values; reference updates do not automatically override project changes. The neutral JSON uses the custom `design-agent-preset-v2` component recipe format and does not claim DTCG interchange compatibility; convert explicitly before handing it to external token tools. `extends` inherits a component in the same file, and curly-brace references point to keys in the same file; responsive configs are sorted ascending by minimum viewport width, and the last satisfied entry matches.

`contrastPairs` declares the solid-color check scope; `focus.light/dark` applies to all interactive components on the corresponding surface. Focus ring, selected border, and selected check each express a different meaning and may appear together. Transparent materials, image backgrounds, and actual layouts still need measurement.

This version of the neutral preset reorganizes type, corner radius, spacing, layout, responsive settings, effects, and common components; common integer scales are not brand-specific parameters, and do not adjust them randomly to avoid numeric coincidences. When upgrading old JSON, migrate by component responsibility; do not automatically map old component keys to new components; values already adopted by existing projects do not change automatically.

## Shared Status Usage

[Shared Status Pairs](status-pairs.json) is the single source of status values. The JSON's `statusSource` is a dependency path relative to the current file; read that file's `status[statusName][theme]`, and load only the themes specified in `statusThemes`; Markdown presets specify themes under "Status Reference". background denotes the reference pairing; a preset's own backgrounds that it explicitly lists and verifies may also use the same status foregrounds, without being forced to the reference background. Shared values are not copied into each preset; when using a JSON recipe, carry the dependency file along. Backgrounds, transparency, or uses beyond the verified scope require re-verification per [Color Pairing](../../standards/defaults.md#color-pairing).

Pair status foregrounds with text or icons so color is not the only cue. They are verified as foregrounds, not as button backgrounds. Use the preset's documented action pairs for buttons; any different pairing needs its own verification.

## Exporting Tokens to DTCG 2025.10

Convert only the values required by the recipient. For example, the recipe's `colors.primary` value `#245da8` becomes this sRGB token, with channels normalized from 36, 93 and 168:

```json
{
  "colors": {
    "primary": {
      "$type": "color",
      "$value": {
        "colorSpace": "srgb",
        "components": [0.14117647, 0.36470588, 0.65882353]
      }
    }
  }
}
```

Convert a size such as `48px` to a `dimension` token with `$value` of `{"value":48,"unit":"px"}`. Preserve aliases to exported tokens by their output paths, for example `"{colors.primary}"`, and verify that they resolve to the intended types. Resolve the recipe's shared status dependency for the requested themes. Component inheritance, responsive selection and contrast test pairs are recipe behavior or verification metadata. Document them separately when needed. Validate the exported token subset against the [DTCG 2025.10 format](https://www.designtokens.org/tr/2025.10/format/) and check the values in the receiving tool.

For other recipe values, choose the type by meaning and verify that the conversion preserves it:

- DTCG dimensions accept px or rem. Keep a measure such as `68ch` as a layout rule outside the token export unless an equivalent supported dimension is justified for the intended font and context.
- A zero letter spacing is still a dimension in a typography token. Encode it as `{"value":0,"unit":"px"}`. A unitless line-height ratio remains a number.
- Export a single font family as a string or a fallback list as an ordered array of family names. Parse the CSS list with its quoting intact before extracting the names.
- Parse border and shadow strings into their typed composite fields. Preserve border width, style and color, and each shadow's offsets, blur, spread, color and inset behavior. Preserve layer order for multiple shadows. Leave values outside the token subset and explain the gap if they cannot be represented faithfully.
