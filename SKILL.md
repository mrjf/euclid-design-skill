---
name: euclid-design-skill
description: Apply a Euclid-inspired paper-and-geometry design system to web pages, applications, documents, components, and visual assets. Use when the user asks for old mathematical book styling, Euclidean geometry aesthetics, thick colored rules, chunky square dashes, ornamental initials, serif book typography, paper texture, or a rigorous print-like interface.
license: MIT
metadata:
  author: mrjf
  version: "1.2"
---

# Euclid Design System

A generic visual design system inspired by Euclidean geometry books: warm paper surfaces, old-style serif typography, thick ink borders, colored construction marks, ornamental initials, and square dashed lines. It is a visual language for any subject: SaaS tools, portfolios, docs, dashboards, editors, forms, games, reports, landing pages, or product interfaces.

Use this skill to give a page or component the Euclid look. For a full static starter, copy `assets/static-site/` into the target project and adapt it. For extra visual references, read `references/visual-system.md`.

## The Look

The Euclid look is tactile, printed, and exact:

- Warm cream paper instead of neutral white.
- Thick black rules instead of soft dividers.
- Large old-style serif display text instead of generic sans-serif hero type.
- Small caps, mono labels, and framed initials for editorial structure.
- Blue, red, and ochre marks used like annotation colors.
- Chunky square dash segments for construction lines, separators, progress marks, and decorative rules.
- Simple geometric accents: circles, arcs, sectors, line fragments, grids, and measured-looking marks.

Do not force the content to be about mathematics. Use the system as a surface treatment and layout grammar.

## Core Principles

1. **Paper first.** Start with a page-like field: cream ground, subtle grid, light speckle, and quiet tonal variation.
2. **Ink defines structure.** Use thick black borders, dividers, and frames to give the interface authority.
3. **Color is annotation.** Blue, red, and ochre should feel like printed marks added to the page, not a conventional brand gradient.
4. **Geometry is optional language.** Add circles, arcs, sectors, rays, and ruled marks when they support the layout or mood; do not invent a literal diagram if the UI does not need one.
5. **Type sets the era.** Use high-contrast serif display type, upright readable body text, small caps labels, and mono controls.
6. **Dashes are signature.** The chunky square dashed line is the most recognizable motif; use it consistently across horizontal, vertical, and diagonal marks.

## Implementation Workflow

1. **Define tokens.** Add paper, ink, blue, red, ochre, border, dash, and type tokens before component work.
2. **Build the paper field.** Apply warm paper color and subtle ruled texture to the page or major panels.
3. **Choose a layout pattern.** Pick a page frame, editorial split, archive/table, tool panel, poster plate, or form layout based on the product need.
4. **Set the type hierarchy.** Use serif display text for high-level statements, readable serif body copy, mono labels, and small caps metadata.
5. **Add thick rules.** Frame important areas with 3px to 6px ink borders; use horizontal and vertical rules as real layout structure.
6. **Use colored marks.** Add blue, red, or ochre lines, swatches, chips, badges, or state marks where they clarify hierarchy or action.
7. **Add geometric accents only where useful.** Use SVG/CSS geometry for decoration, states, data, empty panels, or hero art, but keep the interface content primary.
8. **Verify in browser.** Check text fit, mobile layout, dash rhythm, focus states, copy buttons, and form controls.

## Tokens

Use these defaults unless the target project already has equivalent theme variables:

```css
:root {
  --euclid-paper: #efe2c9;
  --euclid-paper-light: #f8efd9;
  --euclid-paper-dark: #d7c3a2;
  --euclid-ink: #191816;
  --euclid-blue: #0e558a;
  --euclid-red: #c43c35;
  --euclid-ochre: #e4a412;
  --euclid-muted: rgba(25, 24, 22, 0.58);
  --euclid-rule: 4px;
  --euclid-rule-heavy: 6px;
  --euclid-dash-block: 10px;
  --euclid-dash-gap: 5px;
}
```

