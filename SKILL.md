---
name: euclid-design-skill
description: Build and refine Euclid-inspired user interfaces, design systems, landing pages, components, and visual assets based on old geometry book pages, colored proof diagrams, thick ruled borders, ornamental initials, and square dashed construction lines. Use when the user asks for Euclid, geometric proof, old mathematical book, proposition-page, thick color line, or chunky dashed-line design work.
---

# Euclid Design Skill

## Overview

Use this skill to create clean interfaces inspired by Euclid edition pages: book-paper layouts, proposition headings, old-style typography, colored proof marks, and geometric diagrams. Prefer clarity and restraint over literal reproduction of reference photos.

For a full static-site starting point, copy `assets/static-site/` into the target project and adapt it. For detailed visual rules, read `references/visual-system.md`.

## Workflow

1. Establish the page as a proposition sheet: a ruled paper surface, centered italic `PROP. X.` heading, a strong typographic statement, and one clean diagram or component surface.
2. Use color as notation: blue for principal arcs and measured equality, red for alternate or contradictory construction, ochre for known bases/tangents, and ink black for final relation and text.
3. Build diagrams with a small number of readable geometric primitives. Avoid busy overlap, loose decorative fragments, and fake text that looks accidental.
4. Use the square dashed-line system for every construction dash, horizontal or vertical.
5. Verify visually in a browser at desktop and mobile sizes before finishing. Fix text overflow, partial dash endings, cramped initials, and incoherent overlaps.

## Non-Negotiables

- Do not reference inspiration sites or source URLs in the rendered UI unless the user explicitly asks.
- Do not use generic gradient-orb, SaaS-card, or modern landing-page styling.
- Do not slant body or marginal text unless it is a caption or explicit book-style italic.
- Do not end dashed lines with partial dash segments.
- Do not leave unlabeled sections with empty left columns.

## Core Tokens

Use these defaults unless the target project already defines equivalent tokens:

```css
--paper: #efe2c9;
--paper-light: #f8efd9;
--paper-dark: #d7c3a2;
--ink: #191816;
--blue: #0e558a;
--red: #c43c35;
--gold: #e4a412;
--dash-block: 10px;
--dash-gap: 5px;
--rule: 4px;
```

Typography:

- Display/prose: `Cormorant Garamond`, Georgia, serif.
- Small caps/drop caps: `IM Fell English SC`, serif.
- Commands/data: `IBM Plex Mono`, monospace.

## Dashed Lines

Use square construction segments everywhere:

```css
.dash {
  fill: none;
  stroke-dasharray: 10 5;
  stroke-linecap: butt;
  stroke-width: 10;
}
```

For SVG paths, set `pathLength` to values that end on a full dash. With `10 5`, good path lengths are `10`, `25`, `40`, `55`, `70`, `85`, `100`, `115`, `130`, `145`, `160`, `175`, `190`, `205`, `220`, etc.

For CSS inline dashes, use a repeating linear gradient with `--dash-block` and `--dash-gap`, and size the element so the final segment is complete.

## Drop Caps

Drop caps should feel like book initials: centered, framed, and stable.

- Use an ink square with a paper inner rule or double border.
- Center the glyph optically, not only mathematically; inspect it in the browser.
- Keep the letter upright and high-contrast.
- Avoid oversized initials that touch the frame.

## Visual QA

After implementation, use browser screenshots to check:

- No text overlaps with borders, diagrams, or adjacent columns.
- All command boxes and buttons fit at desktop and mobile widths.
- Diagram text is upright and legible.
- Dashed lines have square chunks and no partial final chunks.
- The first viewport shows the actual product/design system, not a marketing placeholder.
