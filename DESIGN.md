---
name: Seasons Portfolio
description: A product designer's portfolio entered through a painted lake that turns through the four seasons.
colors:
  lake-ink: "#141c24"
  lake-ink-muted: "rgba(20, 28, 38, 0.72)"
  hairline: "rgba(20, 28, 38, 0.10)"
  frost: "rgba(255, 255, 255, 0.62)"
  frost-dense: "rgba(255, 255, 255, 0.74)"
  frost-lit: "rgba(255, 255, 255, 0.8)"
  frost-edge: "rgba(255, 255, 255, 0.6)"
  dusk-scrim: "rgba(20, 28, 38, 0.16)"
  lamplight: "rgba(255, 222, 156, 0.6)"
  night-water: "#1d2630"
typography:
  headline:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "22px"
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: "0.08em"
  title:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "12px"
    fontWeight: 500
    lineHeight: 1.45
    letterSpacing: "0.06em"
  body:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "13px"
    fontWeight: 400
    lineHeight: 1.5
  body-small:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "12px"
    fontWeight: 400
    lineHeight: 1.45
  label:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "11px"
    fontWeight: 500
    lineHeight: 1
    letterSpacing: "0.08em"
  label-small:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "10px"
    fontWeight: 600
    lineHeight: 1
    letterSpacing: "0.08em"
rounded:
  glass: "9px"
  thumb: "6px"
spacing:
  xs: "4px"
  sm: "8px"
  md: "14px"
  lg: "22px"
  xl: "30px"
  panel: "clamp(18px, 3vw, 36px)"
components:
  hover-label:
    backgroundColor: "{colors.frost}"
    textColor: "{colors.lake-ink}"
    typography: "{typography.label-small}"
    rounded: "{rounded.glass}"
    padding: "5px 10px"
  popup-panel:
    backgroundColor: "{colors.frost}"
    textColor: "{colors.lake-ink}"
    rounded: "{rounded.glass}"
    padding: "{spacing.panel}"
    width: "max(76vw, min(calc(100vw - 24px), 560px))"
  popup-close:
    backgroundColor: "{colors.frost}"
    textColor: "{colors.lake-ink}"
    rounded: "{rounded.glass}"
    size: "44px"
  popup-close-hover:
    backgroundColor: "{colors.frost-lit}"
  button-glass:
    backgroundColor: "{colors.frost}"
    textColor: "{colors.lake-ink}"
    typography: "{typography.label}"
    rounded: "{rounded.glass}"
    padding: "0 16px"
    height: "44px"
  button-glass-hover:
    backgroundColor: "{colors.frost-lit}"
  card-glass:
    backgroundColor: "{colors.frost-dense}"
    textColor: "{colors.lake-ink}"
    rounded: "{rounded.glass}"
    padding: "10px"
  list-row:
    textColor: "{colors.lake-ink}"
    rounded: "{rounded.glass}"
    padding: "12px 10px"
  list-row-link-hover:
    backgroundColor: "{colors.frost-dense}"
  section-chip:
    backgroundColor: "{colors.frost}"
    textColor: "{colors.lake-ink}"
    typography: "{typography.label}"
    rounded: "{rounded.glass}"
    padding: "0 12px"
    height: "32px"
---

# Design System: Seasons Portfolio

## Overview

**Creative North Star: "The Painted Season"**

The artwork is the system. A painted lake (house, tree, boat, garden, water) fills the viewport and turns Spring → Summer → Autumn → Winter as the visitor scrolls. Every piece of interface is a seasonal guest in that painting. It arrives when called, sits on frosted glass so the season stays visible through it, and leaves without a trace. Nothing in the UI is opaque, and nothing competes with the paint for colour.

Against the soft brushwork, the interface is a **crisp counterpoint**. There is a single monospace face set small, uppercase labels with wide tracking, hairline edges and exact 9px corners. That precision reads like a designer's annotations on a painting: technical and quiet, never decorative. The only warmth the UI adds is lamplight, a pale gold glow borrowed from the house's lit windows. It appears only when something is touched.

Density is low. Glass panels float above the scene on soft ambient shadows, and the scene behind them is blurred and dimmed just enough to read over. Motion follows the same rule: arrivals decelerate confidently, exits are quick and calm, and only transform and opacity move.

**Key Characteristics:**
- Translucent frosted glass for every surface; the season always shows through.
- One typeface (IBM Plex Mono); hierarchy from size, uppercase tracking and two weights.
- Ink-on-frost colour; the warm lamplight glow is the only accent, and it only answers interaction.
- Floating depth: soft ambient shadow at rest, lift and glow on hover.
- Calm, exact motion: expo ease-out arrivals, short in-out exits, no bounce.

## Colors

A near-monochrome system of cool ink on white frost, warmed only by lamplight; all hue comes from the painting behind it.