### Color Roles

| Role | Hex | Use |
| ---- | --- | --- |
| Paper | `#efe2c9` | Page background, inactive areas, quiet section fields |
| Light paper | `#f8efd9` | Main panels, form fields, command boxes, framed surfaces |
| Dark paper | `#d7c3a2` | Offset shadows, gutters, inset page edges |
| Ink | `#191816` | Text, borders, dividers, icons, final emphasis |
| Euclid blue | `#0e558a` | Primary accent marks, selected states, main line graphics |
| Vermilion red | `#c43c35` | Warnings, comparison marks, destructive or alternate states |
| Ochre | `#e4a412` | Primary buttons, highlights, baselines, active accents |

Color should appear as solid printed ink. Prefer flat fills and thick strokes over gradients.

## Typography

Primary display and prose:

```css
font-family: "Cormorant Garamond", Georgia, "Times New Roman", serif;
```

Small caps and ornamental initials:

```css
font-family: "IM Fell English SC", "Cormorant Garamond", Georgia, serif;
```

Commands, labels, coordinates, and data:

```css
font-family: "IBM Plex Mono", "Courier New", monospace;
```

### Type Scale

| Role | CSS starting point | Notes |
| ---- | ------------------ | ----- |
| Display | `clamp(3.4rem, 8vw, 8rem)` | Large old-style serif statements |
| Page title | `clamp(2.4rem, 5vw, 5rem)` | Section or screen titles |
| Panel heading | `clamp(1.6rem, 3vw, 3rem)` | Cards, panels, modules |
| Body | `1.15rem` to `1.4rem` | Upright, generous leading, readable |
| Caption | `0.95rem` to `1.1rem` | Optional italic notes, image captions, footnotes |
| Mono label | `0.8rem` to `1rem` | Uppercase labels, commands, table headers |

Typographic habits:

- Use large old-style serif type for the main page voice.
- Use upright roman text for body copy and UI descriptions.
- Use italic sparingly for captions, footnotes, and editorial emphasis.
- Use mono for controls, commands, tabular data, and technical labels.
- Use small caps for short metadata, nav labels, running labels, and badges.
- Keep display letter spacing at `0`; use tracking only for mono and small uppercase labels.
- Balance large headings manually so long words do not hit borders or adjacent graphics.

## Layout Patterns

### Page Frame

Use for home screens, docs, product pages, settings pages, or focused workflows.

- Warm paper page background.
- One or more thick ruled panels.
- Large serif title or statement.
- Clear action row, table, editor, form, or content region.
- Optional folio-style labels in small caps or mono, based on content.

### Editorial Split

Use when pairing text with controls, examples, media, or a visual accent.

- One column can carry large serif text.
- The other column can carry a panel, form, table, product screenshot, or geometric illustration.
- Use a thick vertical rule, gutter, or frame to separate the areas.
- On mobile, stack in the natural reading order.

### Archive Or Table View

Use for dashboards, collections, search results, admin pages, changelogs, and indexes.

- Use boxed filters or a left rail when there is meaningful navigation.
- Use thick row dividers and mono headers.
- Add mini swatches, line samples, status chips, or geometric icons for scanability.
- Keep dense data readable; let tables scroll horizontally when needed.

### Poster Plate

Use for high-impact pages, announcements, splash screens, reports, and visual summaries.

- Large framed paper plate.
- Big serif headline or product phrase.
- One strong supporting object: a screenshot, chart, geometric composition, product mockup, or typographic specimen.
- Small caps metadata, colored rules, and square dashes for printed-poster energy.

### Tool Panel

Use for editors, calculators, generators, configuration screens, and interactive app surfaces.

- Keep the tool itself central.
- Frame control groups with ink rules.
- Use paper fields, mono labels, and print-block buttons.
- Use colored marks to show selected mode, state, error, or progress.

