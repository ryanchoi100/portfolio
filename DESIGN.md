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
  paper: "#ffffff"
  paper-back: "#f7f4ef"
  paper-back-shade: "#ebe6de"
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
  display:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "clamp(26px, 3vw, 40px)"
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: "-0.01em"
  heading:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "clamp(20px, 2.2vw, 28px)"
    fontWeight: 500
    lineHeight: 1.2
    letterSpacing: "-0.01em"
  body-long:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: 1.7
rounded:
  glass: "9px"
  thumb: "6px"
  paper: "2px"
  media: "18px"
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
    width: "max(80vw, min(calc(100vw - 24px), 560px))"
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

Against the soft brushwork, the interface is a **crisp counterpoint**. There is a single monospace face set small, uppercase labels with wide tracking, hairline edges and exact 9px corners. That precision reads like a designer's annotations on a painting: technical and quiet, never decorative. The only colour the UI adds is lamplight, a glow borrowed from the season on screen: blossom pink in spring, sun gold in summer, ember orange in autumn, frost blue in winter. It appears only when something is touched.

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
- **Lamplight** (`lamplight`): the glow, at 0.6 alpha, whose hue follows the season. Spring is blossom pink `rgb(255, 188, 212)`, summer sun gold `rgb(255, 214, 120)`, autumn ember orange `rgb(255, 160, 96)` and winter frost blue `rgb(168, 206, 255)`. The scene publishes the current hue as `--glow-rgb` on `<html>`, blending between two seasons while the visitor scrolls. The frontmatter value is the fallback before the scene loads. It is used only as a state response: the glow ring on hovered buttons, rows and cards, the Lifted halo, the garden's hover glow, and as text-selection colour (at 0.75 alpha). Never shown at rest.

### Neutral
- **Lake Ink** (`lake-ink`): all text, icons, focus outlines and the tint of every shadow. Cool, deep blue-black from the lake's darkest water.
- **Lake Ink, muted** (`lake-ink-muted`): secondary metadata such as dates and years in list rows. Use it sparingly; most text is full ink.
- **Hairline** (`hairline`): 1px dividers between list rows.
- **Frost** (`frost`): the standard glass fill for the hover label, pop-up panel, close button, glass buttons and section chips.
- **Frost, dense** (`frost-dense`): glass sitting on glass. List rows on hover use it so they separate from the panel beneath.
- **Frost, lit** (`frost-lit`): hovered glass buttons.
- **Frost Edge** (`frost-edge`): the 1px border on every glass surface, which catches light like a pane's edge.
- **Dusk Scrim** (`dusk-scrim`): the ink wash over the scene while a pop-up is open, paired with a 6px blur and 0.9 brightness.
- **Night Water** (`night-water`): the page background seen only before the artwork loads.
- **Paper** (`paper`), **Paper Back** (`paper-back`) and **Paper Back, shaded** (`paper-back-shade`): only for the Resume paper. The page face is white, and the back of the folded sheet is a warm off-white graded into its shade.

Placeholder thumbnail tints (sage, sand, terracotta, rust, slate, dusk at 0.42 alpha) are stand-ins sampled from the seasons. They give way to real imagery and are not system colours.

### Named Rules
**The Painting Leads Rule.** No interface surface is opaque. Glass fills stay at or below 0.8 white so the current season always reads through.

**The Lamplight Rule.** The season glow exists only as a response to hover, press or focus. A surface that glows at rest is a bug.

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
- **Display** (500, 26–40px fluid, 1.1, −0.01em, sentence case): a project title on a case-study page. One per page.
- **Heading** (500, 20–28px fluid, 1.2–1.25, −0.01em, sentence case): the names in the Interfaces list and each case-study section's headline, capped at 22ch.
- **Body long** (400, 15px, 1.6–1.7): case-study paragraphs and the lede, capped at 44ch, short paragraphs with 1.3em between them.

### Named Rules
**The One Face Rule.** Everything is set in IBM Plex Mono. Hierarchy comes from size, case and tracking, never from a second family.

**The Annotation Rule.** Headings, titles and labels are uppercase with 0.06–0.08em tracking. Body copy is sentence case with no tracking. The exception is reading type: Display and Heading (the Interfaces list and case studies) are sentence case with slight negative tracking, because they are read, not scanned. Their kickers and meta labels stay uppercase.

## Layout

The scene is authored on a 1456 × 813 canvas and scaled to cover the viewport (`width: max(100vw, 179.09vh)`, `height: max(55.84vw, 100vh)`, centred). Everything placed in the scene is positioned in percentages of that stage. Narrow screens never shrink the painting: on touch screens where it is wider than the viewport, a sideways swipe pans across it at full size (clamped to its edges), and up/down swipes change the season.

