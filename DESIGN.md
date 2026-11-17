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
  lamplight: "rgba(255, 255, 255, 0.6)"
  night-water: "#1d2630"
  paper: "#ffffff"
  paper-back: "#f7f4ef"
  paper-back-shade: "#ebe6de"
typography:
  headline:
    fontFamily: "Source Serif 4, Georgia, serif"
    fontSize: "30px"
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: "-0.01em"
  title:
    fontFamily: "Source Sans 3, system-ui, sans-serif"
    fontSize: "13px"
    fontWeight: 500
    lineHeight: 1.45
    letterSpacing: "0.06em"
  body:
    fontFamily: "Source Sans 3, system-ui, sans-serif"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: 1.5
  body-small:
    fontFamily: "Source Sans 3, system-ui, sans-serif"
    fontSize: "13px"
    fontWeight: 400
    lineHeight: 1.45
  label:
    fontFamily: "Source Sans 3, system-ui, sans-serif"
    fontSize: "11px"
    fontWeight: 500
    lineHeight: 1
    letterSpacing: "0.08em"
  label-small:
    fontFamily: "Source Sans 3, system-ui, sans-serif"
    fontSize: "11px"
    fontWeight: 600
    lineHeight: 1
    letterSpacing: "0.08em"
  display:
    fontFamily: "Source Serif 4, Georgia, serif"
    fontSize: "clamp(26px, 3vw, 40px)"
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: "-0.01em"
  heading:
    fontFamily: "Source Serif 4, Georgia, serif"
    fontSize: "clamp(20px, 2.2vw, 28px)"
    fontWeight: 500
    lineHeight: 1.2
    letterSpacing: "-0.01em"
  body-long:
    fontFamily: "Source Sans 3, system-ui, sans-serif"
    fontSize: "17px"
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

Against the soft brushwork, the interface is a **crisp counterpoint**. Two faces from the resume's family: a humanist sans for everything you read and click, and its companion serif for titles, plus small uppercase labels with wide tracking, hairline edges and exact 9px corners. That precision reads like a designer's annotations on a painting: quiet, never decorative. The only light the UI adds is lamplight, a white glow like light caught in liquid glass, the same in every season. It appears only when something is touched.

Density is low. Glass panels float above the scene on soft ambient shadows, and the scene behind them is blurred and dimmed just enough to read over. Motion follows the same rule: arrivals decelerate confidently, exits are quick and calm, and only transform and opacity move.

**Key Characteristics:**
- Translucent frosted glass for every surface; the season always shows through.
- Two typefaces (Source Sans 3 and Source Serif 4); the serif only for titles and headlines.
- Ink-on-frost colour; the white lamplight glow is the only accent, and it only answers interaction.
- Floating depth: soft ambient shadow at rest, lift and glow on hover.
- Calm, exact motion: expo ease-out arrivals, short in-out exits, no bounce.

## Colors

A near-monochrome system of cool ink on white frost, lit only by a white lamplight glow; all hue comes from the painting behind it.

### Primary
- **Lamplight** (`lamplight`): a white glow (`rgba(255, 255, 255, 0.6)`, exposed as `--glow-rgb: 255, 255, 255`) that reads like light caught in liquid glass. It is the same in every season. It is used only as a state response: the glow ring on hovered buttons, rows and cards, the Lifted halo, the Playground tile's rim light and the garden's hover glow. Never shown at rest. Text selection does not use it (white would vanish on the frost); selection is a 16% ink tint, `rgba(20, 28, 38, 0.16)`.

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

**The Lamplight Rule.** The white glow exists only as a response to hover, press or focus. A surface that glows at rest is a bug.

## Typography

**Display Font:** Source Serif 4 (with Georgia, serif): pop-up headlines, the Interfaces names, case-study titles and headlines, and Playground titles.
**Body Font:** Source Sans 3 (with system-ui, sans-serif): everything else, including body copy, labels, buttons and meta.
**Label Font:** the same sans, set uppercase and tracked.

