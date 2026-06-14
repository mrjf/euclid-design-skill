---
name: euclid-design-skill
description: Apply a Euclid proof-page design system to web pages, applications, documents, components, and visual assets. Use when the user asks for Euclid, geometric proof, old mathematical book, proposition-page, theorem, colored construction lines, chunky dashed geometry, ornamental initials, book typography, or a rigorous paper-and-ink design language.
license: MIT
metadata:
  author: mrjf
  version: "1.1"
---

# Euclid Design System

A design system rooted in old mathematical proposition pages: serif book typography, paper surfaces, thick ink rules, colored geometric notation, ornamental initials, and square construction dashes. The goal is not antique decoration. The goal is to make an interface feel like a proof: ordered, legible, relational, and visually exact.

Use this skill to design a new page or component in the Euclid system. For a full static starter, copy `assets/static-site/` into the target project and adapt it. For extra reference rules, read `references/visual-system.md`.

## Design Intent

The Euclid system treats every screen as a proposition sheet. Text states the claim, geometry explains the relation, color encodes meaning, and heavy rules organize the proof. A finished page should feel tactile, editorial, and precise while still functioning as modern UI.

Design from the content outward:

1. Identify the claim, task, object, or state the page is proving.
2. Give it a proposition label such as `PROP. I.` or `BOOK III. PROP. XVI.`
3. Build one strong text block and one clear figure, table, form, or tool surface.
4. Use color only when it carries a role in the system.
5. Use thick ruled boundaries and square dashes to make structure visible.

## Core Principles

1. **The page is a proof.** Every section should have a visible proposition role: title, statement, construction, evidence, result, or action.
2. **Geometry is notation.** Circles, arcs, rays, tangent lines, filled angles, and dashed construction paths should explain relationships, not sit as unrelated ornament.
3. **Color has meaning.** Blue, red, ochre, and ink each have a stable semantic role. Do not pick colors ad hoc once the role is established.
4. **Rules create authority.** Thick borders, horizontal dividers, and boxed controls are part of the visual grammar.
5. **Typography carries the voice.** Large old-style serif display text creates the book-page feeling; small caps and mono labels organize the interface.
6. **Restraint beats reproduction.** Use the source language cleanly. A simplified drawn diagram is usually stronger than a literal collage of book-page fragments.

## Implementation Workflow

1. **Choose the composition.** Pick a proof page, editorial spread, archive/table view, form, dashboard, or poster plate based on the user’s task.
2. **Set tokens first.** Define the paper, ink, blue, red, ochre, rules, dash size, and typefaces as variables before styling components.
3. **Create the paper field.** Use a warm page background with subtle grid or speckle texture. Put the content on ruled pages or framed plates.
4. **Place the proposition heading.** Use centered italic proposition labels for major sections. Use small caps running heads for book/chapter context.
5. **Build the main content block.** Keep prose upright and readable. Let the display type be large, but ensure all words fit at mobile and desktop sizes.
6. **Draw the figure.** Use SVG or canvas for proof diagrams. Keep the construction clean and align it to the surrounding grid.
7. **Design controls as proof objects.** Buttons, inputs, cards, tables, and command boxes should use the same paper, ink, border, and color notation.
8. **Verify visually.** Check desktop and mobile renderings for text fit, diagram clarity, dash construction, and interactive states.

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
| Paper | `#efe2c9` | Page field, section ground, inactive surfaces |
| Light paper | `#f8efd9` | Proof plates, forms, command boxes |
| Dark paper | `#d7c3a2` | Shadows, inset rules, aged-page contrast |
| Ink | `#191816` | Text, borders, final relation, proof marks |
| Euclid blue | `#0e558a` | Principal circle, measured equality, main relation |
| Vermilion red | `#c43c35` | Alternate path, contradiction, comparison |
| Proof ochre | `#e4a412` | Known base, tangent, established construction |

Use colored lines sparingly. If a color appears in a diagram, it should also be useful in labels, keys, or component accents.

## Typography

Primary display and prose:

```css
font-family: "Cormorant Garamond", Georgia, "Times New Roman", serif;
```

Small caps and ornamental initials:

```css
font-family: "IM Fell English SC", "Cormorant Garamond", Georgia, serif;
```

Commands, coordinates, labels, and data:

```css
font-family: "IBM Plex Mono", "Courier New", monospace;
```

### Type Scale

| Role | CSS starting point | Notes |
| ---- | ------------------ | ----- |
| Display | `clamp(3.6rem, 9vw, 8rem)` | Main proposition phrase; high contrast, tight but not cramped |
| Section title | `clamp(2.6rem, 6vw, 5.5rem)` | Secondary proposition statements |
| Heading | `clamp(1.8rem, 3vw, 3rem)` | Component and panel headings |
| Body | `1.25rem` to `1.45rem` | Generous leading, upright roman |
| Caption | `1rem` to `1.1rem` | Italic book captions and marginal notes |
| Mono label | `0.85rem` to `1rem` | Uppercase labels, commands, table headers |

Typographic habits:

- Use large old-style serif type for proof statements.
- Use small caps for running heads, proposition metadata, and folio labels.
- Use italic for proposition labels, captions, and book-like emphasis.
- Use mono for commands, structured data, and mechanical controls.
- Keep letter spacing at `0` for display serif text; use uppercase tracking only for mono or small labels.
- Balance headings manually with line breaks when needed; avoid words colliding with borders or diagrams.

## Composition Patterns

### Proof Page

Use for a hero, feature page, article header, or major app state.

- Top: centered `PROP. X.` label or small caps running head.
- Left or first column: large proposition statement and supporting prose.
- Right or second column: framed proof diagram or tool surface.
- Bottom: concise proof metadata, action row, or result statement.

### Editorial Spread

Use for explaining a system, feature set, or methodology.

- Treat the screen as facing pages.
- Pair a drop-cap text block with a principle list, diagram, or table.
- Use thick vertical rules or page gutters to separate columns.
- Keep the main reading order natural on mobile.

### Archive Or Index

Use for collections, dashboards, and browsing interfaces.

- Left rail: book/category filters with boxed buttons.
- Main region: rows as proposition records.
- Each row can include a mini diagram, prop number, title, and state.
- Use a strong toolbar rule at the top.

### Poster Plate

Use for visual summaries, launch pages, reports, or printable graphics.

- Large framed plate.
- One big theorem statement.
- One diagram with 3 to 6 meaningful primitives.
- Small caps metadata and `Q. E. D.`-style proof marks.

### Form Or Tool

Use for data entry and interactive workflows.

- Inputs are paper fields with thick ink borders.
- Labels use mono or small caps.
- Buttons are boxed, high-contrast, and direct.
- Validation can use red construction marks or an ink proof note.

## Components

### Surfaces

Use rectangular paper surfaces with hard corners. A card is acceptable for a repeated object, but the page itself should feel like a sheet or plate rather than a stack of floating modern cards.

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

Use blue, red, or ochre button fills only when the action meaning matches the color role.

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

Drop caps are framed initials, not oversized decorative letters.

- Use an ink square with one or two paper inner rules.
- Center the glyph optically in the square.
- Keep the letter upright and high-contrast.
- Use them at the start of editorial or theorem prose, not in every section.

### Tables And Lists

Tables should look like ruled proof ledgers:

- Thick top and bottom rules.
- Mono uppercase headers.
- Serif values.
- Strong row dividers.
- Optional mini proof glyphs or swatches in the first column.

### Command Boxes

Command boxes are useful for install snippets or copyable configuration.

- Use a framed paper box.
- Put a short colored rule or dash sample before the command.
- Keep the command text mono.
- Provide a real copy button when the command is meant to be copied.

## Diagram System

Use SVG for most proof diagrams. Keep viewBox dimensions simple and align main points to a loose grid.

### Primitive Roles

| Primitive | Role |
| --------- | ---- |
| Circle / arc | Field of relation, theorem body, measured equality |
| Solid line | Known segment, result, tangent, or named object |
| Square dashed line | Construction, extension, assumed relation, secondary path |
| Filled sector | Angle chip, equivalence, local proof emphasis |
| Heavy border | Page, plate, theorem frame |
| Small caps text | Proposition metadata or proof conclusion |

### SVG Stroke Classes

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

### Square Construction Dashes

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

### Diagram Density

A clear Euclid diagram usually needs:

- One primary circle or arc.
- One base or tangent line.
- Two to four relation lines.
- One or two filled angle chips.
- One concise text block or proof mark.

When a diagram starts to feel busy, remove primitives before adding labels. The diagram should clarify the proposition at a glance.

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

- Below tablet width, stack text, controls, and diagrams in reading order.
- Keep framed plates within the viewport width.
- Use `clamp()` for display sizes and container widths, not viewport-only font scaling.
- Preserve at least `44px` touch targets.
- Let tables scroll horizontally when the data requires it.
- Reduce diagram complexity on small screens rather than shrinking labels to illegibility.

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
- Error: red rule, red proof mark, and a readable text explanation.
- Success: blue or ochre rule plus a concise proof/result note.

## Accessibility

- Maintain high contrast between ink and paper.
- Keep text selectable when possible; avoid rendering real paragraphs as images.
- Add accessible names to SVG proof diagrams.
- Do not rely on color alone; pair color roles with labels, line styles, icons, or spatial position.
- Respect reduced-motion settings if adding drawing animations.
- Keep focus order aligned with the visual reading order.

## Visual QA Checklist

Before finishing, inspect the page in a browser:

- Proposition labels, headings, text blocks, diagrams, and controls are aligned to a visible structure.
- The main figure is readable at a glance and not overloaded with unnecessary primitives.
- Square dashes use the Euclid block rhythm horizontally, vertically, and diagonally.
- Text fits within frames, buttons, tables, and cards at mobile and desktop widths.
- Drop-cap letters are optically centered in their boxes.
- Copy buttons, forms, links, and other interactive elements work.
- The page still feels like a proof sheet after real user content replaces placeholder text.
