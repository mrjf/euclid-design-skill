# Euclid Visual System

## Composition

Treat each major section as a page from a proposition book:

- Center an italic proposition heading at the top: `PROP. I.`, `PROP. II.`, etc.
- Use full-width ruled sections or framed proof plates, not nested cards.
- Pair strong type with one diagram or tool surface.
- Keep proof diagrams clean: one main circle or arc, one tangent/base, two or three relation lines, one or two filled angle chips.
- Use empty paper intentionally as margin, gutter, or pause around the proof.

## Color Roles

- `#0e558a` blue: primary circle, measured equality, principal arc.
- `#c43c35` red: alternate line, contradiction, comparison path.
- `#e4a412` ochre: known base, tangent, established construction.
- `#191816` ink: text, borders, final line, proof arrow.
- `#efe2c9` and `#f8efd9`: paper ground and proof plates.

## Typography

- Use large old-style serif display type for the main proposition phrase.
- Use upright roman text for body and marginal proof notes.
- Use italic sparingly for captions, proposition labels, and book-like emphasis.
- Use small caps for running heads such as `BOOK III. PROP. XXV. PROB.`.
- Use mono only for commands, tabular tokens, and machine-like controls.

## Borders And Surfaces

- Use thick ink rules: `3px` to `5px`.
- Keep border radius at `0` unless the host app already requires rounded corners.
- Use paper texture through subtle grid lines, small speckles, and warm tonal shifts.
- Buttons should be boxed, high contrast, and utilitarian.

## Square Dashes

The dashed construction line is a signature element. It must look like separated square blocks, not ordinary thin dashes.

SVG:

```css
.euclid-dash {
  fill: none;
  stroke-dasharray: 10 5;
  stroke-linecap: butt;
  stroke-linejoin: round;
  stroke-width: 10;
}
```

Choose `pathLength` so the pattern ends on a dash. For `10 5`, use:

```text
10, 25, 40, 55, 70, 85, 100, 115, 130, 145, 160, 175, 190, 205, 220
```

CSS inline dash:

```css
.inline-euclid-dash {
  width: 70px;
  height: 10px;
  color: var(--ink);
  background: repeating-linear-gradient(
    90deg,
    currentColor 0 10px,
    transparent 10px 15px
  );
}
```

For vertical dashes, use the same dimensions rotated or switch the gradient direction while preserving `10px` block and `5px` gap.

## Diagram Guidance

Clean diagrams beat exact reproductions. Do:

- Use one large circle or arc as the visual anchor.
- Let colored lines meet at meaningful points.
- Use filled sectors/chips for angles.
- Stop construction lines before text blocks.
- Keep captions below the figure in italic.

Avoid:

- Multiple overlapping circles unless required.
- Loose line fragments that look accidental.
- Slanted paragraph text.
- Diagrams that collide with drop caps or marginal notes.
- Decorative marks that do not explain relation.

## Responsive Rules

- On narrow screens, stack proposition heading, copy, and figure in that order.
- Keep command boxes wrapping cleanly and preserve the copy button.
- Reduce display type inside panels; do not let roman numerals or headings overflow.
- Verify mobile screenshots for text inside borders and button labels.