### Primary
- **Lamplight** (`lamplight`): the warm gold glow from the house windows. It is used only as a state response: the glow ring on hovered buttons, rows and cards, and as text-selection colour (at 0.75 alpha). Never shown at rest.

### Neutral
- **Lake Ink** (`lake-ink`): all text, icons, focus outlines and the tint of every shadow. Cool, deep blue-black from the lake's darkest water.
- **Lake Ink, muted** (`lake-ink-muted`): secondary metadata such as dates and years in list rows. Use it sparingly; most text is full ink.
- **Hairline** (`hairline`): 1px dividers between list rows.
- **Frost** (`frost`): the standard glass fill for the hover label, pop-up panel, close button, glass buttons and section chips.
- **Frost, dense** (`frost-dense`): glass sitting on glass. Playground cards, and list rows on hover, use it so they separate from the panel beneath.
- **Frost, lit** (`frost-lit`): hovered glass buttons.
- **Frost Edge** (`frost-edge`): the 1px border on every glass surface, which catches light like a pane's edge.
- **Dusk Scrim** (`dusk-scrim`): the ink wash over the scene while a pop-up is open, paired with a 6px blur and 0.9 brightness.
- **Night Water** (`night-water`): the page background seen only before the artwork loads.

Placeholder thumbnail tints (sage, sand, terracotta, rust, slate, dusk at 0.42 alpha) are stand-ins sampled from the seasons. They give way to real imagery and are not system colours.

### Named Rules
**The Painting Leads Rule.** No interface surface is opaque. Glass fills stay at or below 0.8 white so the current season always reads through.

**The Lamplight Rule.** The warm glow exists only as a response to hover, press or focus. A surface that glows at rest is a bug.

## Typography

**Display Font:** none (no display face; the painting is the display).
**Body Font:** IBM Plex Mono (with ui-monospace, monospace).
**Label/Mono Font:** the same face.

**Character:** One technical monospace, used small and exact, as a deliberate counterpoint to the painterly scene: annotation, not decoration. Only weights 400 and 500 are loaded; the 600 on the hover label is browser-synthesised.

### Hierarchy
- **Headline** (500, 22px, 1.1, 0.08em, uppercase): the pop-up title. One per pop-up.
- **Title** (500, 12px, 1.45, 0.06em, uppercase): section headings inside a pop-up, card titles and list-row titles.
- **Body** (400, 13px, 1.5–1.6): the pop-up intro line and prose paragraphs, capped at 56–62ch.
- **Body small** (400, 12px, 1.45–1.5): card captions, list-row descriptions and fact lists, capped at 70ch. Dates use tabular numerals.
- **Label** (500, 11px, 0.08em, uppercase): glass buttons and section chips.
- **Label small** (600, 10px, 0.08em, uppercase): the cursor-following hover label, and placeholder image labels.

### Named Rules
**The One Face Rule.** Everything is set in IBM Plex Mono. Hierarchy comes from size, case and tracking, never from a second family.

**The Annotation Rule.** Headings, titles and labels are uppercase with 0.06–0.08em tracking. Body copy is sentence case with no tracking.

## Layout

The scene is authored on a 1456 × 813 canvas and scaled to cover the viewport (`width: max(100vw, 179.09vh)`, `height: max(55.84vw, 100vh)`, centred). Everything placed in the scene is positioned in percentages of that stage. Narrow screens therefore crop the sides of the painting rather than letting it shrink.

Pop-ups are sheets. The panel is horizontally centred, about 76vw wide (capped at 1240px; the full width less 12px gutters on phones), with fluid padding (`spacing.panel`). It opens with its top where a 70vh panel's top would sit and is at least one page tall, so its bottom always runs to the bottom edge of the page. The whole sheet, header included, scrolls inside the scrim: it can always travel up until it fills the page edge to edge, and longer pages keep going until their bottom meets the bottom of the page. Rhythm inside is 8px within the header, 22px between header and body, 14px gutters in grids and 30px between sections. The Playground is an auto-fill grid of cards at least 200px wide. Text pages use a single column, and About pairs a 180–280px portrait with prose. At 640px and below, two-column blocks stack and fact lists drop to one column.

## Elevation & Depth

Depth is floating glass. Surfaces hover just above the painting on one soft, cool ambient shadow with a 1px inner top highlight, as if light catches the top edge of a pane. Glass on glass separates by density (`frost-dense`), not by a heavier shadow. Interaction lifts and warms. Hovered cards rise 3px with a deeper shadow and lamplight halo; hovered buttons and linked rows gain the lamplight ring in place.

