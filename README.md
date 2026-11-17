# Handoff: Seasons Endless-Scroll Scene

## What this is
A full-viewport painterly landscape (lake, house, tree, boat, garden) that cycles endlessly Spring → Summer → Autumn → Winter as the visitor scrolls. Scene objects are the site navigation: hovering one reveals an animated figure plus a frosted-glass label; the garden opens a Playground pop-up.

**Fidelity: high.** Every number in the code (positions, timings, easings, colours) is tuned — port it, don't "clean it up".

## Files
- `index.html` — **single source of truth.** Standalone, dependency-free vanilla JS. Serve over HTTP (`npx serve .`); canvases read image pixels so `file://` fails with CORS.
- `seasons/` — image assets (per season: `-plate.jpg`, `-tree.png`, `-refl.png`, `-lights.png`).
- `source/Seasons.dc.html` + `support.js` — the same design in the prototype's component format (reference only; identical logic).

All logic lives in `class SeasonsScene` in `index.html`, split into commented sections (search for `// ====`). To port into React/Vue/etc.: render the same markup, set `rootRef.current` to the root element, call `componentDidMount()` on mount and `componentWillUnmount()` on unmount.

## Feature inventory (current state)
| Object | Hitbox (scene units) | Seasons | Hover | Label | Click |
|---|---|---|---|---|---|
| House | 662,362→785,502 + 785,380→828,502 | all | window lights fade in | ABOUT ME | TODO |
| Tree | 785,285→1010,505 | all | reader fades in; leaves / snow fall | RESUME | TODO |
| Boat | 360,508→495,550 | not winter | fisher fades in; ripples | EXPERIENCE | TODO |
| Snowman | 398,468→460,548 | winter | kneeler fixes scarf | EXPERIENCE | TODO |
| Garden | 590,474→634,506 | all | warm glow; gardener fades in | PLAYGROUND | opens Playground pop-up |

Hitboxes don't overlap (boat and snowman share a spot but are never active in the same season). First match in `hits` wins.

**Not built:** the brief mentioned a tree-of-experience overlay, a boat Experience list overlay, a mailbox, and fireflies. None exist — fireflies were built and then removed in favour of the garden; the others were never built. Only the Playground pop-up exists.

## Coordinate system
- Artwork authored on **1456 × 813**. The `.stage` box covers the viewport: `width: max(100vw, 179.09vh); height: max(55.84vw, 100vh)`, centred.
- Overlays are positioned in % of the stage; JS works in scene units: `X = (mx − stage.left) / stage.width × 1456`.

## Season scroll
- `pos` / `target` are unbounded floats (integer = season). Wheel: `target += delta × scrollSpeed / 900`. Touch swipe: ×2.2 (up/down; any direction when the whole painting fits the screen). Arrows / Page / Space: ±1 season. **No mouse drag.**
- Touch pan: where the painting is wider than the screen (phones), a sideways swipe pans it at full size via `--pan-x` on the stages, clamped to ±(stage width − screen width)/2, with a short glide. Each gesture locks to one axis after 6px; a swipe never counts as a tap.
- Snap after 180 ms idle: `target += (round − target) × 0.12`/frame. Smoothing: `pos += (target − pos) × 0.09`.
- Wipe: `d = (i − pos)` wrapped to (−2, 2]. 0<d<1 → incoming slide, `clip-path: inset(0 0 0 d·100%)`, z 2. −1<d≤0 → outgoing, z 1.
- Defaults: `snap = true`, `scrollSpeed = 3`, `swayAmount = 1.5`.

## Ambient animation
- Wind `A·(0.7 sin(1.15t+i) + 0.3 sin(2.9t+2.1i))`° drives the tree (pivot at roots), reflection (inverse) and boat (×1.5, plus bob).
- Winter chimney smoke: S-curve puffs, 13–16 s life, reflected at 40 %.

## Figures
Procedurally painted with soft brush strokes (`paintFig`). Mid-brown skin `rgb(178,124,88)`, three-quarter view, seasonal outfits in `outfit`. All fade 0.7 s in / 1.2 s out (smoothstep).
- Fisher (boat), Reader (tree), Kneeler (snowman), Gardener (garden): spring waters tulips, summer picks flowers into a basket, autumn carries a pumpkin, winter pats the snow mound.

## Garden patch
Painted once per season into a canvas (`paintGarden`) — same footprint in all four: spring tulip cluster, summer fern clump with blooms, autumn pumpkin pile, winter snow dome. Hover adds a warm `drop-shadow` glow.

## Hover label
Follows the cursor, centred 22 px below, flips above near the bottom, clamped 6 px from edges, eased 0.35/frame.
Glass tokens (reused by the pop-up): bg `rgba(255,255,255,0.62)`, `backdrop-filter: blur(10px) saturate(1.4)`, border `1px solid rgba(255,255,255,0.6)`, radius 9px, shadow `0 4px 14px rgba(20,28,38,.10), inset 0 1px 0 rgba(255,255,255,.35)`, ink `#141c24`, IBM Plex Mono 600 10px uppercase, letter-spacing .08em. Fade .25 s, scale .94 → 1.

## Playground pop-up
- Same glass pop-up shell as the other pages (panel about 80vw x 90vh). Inside, logos and logo animations sit on a diagonal track that loops endlessly; the wheel, a drag or the arrow keys move it. Hovering a tile ripples its edges like liquid glass (SVG filter `#pg-liquid`), and clicking the centred tile swings it out to fill the screen, tilted right, while Back or Escape swings it back, tilted left. See DESIGN.md, Playground.
- While open, the overlay stops wheel/pointer/click propagation and arrow keys are ignored by the scene, so the season never changes.
- Six placeholder tiles: put an `<img>` or `<video>` inside a tile's `.pg-card__media` (see the comment above the playground template).

## TODO for the real build
- Click destinations for About Me / Resume / Experience.
- Real Playground logos and logo animations.
- Fonts: only IBM Plex Mono 400/500 are loaded; the label's 600 is synthesised by the browser. Load 600 if you want true semibold.