### Form

Use for onboarding, settings, contact flows, registration, and data entry.

- Inputs are paper fields with thick ink borders.
- Labels use mono or small caps.
- Help text uses muted serif or mono, depending on density.
- Validation can use red rules, red side marks, or boxed notes.

## Components

### Surfaces

Use rectangular paper surfaces with hard corners. A card is acceptable for a repeated object, but avoid making the whole page look like generic floating cards.

```css
.euclid-plate {
  background: var(--euclid-paper-light);
  border: var(--euclid-rule) solid var(--euclid-ink);
  box-shadow: 14px 14px 0 var(--euclid-paper-dark);
}
```

### Buttons

Buttons should feel like print blocks:

```css
.euclid-button {
  min-height: 44px;
  padding: 0.8rem 1.1rem;
  border: var(--euclid-rule) solid var(--euclid-ink);
  background: var(--euclid-ochre);
  color: var(--euclid-ink);
  font-family: "IBM Plex Mono", monospace;
  font-weight: 700;
  text-transform: uppercase;
}
```

Use hover and active states as physical print effects: slight offset, inset shadow, darker paper, or heavier rule.

### Inputs

Inputs, selects, and textareas use paper fill, ink borders, serif values, and mono labels.

```css
.euclid-field {
  background: var(--euclid-paper-light);
  border: var(--euclid-rule) solid var(--euclid-ink);
  color: var(--euclid-ink);
  font: 1.2rem "Cormorant Garamond", Georgia, serif;
}
```

### Drop Caps

Drop caps and initial blocks are optional editorial accents.

- Use an ink square with one or two paper inner rules.
- Center the glyph optically in the square.
- Keep the letter upright and high-contrast.
- Use sparingly, typically at the start of a prominent text block.

### Tables And Lists

Tables should look like ruled ledgers:

- Thick top and bottom rules.
- Mono uppercase headers.
- Serif values or mono numeric data.
- Strong row dividers.
- Optional swatches, line samples, or glyph marks in leading cells.

### Command Boxes

Command boxes are useful for install snippets, code, copyable config, or exact instructions.

- Use a framed paper box.
- Put a short colored rule or dash sample before the command.
- Keep the command text mono.
- Provide a real copy button when the command is meant to be copied.

### Badges And Chips

Badges should look printed, not pill-like.

- Prefer rectangular chips with ink borders.
- Use mono uppercase labels.
- Use colored side marks, underlines, or small swatches for state.
- Keep border radius at `0` unless the host app already has rounded components.

## Geometry And Marks

Geometry is a style ingredient, not a content requirement. Use these marks to add the Euclid feel to any interface.

### Useful Motifs

| Motif | Use |
| ----- | --- |
| Circle or arc | Avatar frame, progress ring, chart accent, empty-state mark |
| Straight rule | Divider, baseline, section separator, button accent |
| Square dashed rule | Construction accent, loading/progress, relation between UI areas |
| Filled sector | Angle-like chip, status wedge, chart slice, decorative corner |
| Thick frame | Modal, page plate, card, screenshot border, tool boundary |
| Grid or dot field | Paper texture, canvas background, editor surface |

### Stroke Classes

Use SVG when drawing custom geometry, charts, marks, or hero art. CSS borders and gradients are fine for simple rules and dash samples.

```css
.stroke-ink,
.stroke-blue,
.stroke-red,
.stroke-ochre {
  fill: none;
  stroke-width: 6;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.stroke-ink { stroke: var(--euclid-ink); }
.stroke-blue { stroke: var(--euclid-blue); }
.stroke-red { stroke: var(--euclid-red); }
.stroke-ochre { stroke: var(--euclid-ochre); }
```

### Square Dashes

The Euclid dash is chunky and block-like. Use butt caps so each segment reads as a square chunk.