Pop-ups are centred on the scene. The panel is about 80vw wide (capped at 1600px) and 90vh tall, sitting 5vh from the top and bottom of the screen, and fills the screen less 12px gutters on phones. It has fluid padding (`spacing.panel`) and is laid out as a fixed header plus one scrolling body: long pages scroll inside the panel, and the panel never touches the screen's edges. Rhythm inside is 8px within the header, 22px between header and body, 14px gutters in grids and 30px between sections. The Playground is an auto-fill grid of cards at least 200px wide. Text pages use a single column, and About pairs a 180–280px portrait with prose. At 640px and below, two-column blocks stack and fact lists drop to one column.

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

One gently curved corner (`rounded.glass`, 9px) on every glass surface: label, panel, buttons, cards, rows and chips. Image slots inside cards use a slightly tighter 6px (`rounded.thumb`) so they nest inside the card's curve. The Resume paper is nearly square-cornered (`rounded.paper`, 2px), like a real sheet. Playground media tiles are the one softer shape (`rounded.media`, 18px): they are pictures, not glass. Borders are a single 1px frost edge. Dividers are 1px ink hairlines. There are no pills, circles or decorative outlines.

## Components

### Hover Label
*The scene's whisper.* A small frost tag that follows the cursor 22px below it (flipping above near the bottom edge). It names the object under the pointer in uppercase label-small type with a → arrow. It fades in over 0.25s while scaling from 0.94 to 1.

### Pop-up Shell (signature)
*One pane of glass for every page.* Dusk Scrim over the scene, a centred frost panel whose body scrolls inside it, and a 44px frost close button (×) pinned 12px from the panel's top-right. Pages differ only in their content, which is a header (headline plus an intro line) and a body.
- **Open:** panel scales 0.96 → 1 and fades in with the scrim over 300ms on an expo ease-out (`cubic-bezier(0.16, 1, 0.3, 1)`). The panel grows from the scene object that was clicked.
- **Stagger:** content blocks rise 6px and fade over 280ms, starting 60ms in and 35ms apart, capped at 8 steps.
- **Close:** the same scale and fade reversed over 220ms on an in-out curve (`cubic-bezier(0.455, 0.03, 0.515, 0.955)`). Content stays put while the panel leaves.
- **Reduced motion:** no scale, rise or stagger. A 150ms fade only.
- Closes on ×, scrim click or Escape. Focus is trapped inside while open and returns to the trigger on close.

### Resume Paper (signature)
*The one place the page itself leaves the glass.* The tree opens the resume as the actual PDF page, set on white paper with a soft paper shadow and no glass. It is sized to fit the screen with no scrolling: the page height is 90% of the screen, leaving the same 5vh margin above and below as the glass panel, or narrower on small screens. Open PDF and Download glass buttons sit left of the close button, and clicking the page opens the PDF.
- **Unfold:** the page is cut along one vertical fold and two horizontal folds into 2 × 3 panels. A folded packet (paper-back side out) flies out of the tree and grows to full size over 420ms (expo ease-out). The right half swings open about the vertical fold over 520ms, then the top flaps and then the bottom flaps open, 460ms each, all on an in-out cubic curve. Folding faces darken slightly and clear as they open, and the shadow lands last. The whole sequence runs about 1.5s and animates transform and opacity only.
- **Close:** the shell's 220ms fade. **Reduced motion:** no unfold; the flat page fades in.

### Project List (Interfaces)
*Names that travel with their pictures, without end.* The boat's page has no header (its title is screen-reader-only). The list runs from the panel's top edge to its bottom edge, clipped to the glass's rounded corners, with the close button floating over it. Large names (left, Heading type) sit beside a column of 4:5 project images (right, about two thirds of the panel height and at most 42% of its width). The images run edge to edge but fade in and out through a soft mask over the top and bottom 14%, so they appear out of the glass instead of being cut off. The names take only the middle three quarters of the height and fade out at both ends. The image column scrolls, and the names slide with it so the centred image's name sits level with it at full ink, with its meta (disciplines and year, label type) on the same baseline to its right, while the other names drop to 38% ink. Images away from the middle shrink slightly, by up to 7%. The movement is tied directly to the scroll position, so there is no easing to lag behind the finger. The list loops: a copy of the projects sits above and below the originals, and scrolling past either end jumps silently by one set, so it never ends. The copies are hidden from screen readers and the Tab order. Hover or focus lifts a name to full ink. Hovering an image lifts it 3px with the Lifted shadow. Clicking a name or an image opens that project. On phones (720px and below) it becomes one looping column of images, each with its name underneath.

