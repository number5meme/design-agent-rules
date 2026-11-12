# Workspace Design Method

For management, configuration, and data operations. First judge whether the user is finding, comparing, editing, or monitoring objects, then decide information density, navigation, and action placement.

## Content Organization

- Choose sidebar, top bar, or other navigation structures by information architecture; when combining, define responsibilities and avoid duplicate entry points.
- Arrange filters, batch actions, and data areas by usage frequency and target object, without a fixed order. Batch actions clearly present the current selection scope.
- Tables suit field-by-field comparison; lists or cards suit identifying objects; complex tasks can combine them, but do not stack panels for a "professional feel".
- Values, units, precision, and alignment support comparison, and important identifiers remain recognizable on narrow screens. Icons help identify actions and do not replace business content.

## Visuals and Adaptation

Color, type, corner radius, and density are decided by the project brand, content, and usage environment. Define surface, text, action, and status roles, and verify per [Color Pairing](../../standards/defaults.md#color-pairing); design light and dark themes separately, without directly inverting colors.

Prefer reusing existing components and theme interfaces. When space is short, choose collapsed navigation, grouped filters, horizontal scrolling, or reflow by task; breakpoints are decided by actual content. Check long names, multiple conditions, no results, failures, batch selection, and applicable theme states.
