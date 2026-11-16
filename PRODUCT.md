# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

- **Recruiters and hiring managers.** They skim. They need to see the role (product / UX designer), recent experience and a resume within seconds, then decide whether to reach out.
- **Design and engineering leads.** They go deep. They read case studies to judge design thinking, process, craft and outcomes.
- **Peers and the design community.** They come for the experiments and the craft of the site itself.

## Product Purpose

A personal portfolio that presents its owner as a **product / UX designer**. Success is a mix: the site must be job-ready (a visit can end in an interview request or a resume download) and also be a home for experiments and personal work.

## Positioning

The portfolio is entered through a painted lake landscape that cycles Spring → Summer → Autumn → Winter as the visitor scrolls, and the objects in the scene are the navigation. A designer's portfolio you explore rather than read.

Open: the owner's professional positioning (specialism, industries, the kind of problems they are known for) has not been stated yet. Do not invent it.

## Operating Context

- Navigation by scene object: house → About Me, tree → Resume, boat (snowman in winter) → Experience & Projects, garden → Playground. Each opens a frosted-glass pop-up over the scene.
- Seasons change by wheel, touch swipe and arrow / Page / Space keys. While a pop-up is open the season never changes.
- A sections menu, invisible until tabbed into, opens every pop-up from the keyboard.
- Visitors arrive on desktop and on phones. The scene crops to the viewport, so on narrow phones the boat and snowman are off-screen. Experience is currently unreachable by touch there (open issue, needs a decision).

## Capabilities and Constraints

- One static `index.html`: vanilla JS, no dependencies, no build step. Must be served over HTTP, because the canvas reads image pixels and `file://` fails.
- The scene handoff is high fidelity. Positions, timings, easings and hitboxes are tuned: port them, don't "clean them up".
- The owner asked that the season scroll, the scene artwork and the fireflies (not in the current build) not be changed without asking.
- All four pop-ups share one reusable shell, and pages differ only in content (`<template data-popup-page>` blocks).
- Undecided:
  - the owner's display name and title
  - the deploy target and domain
  - real link destinations (resume PDF, case studies, project pages)
  - whether a Contact page or mailbox is added later (explicitly not now)

## Brand Commitments

- The painted seasonal scene (`seasons/` plates, tree, reflection and window-light assets) is the identity and is binding.
- The existing glass pop-up look is the established system. It is documented in code (the GLASS TOKENS block in `index.html`); no DESIGN.md exists yet.

## Evidence on Hand

- Artwork: `seasons/` (four seasons × plate, tree, reflection, lights).
- No real content yet. Every pop-up holds placeholder copy, the resume download and all project links point nowhere, and the Playground has six placeholder cards. There is no bio, resume, case study, project imagery, metric, client name or testimonial on hand. Future work must not fabricate any of them.

## Product Principles

1. **Recruiter in seconds.** The scene must never make the role, experience or resume hard to find. The fast path to them is always one click or one key away.
2. **The scene is the navigation, not decoration.** New sections attach to the landscape and its objects instead of competing UI. The artwork is never sacrificed for interface.
3. **Show the thinking.** Experience & Projects exists for leads: process, decisions and outcomes, not just screenshots.
4. **Experiments stay in the Playground.** Personal and exploratory work is welcome, kept apart from the job-critical path.
5. **Real or nothing.** Placeholder content is labelled as placeholder until the owner supplies the real thing; nothing is invented to fill a gap.

## Accessibility & Inclusion

- Every section must be reachable without a pointer (keyboard menu, focus kept inside open pop-ups, focus returned on close) and by touch on every screen size.
- Respect `prefers-reduced-motion`: no scaling, sliding or stagger, only short fades.