**Character:** The resume is set in Myriad, which needs an Adobe Fonts licence to embed on the web. Source Sans 3 is Adobe's open-source humanist sans in the same spirit, so the site reads like the resume. Source Serif 4, its companion, gives titles a calm editorial voice against the painting. Sans weights 400, 500 and 600 and serif weights 400, 500 and 600 are loaded from Google Fonts. To use Myriad itself, swap `--font-sans` for an Adobe Fonts kit.

### Hierarchy
- **Headline** (serif 500, 30px, 1.1, −0.01em, sentence case): the pop-up title. One per pop-up.
- **Title** (sans 500, 13px, 1.45, 0.06em, uppercase): section headings inside a pop-up and list-row titles.
- **Body** (sans 400, 15px, 1.5–1.6): the pop-up intro line and prose paragraphs, capped at 56–62ch.
- **Body small** (sans 400, 13px, 1.45–1.5): list-row descriptions, fact lists and the case-study meta, capped at 70ch. Dates use tabular numerals.
- **Label** (sans 500, 11px, 0.08em, uppercase): glass buttons, section chips, kickers and meta lines.
- **Label small** (sans 600, 11px, 0.08em, uppercase): the cursor-following hover label.
- **Display** (serif 500, 26–40px fluid, 1.1, −0.01em, sentence case): a project title on a case-study page. One per page.
- **Heading** (serif 500, 20–28px fluid, 1.2–1.25, −0.01em, sentence case): the names in the Interfaces list, each case-study section's headline, and Playground titles. Capped at 22ch.
- **Body long** (sans 400, 17px, 1.6–1.7): case-study paragraphs and the lede, capped at 44ch, short paragraphs with 1.3em between them.

### Named Rules
**The Two Faces Rule.** Source Serif 4 is only for titles and headlines (Headline, Display, Heading). Everything else is Source Sans 3. No third family.

**The Annotation Rule.** Sans titles and labels are uppercase with 0.06–0.08em tracking. Body copy is sentence case with no tracking. The exception is reading type: Display and Heading (the Interfaces list and case studies) are sentence case with slight negative tracking, because they are read, not scanned. Their kickers and meta labels stay uppercase.

## Layout

The scene is authored on a 1456 × 813 canvas and scaled to cover the viewport (`width: max(100vw, 179.09vh)`, `height: max(55.84vw, 100vh)`, centred). Everything placed in the scene is positioned in percentages of that stage. Narrow screens never shrink the painting: on touch screens where it is wider than the viewport, a sideways swipe pans across it at full size (clamped to its edges), and up/down swipes change the season.

Pop-ups are centred on the scene. The panel is about 80vw wide (capped at 1600px) and 90vh tall, sitting 5vh from the top and bottom of the screen, and fills the screen less 12px gutters on phones. It has fluid padding (`spacing.panel`) and is laid out as a fixed header plus one scrolling body: long pages scroll inside the panel, and the panel never touches the screen's edges. Rhythm inside is 8px within the header, 22px between header and body, 14px gutters in grids and 30px between sections. The Playground is an auto-fill grid of cards at least 200px wide. Text pages use a single column, and About pairs a 180–280px portrait with prose. At 640px and below, two-column blocks stack and fact lists drop to one column.

## Elevation & Depth

Depth is floating glass. Surfaces hover just above the painting on one soft, cool ambient shadow with a 1px inner top highlight, as if light catches the top edge of a pane. Glass on glass separates by density (`frost-dense`), not by a heavier shadow. Interaction lifts and lights up. Hovered cards rise 3px with a deeper shadow and lamplight halo; hovered buttons and linked rows gain the lamplight ring in place.

### Shadow Vocabulary
- **Resting glass** (`box-shadow: 0 4px 14px rgba(20,28,38,0.10), inset 0 1px 0 rgba(255,255,255,0.35)`): every glass surface at rest.
- **Lamplit** (`box-shadow: 0 4px 14px rgba(20,28,38,0.10), 0 0 14px rgba(255,255,255,0.6), inset 0 1px 0 rgba(255,255,255,0.35)`): hovered buttons, close button and linked rows.
- **Lifted** (`box-shadow: 0 10px 24px rgba(20,28,38,0.14), 0 0 18px rgba(255,255,255,0.55), inset 0 1px 0 rgba(255,255,255,0.35)`): hovered cards.

