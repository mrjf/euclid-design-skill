# Euclid Visual System

This reference describes how to get the Euclid-inspired look without making the content literally about Euclid or mathematics.

## Composition

Treat major sections as printed paper surfaces:

- Use full-width ruled sections, hard-edged plates, or framed tool panels.
- Pair strong type with a form, table, image, product surface, chart, editor, or geometric accent.
- Use thick borders and gutters to create a book-page rhythm.
- Use empty paper intentionally as margin, pause, or contrast.
- Keep real product content primary; geometry is a visual language, not mandatory subject matter.

## Color Roles

- `#0e558a` blue: primary accents, selected states, major line graphics.
- `#c43c35` red: warnings, comparisons, destructive states, alternate marks.
- `#e4a412` ochre: highlights, primary actions, baselines, active accents.
- `#191816` ink: text, borders, icons, dividers, strong emphasis.
- `#efe2c9` and `#f8efd9`: page ground, panels, forms, command boxes.

## Typography

- Use large old-style serif display type for the main page voice.
- Use upright roman text for body and UI copy.
- Use italic sparingly for captions, footnotes, and editorial emphasis.
- Use small caps for short metadata, nav labels, badges, and running labels.
- Use mono only for commands, tabular tokens, technical labels, and machine-like controls.

## Borders And Surfaces

- Use thick ink rules: `3px` to `5px`.
- Keep border radius at `0` unless the host app already requires rounded corners.
- Use paper texture through subtle grid lines, small speckles, and warm tonal shifts.
- Buttons should be boxed, high contrast, and utilitarian.
- Inputs should be paper fields with visible ink borders.

## Square Dashes

The square dashed mark is a signature element. It must look like separated square blocks, not ordinary thin dashes.

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
  color: var(--euclid-ink);
  background: repeating-linear-gradient(
    90deg,
    currentColor 0 10px,
    transparent 10px 15px
  );
}
```

For vertical dashes, use the same dimensions rotated or switch the gradient direction while preserving `10px` block and `5px` gap.

## Geometric Marks

Use geometry as accents, state indicators, data marks, empty-state art, or structural decoration.

Good motifs:

- Heavy circles or arcs.
- Straight colored rules.
- Square dashed paths.
- Filled wedges or sector chips.
- Ruled grids and dot fields.
- Hard-edged framed panels.

Keep marks simple and purposeful. They should support the layout, not require the page content to become a geometry lesson.

## Responsive Rules

- On narrow screens, stack text, controls, media, and panels in reading order.
- Keep command boxes wrapping cleanly and preserve copy buttons.
- Reduce display type inside panels so headings do not overflow.
- Reduce decorative mark density before shrinking useful text.
- Verify mobile screenshots for text inside borders and button labels.
