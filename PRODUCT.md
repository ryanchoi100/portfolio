# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

- **Recruiters and hiring managers.** They skim. They need to see the role (product / UX designer), recent experience and a resume within seconds, then decide whether to reach out.
- **Design and engineering leads.** They go deep. They read case studies to judge design thinking, process, craft and outcomes.
- **Peers and the design community.** They come for the experiments and the craft of the site itself.

## Product Purpose

The personal portfolio of **Ryan Choi, UI/UX & Brand Designer** (per the resume; a Computer Science and Design student at Northeastern University, expected 2028). Success is a mix: the site must be job-ready (a visit can end in an interview request or a resume download) and also be a home for experiments and personal work.

## Positioning

The portfolio is entered through a painted lake landscape that cycles Spring → Summer → Autumn → Winter as the visitor scrolls, and the objects in the scene are the navigation. A designer's portfolio you explore rather than read.

Professional positioning comes from the resume: UI/UX and brand design across internships (Sagetopia, IT Concepts) and design-lead projects (Boston Climate Action Network, Rainfall, Recreon), with strengths in prototyping, accessibility, design systems and brand identity. Anything beyond the resume is still open; do not invent it.

## Operating Context

- Navigation by scene object: house → About Me, tree → Resume, boat (snowman in winter) → Interfaces (projects and experience), garden → Playground. Each opens a frosted-glass pop-up over the scene.
- Seasons change by wheel, touch swipe and arrow / Page / Space keys. While a pop-up is open the season never changes.
- A sections menu, invisible until tabbed into, opens every pop-up from the keyboard.
- Visitors arrive on desktop and on phones. The painting keeps its proportions on every screen; on phones it is wider than the screen, so a sideways swipe pans across it (up/down still changes the season) and every object, the boat included, can be reached and tapped.

## Capabilities and Constraints

- One static `index.html`: vanilla JS, no dependencies, no build step. Must be served over HTTP, because the canvas reads image pixels and `file://` fails.
- The scene handoff is high fidelity. Positions, timings, easings and hitboxes are tuned: port them, don't "clean them up".
- The owner asked that the season scroll, the scene artwork and the fireflies (not in the current build) not be changed without asking.
- All four pop-ups share one reusable shell, and pages differ only in content (`<template data-popup-page>` blocks).
- The Resume pop-up shows the PDF page itself (origami unfold), sized to fit a desktop screen without scrolling, with Open PDF and Download.
- Deploy: GitHub Pages from `main`; a custom domain is planned for later.
- Undecided:
  - the remaining case studies: BCAN has a full draft written from the owner's own text; Sagetopia, Rainfall, Recreon and IT Concepts have short pages built only from the resume, marked "Full case study in progress"
  - whether a Contact page or mailbox is added later (explicitly not now)

## Brand Commitments

- The painted seasonal scene (`seasons/` plates, tree, reflection and window-light assets) is the identity and is binding.
- The glass pop-up look is the established system, documented in DESIGN.md ("The Painted Season").

## Evidence on Hand

- Artwork: `seasons/` (four seasons × plate, tree, reflection, lights).
- Resume: `resume/RyanChoi_Resume.pdf` (one page; also rendered to `resume/resume-page.webp` for the unfold). It is the source for About Me and Interfaces. It includes a phone number and email, so it is public once deployed.
- BCAN case-study text: supplied by the owner (scope, client, year, industry, context, approach, outcome); it is the source for the BCAN page.
- Still missing: a portrait photo, full case studies for the other four projects, all project imagery (every image is a labelled placeholder) and Playground content (six placeholder cards). There are no metrics, client quotes or testimonials beyond the resume. Future work must not fabricate any of them.

## Product Principles

1. **Recruiter in seconds.** The scene must never make the role, experience or resume hard to find. The fast path to them is always one click or one key away.
2. **The scene is the navigation, not decoration.** New sections attach to the landscape and its objects instead of competing UI. The artwork is never sacrificed for interface.
3. **Show the thinking.** Interfaces exists for leads: process, decisions and outcomes, not just screenshots.
4. **Experiments stay in the Playground.** Personal and exploratory work is welcome, kept apart from the job-critical path.
5. **Real or nothing.** Placeholder content is labelled as placeholder until the owner supplies the real thing; nothing is invented to fill a gap.

## Accessibility & Inclusion

- Every section must be reachable without a pointer (keyboard menu, focus kept inside open pop-ups, focus returned on close) and by touch on every screen size.
- Respect `prefers-reduced-motion`: no scaling, sliding or stagger, only short fades.
