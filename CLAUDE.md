# CLAUDE.md — building themes for `my-themes`

This repository is a **gallery of enterprise design systems / UI themes**. Each theme lives in
`themes/<name>/` and ships a self-contained demo, a written spec, and a README. When asked to
create or modify a theme, follow this document exactly. These are hard requirements, not
suggestions.

> **Adhere to `PRINCIPALS.md`.** Every theme — its demo, its spec, and its components — **must
> adhere to the UI/UX instruction set in [`PRINCIPALS.md`](./PRINCIPALS.md)** (the foundational
> philosophy, usability heuristics, layout, typography, color, hierarchy, interaction, motion,
> forms, states, accessibility, responsive design, performance, anti-patterns, and the pre-ship
> checklist). It is the floor that all themes sit on. Where a theme's own opinionated principles
> add to it, they may go further — but never below the `PRINCIPALS.md` floor. Read it before you
> start and run its Pre-Ship Checklist (§20) before you call a theme done. The canonical source
> is also kept one level up at `../PRINCIPALS.md`; the in-repo copy is the version themes bind to.

---

## The four non-negotiables

Every theme **must** be:

1. **Not generic.** It needs a strong, specific, defensible point of view — a metaphor, a real
   design lineage, and signature decisions you can name. "Modern rounded SaaS," a default Tailwind
   look, an Inter-everything dashboard, or "Bootstrap with a new accent" are rejected. Before
   building, write the one-sentence thesis ("a dashboard is a front page"). If you can't, you don't
   have a theme yet. Each new theme must also be a **distinct pole** from the ones already in the
   repo (see "Existing themes" below) — different metaphor, type, structure, and palette.

2. **Responsive and mobile-friendly — but never mobile-only.** The demo must look genuinely
   excellent on a **desktop monitor** *and* collapse gracefully to **mobile**. Do **not** render a
   phone mock centered in a desktop window — that is a failure. Use real breakpoints: a full
   desktop layout (e.g. sidebar + multi-column content) that reflows to a single column with a
   drawer/hamburger and/or bottom nav on small screens. Touch targets ≥ 44px. Test mentally at
   ~375px, ~768px, and ≥1280px.

3. **Polished and professional.** Production quality. Deliberate spacing rhythm, type scale,
   contrast, alignment, hover/active/focus states, empty/loading/error states, and motion. No
   half-finished screens, no lorem misalignment, no clipping. It should look like a real product.

4. **Token-driven, accessible, zero-build.** All visual values resolve to CSS custom properties
   so light/dark is a token swap. WCAG 2.1 AA on the actual surfaces (verify contrast on tinted
   backgrounds, both modes). One self-contained `index.html` using CDNs (Tailwind Play, a font,
   Alpine, Lucide, Chart.js) — no build step.

---

## The demo must be full-fledged

A theme's `index.html` is not a landing page or a single screen. It is a **complete, working app
demo** that exercises the design system across real enterprise surfaces. Every demo **must**
include all of the following, themed consistently:

- **A BI / analytics dashboard page** — KPI tiles **and** real charts (Chart.js): at least a
  line/area, a bar, and a doughnut/pie, plus a data table. Charts must re-render correctly on
  theme (edition) switch and when their tab becomes visible.
- **Data tables** — sortable-looking headers, status cells, zebra/hover, responsive (horizontal
  scroll or card reflow on mobile), and at least one **inline-editable cell** (e.g. a status
  `<select>` or click-to-edit value that updates the row).
- **The full range of inputs** — text, search, `<select>`, textarea, toggle/switch, segmented
  control, stepper (+/−), filter chips, and a numeric/inline-editable field. All keyboard usable
  with visible focus.
- **Modals** — a centered modal dialog (e.g. a "new record" form) with scrim, Esc-to-close, and a
  working create/confirm action.
- **Side drawers** — a right-hand **edit drawer** ("app drawer edit": open a record, edit its
  fields inline, Save/Cancel) **and** a left **navigation drawer** for mobile (hamburger).
- **Inline edits** — at least two: an editable table cell and a click-to-edit field (e.g. a name
  or reading that becomes an input with Save/Cancel).
- **Feedback** — toasts/snackbars for actions, plus status chips / badges using a consistent
  semantic system.
- **Navigation** — a persistent app shell (sidebar/top bar) where **every** nav item routes to a
  real, distinct, populated page. No dead links, no "coming soon" stubs.
- **Light + dark** ("editions") toggle, wired through tokens.

Treat this list as a checklist. A demo missing any of these is not done.

---

## Existing themes (keep new ones distinct)

| Theme | Metaphor | Type | Structure | Surface | Accent |
| --- | --- | --- | --- | --- | --- |
| **meridian-enterprise** | Instrument panel (Carbon) | IBM Plex Sans + Mono | Boxed 2px grid, flat | Cool gray, white | Carbon blue |
| **broadsheet** | Financial front page | Fraunces + Archivo + Spline Mono | Hairline rules + columns, flat | Tinted newsprint | Claret |
| **frontline** | Field / operations app | Saira + Martian Mono | Rounded, elevated cards | Hi-vis concrete | Safety orange |

A new theme must not overlap these on metaphor, typography, structure, and palette all at once —
pick an unexplored pole (e.g. a different domain, a different type voice, a different density).

---

## Structure & wiring

```
themes/<name>/
  index.html        # the full-fledged, self-contained demo (see above)
  <name>.md         # the design spec (principles, tokens, type, color, components, a11y, checklist)
  README.md         # overview: thesis, contrast vs other themes, principles, quick start, theming
```

When adding a theme, also:
- Add a row to the root [`README.md`](./README.md) themes table and update the theme-count badge.
- Add a card to the landing [`index.html`](./index.html) gallery and bump its count.
- Keep the spec parallel in quality to the existing specs; state the thesis and the contrast with
  the other themes explicitly.

## Conventions

- **Tokens:** define light under `:root` and dark under `html.dark` (or `.theme-*`). Use a
  dedicated structural separator token for chrome (sidebar edge, top bar) that is a touch stronger
  than card hairlines, so the layout reads clearly.
- **Tech:** Tailwind Play CDN (with an inline `tailwind.config` for fonts/colors), Alpine for
  state, Lucide for icons, Chart.js for charts. Call `lucide.createIcons()` after Alpine renders
  and re-render charts on edition switch / tab activation (guard hidden canvases via
  `offsetParent === null`).
- **Self-contained:** no local build, no bundler; everything works by opening the file.
- **Definition of done:** the four non-negotiables hold, the full-fledged demo checklist passes,
  the `PRINCIPALS.md` Pre-Ship Checklist (§20) passes, and the theme is wired into the gallery.

## Workflow notes

- **Do not `git push` unless explicitly asked.** Commit locally if useful, but pushing is the
  user's call.
- A live preview server can be run with `python3 -m http.server 8989 --bind 0.0.0.0` from a
  theme's folder (LAN: `http://172.25.1.22:8989/`). It serves from disk, so edits are live on
  refresh.