### Named Rules
**The Frost Rule.** Glass is `backdrop-filter: blur(10px) saturate(1.4)`, always the same values. The blur is never animated.

**The Glow-On-Touch Rule.** Elevation changes only in response to the pointer or focus. At rest, everything sits at the same resting depth.

## Shapes

One gently curved corner (`rounded.glass`, 9px) on every glass surface: label, panel, buttons, cards, rows and chips. Image slots inside cards use a slightly tighter 6px (`rounded.thumb`) so they nest inside the card's curve. The Resume paper is nearly square-cornered (`rounded.paper`, 2px), like a real sheet. Playground tiles are the one softer shape: corners at 20% of the tile (about 30px), and 28px on the focused landscape card (`rounded.media` is the 18px base). They are pictures, not glass. Borders are a single 1px frost edge. Dividers are 1px ink hairlines. There are no pills, circles or decorative outlines.

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
*An assembly of work, floating in depth.* Modelled on the owner's reference recordings and stills. The garden's page holds a tight cluster of 8 rounded-square logo tiles (3, 2 and 3 in three lanes) (corners at 20% of the tile, a soft drop shadow), about 2.7 tiles wide and 2.4 tall, overlapping closely in the middle of the panel with generous empty space around it. Every tile is fully visible: no fading or dimming; tiles that loop past the panel's edge are simply cut off by it. The six logos fill the eight tiles (two repeat). A frost chip in the bottom-left reads "Playground · Logos & motion".
- **Depth:** every tile has its own depth that drifts very slowly, so the layering shifts over time and nothing moves in lockstep. Nearer tiles are larger (72–112%) and sit on top. Each tile also has a barely-there bob and a hair of tilt, and the cluster curves away in perspective toward its edges (up to 10° on the sides, 6° top and bottom).
- **Idle:** almost still. The tiles sway a few pixels and bob 1–3px, slowly.
- **Scroll (endless loop):** the wheel (either axis) or a drag slides the lanes in a continuous loop, as in the owner's recording: odd lanes to the right and even lanes to the left, eased in. Tiles pass over and under the tiles of the other lanes. A tile that leaves one edge of the panel comes back in at the other, so scrolling never runs out. Nearer tiles move slightly further (parallax), so the order within a lane slowly reshuffles. When input stops, the lanes stay where they are.
- **Open a tile:** the other tiles scatter outward around the landscape card and its caption and shrink to 84%, both easing in gently (about two seconds to settle, never abrupt). While a card is open the whole field floats with the mouse, smoothed slowly: nearer tiles move up to about 44px and tilt a few degrees toward the pointer.
- **Hover (fluid glass, the only liquid effect):** the tile rises over its neighbours. It scales to 1.08 with the Lifted shadow, a white rim light follows the pointer, and the `#pg-liquid` filter ripples its edge. Pointer devices only; off under reduced motion.
- **Focus (click a tile):** the tile flies from where it is to the centre and opens out into a landscape 3:2 card (about half the panel's width, 28px corners, a deep shadow) over 760ms on the expo ease-out. The field scatters around it (see Open a tile). The panel takes on a soft wash of the tile's colour. Below the card a centred caption rises in (from 260ms, 60ms apart): the kind and placeholder status (label, 0.16em tracking), the title (serif, 28–44px) and a short descriptor.
- **Swap / release:** clicking another tile flies the new one in while the old card shrinks back into its tile, which is still moving with its row (620ms, in-out cubic). Escape, or a click on empty space, releases the card and lets the field close back in.
- **Keyboard:** the field takes focus (outlined chip). Arrow keys step through the six logos, focusing the nearest copy of each, and Escape releases.
- **Reduced motion:** no idle sway, bob or depth drift; the card and caption fade in place.
- **Media:** every tile is a labelled placeholder until the owner adds logo files or logo animations (an `<img>` or `<video>` inside an entry in `[data-pg-src]`). The tiles and the focused card reuse the same media.

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
