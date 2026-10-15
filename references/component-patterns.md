# Component relationships

Use these patterns as diagnostic questions, not fixed pixel recipes. A reference may already be correct.

## Large numeral with a stacked label

Example: a large `33` alongside `days` / `left` inside a rounded rectangle.

- Treat the numeral and stacked label as one group inside the container.
- Inspect the label's total line box, the numeral's visible height, and the gap between them separately.
- Determine the intended vertical relationship from the reference or surrounding components.
- Check changing digit counts and longer labels; do not pin positions to the width of `33`.
- Preserve deliberate proportions rather than making both pieces the same size or weight.

## Text with a magnifying glass in a pill

- Check the text-icon gap, the whole group's placement, and the external padding as separate relationships.
- Inspect SVG viewBox whitespace and path placement. The lens and handle have different visual mass; bounding-box centering alone cannot establish balance.
- Preserve the icon's proportions and stroke weight. Check the text baseline and line height before shifting the icon.
- Compare the final button at ordinary viewing size. Do not automatically assign unequal padding because an icon is asymmetric.

## Arrow in a circular control inside a pill

- Inspect arrow-to-circle positioning separately from circle-to-pill positioning.
- Compare top, bottom, and trailing insets relative to the intended border edges; account for border thickness.
- Distinguish the arrow's visible path from its SVG viewport. Check the shaft and head as a whole.
- Preserve the focus ring and hit area. Do not use clipping or absolute positions that fail when the outer label wraps.

## Repeated components and deliberate exceptions

Compare equivalent roles, sizes, and states. Do not flag a hero heading for differing from a card title, or an intentional asymmetric composition for failing a symmetry rule. An optical correction justified for one glyph is not automatically appropriate for every icon in the library.