### Case Study (signature)
*The name becomes the page.* A project opens inside the same panel. A frost Back button and the "Interfaces" crumb sit top-left, the close button top-right. Below them the story (left) scrolls past a sticky figure (right) that is exactly the list image's size and position. The story is a kicker, the Display title, a lede, a hairline-topped meta grid (Scope, Client, Year…), then generous sections, each made of a kicker, a Heading headline and two or three short Body long paragraphs. The figure cross-fades (450ms, settling from 1.03 scale) to the image of the section crossing the middle of the scroller. On phones the figure sticks to the top on paper-back so the story scrolls under it.
- **Open:** the clicked name grows into the title, and the image glides into the figure's place, over 560ms on `cubic-bezier(0.32, 0.72, 0, 1)` (FLIP, transform only). The list fades out over 200ms, and the kicker, lede, meta and first section rise 10px and fade in over 380ms, from 220ms, 45ms apart.
- **Back:** Back or Escape scrolls the list to the project, then the title shrinks back into its name (or, if it is scrolled away, the name fades in) and the figure glides back into the list image over 480ms, while the page fades out over 200ms and the rest of the list fades back in. Focus returns to the project's name.
- **Reduced motion:** a 150ms cross-fade between the views; no movement.
- **Images:** every image is a labelled placeholder until real ones arrive. Each project's first figure image is the same picture as its list image, so the morph stays seamless.

### Buttons
- **Shape:** gently curved (9px), 44px tall, 16px side padding.
- **Glass:** frost fill, frost edge, resting shadow, ink label text, with an optional trailing glyph.
- **Hover / Focus:** frost-lit fill plus the lamplight ring (200ms ease). On press it scales to 0.97 over 120ms. Focus shows a 2px ink outline on the edge.

### Playground (signature)
*Work laid on a diagonal, poured like glass.* The garden's page is a looping track of 4:5 media tiles (`rounded.media`, a solid paper-back base, a deep soft shadow) running from top-left to bottom-right. The centred tile is upright and about 60% of the panel's height. Each step away moves it a third of the panel along the diagonal, tilts it 9° (counter-clockwise up the track, clockwise down it), shrinks it to 58% and fades it. The track is masked so tiles appear out of the panel's edges. The panel's bottom-left holds the "Playground" kicker, the centred tile's title (Heading) and its kind, placeholder status and count (label).
- **Scroll:** the wheel (either axis), a drag along the diagonal, or the arrow keys move the track. It eases toward the input and settles on the nearest tile once input stops, frame-rate independent. The track loops endlessly.
- **Hover (fluid glass, the only liquid effect):** the tile grows 2%, a season-coloured rim light and a soft highlight follow the pointer, and the `#pg-liquid` SVG filter ripples only the tile's edge band (noise displaced through a rim mask), eased in over about 300ms and out on leave. It applies to pointer devices only and is off under reduced motion.
- **Open** (matched frame by frame to the owner's reference recording): clicking the centred tile (or Enter on it) opens it across the whole pop-up panel (not the screen; the panel clips it to its rounded corners). Clicking another tile brings it to the centre first. The tile is picked up by its right side. Its right and bottom edges sweep out first (540ms, `cubic-bezier(0.45, 0, 0.2, 1)`), while its left and top edges hold back and catch up at the end (540ms from 60ms, `cubic-bezier(0.7, 0, 0.3, 1)`). Over the 600ms it leans slightly anticlockwise (−4° at the halfway point) with its right side turned toward the viewer (`perspective(1000px) rotateY(-8deg)`). It keeps its 18px corners until 80% of the way, then squares off. The edges stay clean, with no ripple. The frost Back button and caption fade up just after it lands.
- **Close:** Back or Escape fades the caption and Back button (150ms), then reverses the move over 600ms on in-out cubic. The tile shrinks back to its place on the track, its right and bottom edges slightly ahead, leaning a little clockwise (4°) with its right side turned away (rotateY 8°), and its corners round off early. Focus returns to the tile.
- **Reduced motion:** the full view fades in and out over 200ms.
- **Media:** every tile is a labelled placeholder until the owner adds logo files or logo animations (an `<img>` or `<video>` inside the tile's media), and the full view reuses the same media.

### Cards / Containers
- **Corner Style:** 9px; the image slot inside is 6px.
- **Background:** frost-dense (glass on glass).
- **Shadow Strategy:** resting at rest, Lifted on hover.
- **Internal Padding:** 10px.

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
- **Do** keep the painting at full size on narrow screens and let touch users pan sideways across it, rather than shrinking it.

### Don't:
- **Don't** put an opaque surface over the scene, or push a glass fill above 0.8 white.
- **Don't** introduce a second typeface or a heavier weight than 500 (600 only on the existing hover label).
- **Don't** let anything glow at rest.
- **Don't** animate `backdrop-filter`, layout properties or the blur amount; and no bounce or linear easing on UI.
- **Don't** alter the season scroll, the artwork or the tuned scene positions and timings to fit an interface element.