```css
.euclid-dash {
  fill: none;
  stroke-width: 10;
  stroke-linecap: butt;
  stroke-linejoin: round;
  stroke-dasharray: 10 5;
}
```

For SVG paths, use `pathLength` values that complete the `10 5` dash cycle cleanly:

```html
<path class="stroke-blue euclid-dash" pathLength="130" d="M20 20 L150 80" />
```

Good lengths include:

```text
10, 25, 40, 55, 70, 85, 100, 115, 130, 145, 160, 175, 190, 205, 220
```

For horizontal or vertical UI dash samples, use the same block and gap:

```css
.euclid-inline-dash {
  width: 70px;
  height: 10px;
  background: repeating-linear-gradient(
    90deg,
    currentColor 0 10px,
    transparent 10px 15px
  );
}
```

For vertical samples, rotate the element or use a `180deg` gradient while preserving the same `10px` block and `5px` gap.

### Mark Density

The system works best when marks are deliberate:

- Use one or two geometric motifs per major area.
- Keep colored lines thick enough to feel printed.
- Leave paper margin around marks so they do not look like accidental decoration.
- Let real product content remain more important than the ornament.

## Layout And Responsiveness

Use mobile-first layouts. The design language can be ornate, but the structure must remain practical.

Base layout:

```css
.euclid-section {
  padding: clamp(4rem, 8vw, 8rem) clamp(1rem, 5vw, 6rem);
}

.euclid-grid {
  display: grid;
  grid-template-columns: repeat(12, minmax(0, 1fr));
  gap: clamp(1rem, 3vw, 2rem);
}
```

Responsive rules:

- Below tablet width, stack text, controls, media, and panels in reading order.
- Keep framed plates and tool panels within the viewport width.
- Use `clamp()` for display sizes and container widths.
- Preserve at least `44px` touch targets.
- Let tables scroll horizontally when the data requires it.
- Reduce decorative mark density on small screens before shrinking text too far.

## Tailwind Translation

If the host app uses Tailwind, express the system with arbitrary values and CSS variables:

```html
<section class="bg-[var(--euclid-paper)] text-[var(--euclid-ink)]">
  <div class="border-[4px] border-[var(--euclid-ink)] bg-[var(--euclid-paper-light)]">
    ...
  </div>
</section>
```

Use project tokens in `theme.extend` when you will repeat the style across many components:

```js
theme: {
  extend: {
    colors: {
      euclid: {
        paper: "#efe2c9",
        ink: "#191816",
        blue: "#0e558a",
        red: "#c43c35",
        ochre: "#e4a412"
      }
    }
  }
}
```

## Interaction States

Interactive states should preserve the print language:

- Hover: slight inset movement, darker paper, or thicker rule.
- Focus: visible ink outline with a small colored offset rule.
- Active: pressed block effect, ochre darkening, or reduced shadow.
- Disabled: lower ink opacity and no colored emphasis.
- Error: red rule, red side mark, and a readable text explanation.
- Success: blue or ochre rule plus a concise result note.

## Accessibility

- Maintain high contrast between ink and paper.
- Keep text selectable when possible; avoid rendering real paragraphs as images.
- Add accessible names to custom SVGs and decorative mark groups where appropriate.
- Do not rely on color alone; pair color roles with labels, line styles, icons, or position.
- Respect reduced-motion settings if adding drawing or page-texture animations.
- Keep focus order aligned with the visual reading order.

## Visual QA Checklist

Before finishing, inspect the page in a browser:

- Paper texture, borders, typography, and color marks create the Euclid look without overwhelming the product content.
- Square dashes use the same block rhythm horizontally, vertically, and diagonally.
- Text fits within frames, buttons, tables, cards, and form fields at mobile and desktop widths.
- Drop-cap letters are optically centered when used.
- Copy buttons, forms, links, and other interactive elements work.
- Decorative geometry does not collide with real UI, labels, or body text.
- The design still works after real user content replaces placeholder text.