### Shadow Vocabulary
- **Resting glass** (`box-shadow: 0 4px 14px rgba(20,28,38,0.10), inset 0 1px 0 rgba(255,255,255,0.35)`): every glass surface at rest.
- **Lamplit** (`box-shadow: 0 4px 14px rgba(20,28,38,0.10), 0 0 14px rgba(255,222,156,0.6), inset 0 1px 0 rgba(255,255,255,0.35)`): hovered buttons, close button and linked rows.
- **Lifted** (`box-shadow: 0 10px 24px rgba(20,28,38,0.14), 0 0 18px rgba(255,222,156,0.55), inset 0 1px 0 rgba(255,255,255,0.35)`): hovered cards.

### Named Rules
**The Frost Rule.** Glass is `backdrop-filter: blur(10px) saturate(1.4)`, always the same values. The blur is never animated.

**The Glow-On-Touch Rule.** Elevation changes only in response to the pointer or focus. At rest, everything sits at the same resting depth.

## Shapes

One gently curved corner (`rounded.glass`, 9px) on every glass surface: label, panel, buttons, cards, rows and chips. The one exception is the pop-up sheet's bottom edge, which runs off the bottom of the page, so its bottom corners are square and it has no bottom border. Image slots inside cards use a slightly tighter 6px (`rounded.thumb`) so they nest inside the card's curve. Borders are a single 1px frost edge. Dividers are 1px ink hairlines. There are no pills, circles or decorative outlines.

## Components

### Hover Label
*The scene's whisper.* A small frost tag that follows the cursor 22px below it (flipping above near the bottom edge). It names the object under the pointer in uppercase label-small type with a → arrow. It fades in over 0.25s while scaling from 0.94 to 1.

### Pop-up Shell (signature)
*One pane of glass for every page.* Dusk Scrim over the scene, a frost sheet that runs to the bottom of the page and scrolls as one piece, and a 44px frost close button (×) 12px from the sheet's top-right. Once the sheet scrolls past, the close button stays pinned 12px below the top of the page. Every page opens scrolled to its top. Pages differ only in their content, which is a header (headline plus an intro line) and a body.
- **Open:** panel scales 0.96 → 1 and fades in with the scrim over 300ms on an expo ease-out (`cubic-bezier(0.16, 1, 0.3, 1)`). The panel grows from the scene object that was clicked.
- **Stagger:** content blocks rise 6px and fade over 280ms, starting 60ms in and 35ms apart, capped at 8 steps.
- **Close:** the same scale and fade reversed over 220ms on an in-out curve (`cubic-bezier(0.455, 0.03, 0.515, 0.955)`). Content stays put while the panel leaves.
- **Reduced motion:** no scale, rise or stagger. A 150ms fade only.
- Closes on ×, scrim click or Escape. Focus is trapped inside while open and returns to the trigger on close.

### Buttons
- **Shape:** gently curved (9px), 44px tall, 16px side padding.
- **Glass:** frost fill, frost edge, resting shadow, ink label text, with an optional trailing glyph.
- **Hover / Focus:** frost-lit fill plus the lamplight ring (200ms ease). On press it scales to 0.97 over 120ms. Focus shows a 2px ink outline on the edge.

### Cards / Containers
- **Corner Style:** 9px; the image slot inside is 6px.
- **Background:** frost-dense (glass on glass).
- **Shadow Strategy:** resting at rest, Lifted on hover. The inner surface rises 3px while the outer hit area stays still, so the pointer never loses it.
- **Internal Padding:** 10px, with a 10px gap between image and text.

### List Rows
- **Rest:** no fill. Title and right-aligned date on one line, description below, separated by ink hairlines.
- **Linked rows:** hover adds a frost-dense surface, frost edge and lamplight ring, and the trailing → nudges 3px right. Static rows get only a faint frost tint.

### Navigation
- **Scene objects** are the primary navigation: house, tree, boat (the snowman in winter) and garden.
- **Section chips:** a row of frost chips top-left (label type, 32px tall). They are invisible until a keyboard user tabs into them, and stay visible under the scrim while their pop-up is open.

## Do's and Don'ts

### Do:
- **Do** build every new surface from the shared glass tokens (`frost`, `frost-edge`, resting shadow, 9px), never with restated values.
- **Do** keep text in Lake Ink on frost and let the season supply all colour.
- **Do** reserve Lamplight for hover, press and focus responses.
- **Do** animate only transform and opacity: 300ms expo ease-out in, 220ms in-out out, 150ms fade under reduced motion.
- **Do** keep hover effects behind `(hover: hover) and (pointer: fine)`, and keep touch targets at least 44px.
- **Do** let narrow screens crop the painting rather than shrinking it.

### Don't:
- **Don't** put an opaque surface over the scene, or push a glass fill above 0.8 white.
- **Don't** introduce a second typeface or a heavier weight than 500 (600 only on the existing hover label).
- **Don't** let anything glow at rest.
- **Don't** animate `backdrop-filter`, layout properties or the blur amount; and no bounce or linear easing on UI.
- **Don't** alter the season scroll, the artwork or the tuned scene positions and timings to fit an interface element.
