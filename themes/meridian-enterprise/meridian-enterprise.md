# Meridian Enterprise — Theme Design Specification

> **Version 1.0** · Carbon-grade B2B design system · Light + Dark (Gray-90 / Gray-100)
> Tagline: **"Calm, governance-grade software for people who run the business."**

A meridian is the line a navigator uses to fix position with confidence. This system is
named for that idea: in dense, high-stakes enterprise software, the interface should be the
fixed reference that lets an operator always know *where they are, what is true right now, and
what to do next.* Meridian is not a marketing aesthetic bolted onto an app — it is a
**productive, data-first system** in the lineage of IBM Carbon: disciplined tokens, sharp 1px
borders, a strict 2px grid, and motion that informs rather than entertains.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Brand & Voice](#2-brand--voice)
3. [Color System](#3-color-system)
4. [Typography](#4-typography)
5. [Spacing, Grid & Layout](#5-spacing-grid--layout)
6. [Borders, Radius & Elevation](#6-borders-radius--elevation)
7. [Motion](#7-motion)
8. [Iconography](#8-iconography)
9. [Interactive States](#9-interactive-states)
10. [Component Principles](#10-component-principles)
11. [Data & Business Intelligence](#11-data--business-intelligence)
12. [Accessibility](#12-accessibility)
13. [Content & Microcopy](#13-content--microcopy)
14. [Theming & Tokens in Practice](#14-theming--tokens-in-practice)
15. [Implementation Checklist](#15-implementation-checklist)
16. [Universal UX Foundations (Heuristics & Laws)](#16-universal-ux-foundations-heuristics--laws)
17. [Anti-Patterns Meridian Forbids](#17-anti-patterns-meridian-forbids)
18. [Pre-Ship Checklist](#18-pre-ship-checklist)
19. [Component Specifications & Code](#19-component-specifications--code)
20. [Component State Matrix](#20-component-state-matrix)
21. [Keyboard Shortcuts](#21-keyboard-shortcuts)
22. [Internationalization & RTL](#22-internationalization--rtl)
23. [Governance, Versioning & Contribution](#23-governance-versioning--contribution)

> **Foundations note.** Meridian's seven principles (§1) are this system's *specific,
> opinionated* expression of a broader, durable body of UX practice — Nielsen's 10 heuristics,
> the classic interaction laws, and the craft rules in our base instruction set
> (`PRINCIPALS.md`). Sections §16–§18 fold that instruction set into Meridian so a builder has
> one document: the universal rule **and** the Meridian decision that satisfies it. Where the
> two could ever conflict, the Meridian principle governs (earlier number wins) — but it is
> built never to fall below the universal floor.

---

## 1. Design Principles

Seven principles govern every decision. When two guidelines conflict, the **earlier**
principle wins. Each maps to the universal heuristics and laws catalogued in §16 — the
parenthetical references show the lineage.

### P1 — Clarity over decoration
Every pixel must earn its place by communicating state, hierarchy, or affordance. We remove
before we add. Ornament that does not carry information (gradients-for-mood, drop shadows on
flat surfaces, decorative illustration inside the working canvas) is rejected. *Rationale: in
software people use for eight hours a day, decoration becomes noise, and noise is fatigue.*
*(Lineage: aesthetic & minimalist design; "clarity beats cleverness"; Chanel's "remove one thing.")*

### P2 — Truth is immediate
The current state of the system is always visible without a click. Status, freshness ("updated
12s ago"), connection health, and the consequences of an action are surfaced *before* the user
acts, not discovered after. *Rationale: enterprise operators make decisions with real
financial, clinical, or safety stakes; ambiguity is a defect, not a style choice.*
*(Lineage: visibility of system status; recognition over recall; help users recover from errors.)*

### P3 — Dense, but disciplined
We embrace information density — operators want more on screen, not less — but density is
earned through a strict 2px spacing grid, consistent alignment, and ruthless typographic
hierarchy. Density without discipline is clutter; discipline makes density legible. *Rationale:
a control tower is dense and calm at the same time because everything has a fixed place.*
*(Lineage: Miller's Law — chunk content; Law of Proximity; "constraints create quality.")*

### P4 — Sharp & precise
Small radii (2–4px), crisp 1px borders, hairline gridlines. The interface looks engineered,
not soft. Edges are honest about where one region ends and another begins. *Rationale:
precision signals trustworthiness; an instrument panel earns confidence by looking exact.*
*(Lineage: consistent radii/borders/shadows; pixel-snap; "spend boldness in one place.")*

### P5 — Tokens, not decisions
No one chooses a raw hex, a magic margin, or a one-off duration in a feature branch. Every
value resolves to a named token (`--text-secondary`, `space-3`, `duration-fast`). Theming,
dark mode, and rebranding are then a token swap, never a refactor. *Rationale: a design system
that depends on individual judgement does not scale past one team.*
*(Lineage: tokenize everything; single source of truth; consistency & standards.)*

### P6 — Accessible by default, not by audit
WCAG 2.1 AA is the floor, designed in from the first frame: visible focus rings, 4.5:1 body
text contrast, colour never the sole signal, 44px touch targets, full keyboard operability.
*Rationale: accessibility retrofitted is accessibility half-done; building it in costs nothing
and excludes no one.* *(Lineage: WCAG 2.1/2.2 AA; "the quality floor is invisible but mandatory";
verify, don't assume.)*

### P7 — Productive motion
Motion exists to explain causality and continuity — where a panel came from, that a value just
changed — in short, standard-eased durations (70–240ms). A separate, slower "expressive" set is
reserved for rare large moments (onboarding, first-run). Motion is never load-bearing for
meaning and always respects `prefers-reduced-motion`. *Rationale: in a productivity tool, a
half-second animation repeated 400 times a day is half a second stolen 400 times.*
*(Lineage: Doherty Threshold (<400ms); motion serves meaning; "one orchestrated moment beats
scattered effects"; never block input.)*

---

## 2. Brand & Voice

| Attribute | Meridian is… | Meridian is **not**… |
|---|---|---|
| Personality | Calm, exact, dependable, quietly expert | Playful, loud, trendy, cute |
| Tone of voice | Plain, direct, second person, present tense | Salesy, jargon-heavy, apologetic |
| Visual feel | Instrument panel, control tower, ledger | Landing page, dribbble shot, hero banner |
| Emotional goal | "I trust this. I know what's happening." | "Wow, pretty." |

**The one-paragraph manifesto.** Meridian is for the people who keep the business running — the
analyst reconciling a ledger, the nurse reading a census board, the engineer watching a service
degrade. They do not want to be delighted; they want to be *correct, quickly.* So Meridian
spends its craft budget on legibility, state, and trust instead of spectacle. It is dense
because their work is dense, sharp because their decisions are exact, and calm because calm is
what competence feels like.

---

## 3. Color System

Color is **functional**. Hue carries meaning (blue = interactive/brand, red = danger/down,
green = healthy/up, yellow = warning/attention). Neutral grays do the structural work of
surfaces, borders, and text. Three themes are first-class: **White** (light), **Gray-90**, and
**Gray-100** (dark, canonical for SOC / observability domains).

### 3.1 Brand / Interactive (Blue)

The primary scale. `blue-60` is the canonical interactive color in light themes; `blue-50` in
dark themes (it holds contrast on dark surfaces).

| Token | Hex | Use |
|---|---|---|
| `blue-10` | `#edf5ff` | Selected-row tint, subtle info background |
| `blue-20` | `#d0e2ff` | Hover on selected, info banner fill |
| `blue-30` | `#a6c8ff` | Disabled-on-color, decorative |
| `blue-40` | `#78a9ff` | Dark-theme links, chart series |
| `blue-50` | `#4589ff` | **Dark-theme interactive**, focus on dark |
| `blue-60` | `#0f62fe` | **Primary interactive** (buttons, links, focus) |
| `blue-70` | `#0043ce` | Hover on primary button |
| `blue-80` | `#002d9c` | Active/pressed primary |
| `blue-90` | `#001d6c` | Headings on light, deep accents |
| `blue-100`| `#001141` | Maximum-contrast brand ink |

### 3.2 Neutral Gray Scale

The structural backbone. Ten steps, gray-10 → gray-100.

| Token | Hex | Primary use |
|---|---|---|
| `gray-10` | `#f4f4f4` | `layer-01` surface (light), subtle fill |
| `gray-20` | `#e0e0e0` | `border-subtle`, dividers, disabled fills |
| `gray-30` | `#c6c6c6` | Disabled text, strong dividers |
| `gray-40` | `#a8a8a8` | Placeholder text, icons-muted |
| `gray-50` | `#8d8d8d` | `border-strong`, secondary icons |
| `gray-60` | `#6f6f6f` | Tertiary text, dark hover surfaces |
| `gray-70` | `#525252` | **Secondary text** (light), chart text |
| `gray-80` | `#393939` | Dark `layer`, dark borders |
| `gray-90` | `#262626` | Dark canvas (Gray-90 theme) |
| `gray-100`| `#161616` | **Primary text** (light); darkest canvas |

### 3.3 Semantic Colors

Never the *only* signal — always paired with an icon and/or text label (see P6).

| Role | Light | Dark | Pair with |
|---|---|---|---|
| Danger / Down / Error | `red-60 #da1e28` | `red-50 #fa4d56` | `alert-circle`, "Error" |
| Danger fill / Active | `red-70 #a2191f` | `red-30 #ffd7d9` | — |
| Success / Up / Healthy | `green-60 #24a148` | `green-50 #42be65` | `check-circle`, "Healthy" |
| Warning / Attention | `yellow-30 #f1c21b` | `yellow-30 #f1c21b` | `alert-triangle`, "Warning" |
| Warning (text-safe) | `yellow-40 #d2a106` | `yellow-20 #fdd13a` | — |
| Info / Brand neutral | `blue-60 #0f62fe` | `blue-50 #4589ff` | `info`, "Info" |

> **Yellow caution.** `yellow-30` fails 4.5:1 against white. For warning *text* use
> `yellow-40` (`#d2a106`) on light; reserve `yellow-30` for fills, dots, and large badges
> where contrast rules differ.

### 3.4 Semantic Role Tokens (theme-aware)

These are the tokens features actually consume. They resolve per theme, so a component written
once works in all three.

| Role token | White | Gray-90 | Gray-100 |
|---|---|---|---|
| `--bg` (canvas) | `#ffffff` | `#262626` | `#161616` |
| `--layer-01` | `#f4f4f4` | `#393939` | `#262626` |
| `--layer-02` | `#ffffff` | `#525252` | `#393939` |
| `--field` (input) | `#f4f4f4` | `#393939` | `#262626` |
| `--text-primary` | `#161616` | `#f4f4f4` | `#f4f4f4` |
| `--text-secondary` | `#525252` | `#c6c6c6` | `#c6c6c6` |
| `--text-placeholder` | `#a8a8a8` | `#6f6f6f` | `#6f6f6f` |
| `--text-on-color` | `#ffffff` | `#ffffff` | `#ffffff` |
| `--border-subtle` | `#e0e0e0` | `#393939` | `#393939` |
| `--border-strong` | `#8d8d8d` | `#8d8d8d` | `#8d8d8d` |
| `--interactive` | `#0f62fe` | `#4589ff` | `#4589ff` |
| `--hover-ui` | `#e8e8e8` | `#4c4c4c` | `#2c2c2c` |
| `--selected-ui` | `#e0e0e0` | `#525252` | `#393939` |
| `--focus` | `#0f62fe` | `#ffffff` | `#ffffff` |

### 3.5 Contrast Rules (WCAG)

- Body text uses `--text-primary` (≈ 16:1 on white) or `--text-secondary` (≈ 7.4:1) — both AA & AAA for body.
- `--text-placeholder` (~2.9:1) is **non-essential only**; never use it for required information.
- Interactive `blue-60` on white is 4.6:1 → AA for text and UI components.
- White text on `blue-60`, `red-60`, `green-60` all clear 4.5:1.
- Focus ring (`--focus`) must hit 3:1 against both the component and its background — hence
  white focus rings on dark themes.

---

## 4. Typography

**IBM Plex Sans** for all UI; **IBM Plex Mono** for code, IDs, and tabular data. Two scales: a
compact **Productive** scale (the default for dense app UI) and a roomier **Expressive** scale
for marketing-adjacent moments (cover, empty states, onboarding).

Load: `IBM+Plex+Sans:wght@300;400;500;600;700` + `IBM+Plex+Mono:wght@400;500;600`.

### 4.1 Productive Type Scale (default)

| Token | px / rem | Line-height | Weight | Tracking | Use for |
|---|---|---|---|---|---|
| `label-01` | 12 / 0.75 | 16px | 400 | +0.32px | Field labels, captions, table headers |
| `helper-text` | 12 / 0.75 | 16px | 400 | +0.32px | Helper & error text under fields |
| `body-compact` | 14 / 0.875 | 18px | 400 | 0 | Dense body, table cells, default UI text |
| `body-01` | 14 / 0.875 | 20px | 400 | 0 | Default paragraph body |
| `heading-compact` | 14 / 0.875 | 18px | 600 | 0 | Inline section headings, card titles |
| `heading-01` | 16 / 1.0 | 22px | 600 | 0 | Subsection headings |
| `heading-03` | 20 / 1.25 | 28px | 400 | 0 | Page/section headings |
| `heading-04` | 28 / 1.75 | 36px | 400 | 0 | Major headings |

### 4.2 Expressive Type Scale

| Token | px / rem | Weight | Use for |
|---|---|---|---|
| `heading-05` | 32 / 2.0 | 400 | Feature headings |
| `heading-06` | 42 / 2.625 | 300 | Hero / cover headings |
| `display-01` | 54 / 3.375 | 300 | Marketing display |
| `display-02` | 76 / 4.75 | 300 | Maximum display |

### 4.3 Typography Rules
- **Weights:** 400 body, 500 emphasis/links, 600 headings & buttons, 300 only at ≥32px.
- **Numerals:** use **tabular** (`font-variant-numeric: tabular-nums`) for any column of
  numbers, KPIs, currency, and tables — digits must align vertically. Proportional numerals are
  fine in running prose.
- **Mono:** use IBM Plex Mono for IDs, hashes, timestamps, codes, token names, and any value a
  user might copy or compare character-by-character.
- **Measure:** body copy caps at ~75ch for readability.
- **Casing:** sentence case everywhere (labels, buttons, headings). No ALL-CAPS except 12px
  overline labels with positive tracking.

---

## 5. Spacing, Grid & Layout

### 5.1 The 2px Spacing Grid
All spacing derives from a **2px base**. The named scale:

| Token | px | Common use |
|---|---|---|
| `space-01` | 2 | Hairline gaps, icon-to-text nudge |
| `space-02` | 4 | Tight padding, chip internals |
| `space-03` | 8 | Default small gap, button padding-y |
| `space-04` | 12 | Compact component padding |
| `space-05` | 16 | **Default component padding**, card gutters |
| `space-06` | 24 | Section spacing, card padding |
| `space-07` | 32 | Group separation |
| `space-08` | 40 | Large section gaps |
| `space-09` | 48 | Page section rhythm |
| `space-10` | 64 | Major page divisions |

> **Rule:** never use a value off the scale. If 10px "looks right," the layout is misaligned —
> pick 8 or 12.

### 5.2 Layout Grid
- **16-column** fluid grid. Gutters `space-05` (16px), outer margins `space-05`→`space-07`
  responsive.
- **Max content width** 1584px; the working canvas can also run full-bleed for dashboards.
- **App shell:** fixed top bar (48px), collapsible left side-nav (256px expanded / 48px rail),
  optional sticky context/breadcrumb bar (40px), then scrollable main.

### 5.3 Breakpoints

| Token | Min width | Columns | Notes |
|---|---|---|---|
| `sm` | 320px | 4 | Mobile; side-nav becomes a drawer |
| `md` | 672px | 8 | Tablet |
| `lg` | 1056px | 16 | Desktop; side-nav docks |
| `xl` | 1312px | 16 | Wide desktop |
| `max`| 1584px | 16 | Max canvas |

**Mobile rules:** side-nav → hamburger drawer; data tables scroll horizontally with sticky
header and sticky first column; every target ≥44px; usable at 360px wide.

---

## 6. Borders, Radius & Elevation

### 6.1 Radius
Sharp by identity. `radius-sm 2px` is the default for buttons, inputs, cards, and tiles.
`radius-md 4px` for nested/large surfaces. `radius-lg 8px` only for modals/overlays.
**Never** fully-rounded except avatars and circular icon-only toggles.

### 6.2 Border Widths
- `1px` — the workhorse. Subtle (`--border-subtle`) for structure, strong (`--border-strong`)
  for emphasis and input outlines on focus-adjacent states.
- `2px` — focus ring only, and the left "selected" indicator on nav items.

### 6.3 Elevation
Meridian is **mostly flat** — borders define regions, not shadows (P4). Shadows are reserved
for genuinely floating layers:

| Token | Shadow | Use |
|---|---|---|
| `elevation-0` | none | Default surfaces (use borders) |
| `elevation-01` | `0 1px 2px rgba(0,0,0,.10)` | Dropdowns, popovers, hover-cards |
| `elevation-02` | `0 2px 6px rgba(0,0,0,.12)` | Toasts, menus |
| `elevation-03` | `0 8px 24px rgba(0,0,0,.18)` | Modals, command palette |

### 6.4 Sticky chrome — subtle glass (the one sanctioned translucency)

Meridian is otherwise flat and opaque (P1, P4). The **single exception** is the persistent
sticky chrome — the top bar and the breadcrumb/context bar — which uses a restrained,
token-driven translucency so page content faintly blurs beneath it on scroll, reinforcing
that the chrome floats above a live data surface. This is *subtlety*, not glassmorphism; do not
extend it to cards, panels, modals, or any content surface.

| Token | Background | Backdrop | Applied to |
|---|---|---|---|
| `glass-bar` | `color-mix(in srgb, var(--bg) 82%, transparent)` | `blur(8px) saturate(1.2)` | Breadcrumb / context bar |
| `glass-bar-2` | `color-mix(in srgb, var(--layer-02) 86%, transparent)` | `blur(8px) saturate(1.2)` | Product top bar |

Rules: (1) translucency is **token-derived** — it resolves per theme (White / Gray-90 /
Gray-100), never a hardcoded `rgba`. (2) Keep opacity ≥ 80% so text/controls stay legible and
contrast holds. (3) Always pair with the 1px `--border-subtle` bottom border — the border, not
the blur, defines the edge. (4) **Fallback:** where `backdrop-filter` is unsupported, fall back
to the **opaque** token (`var(--bg)` / `var(--layer-02)`) — a see-through bar without blur is a
defect, not a degraded state.

### 6.5 Z-Index Layers

| Layer | z | Examples |
|---|---|---|
| base | 0 | Page content |
| sticky | 100 | Sticky headers, scroll-spy bar |
| nav | 200 | Side-nav, top bar |
| dropdown | 300 | Menus, popovers, tooltips |
| overlay | 400 | Drawer/modal scrim |
| modal | 500 | Dialogs, command palette |
| toast | 600 | Notifications (always on top) |

---

## 7. Motion

Two motion families. Default to **Productive**.

### 7.1 Duration Tokens
| Token | ms | Use |
|---|---|---|
| `duration-fast-01` | 70 | Micro feedback (button press, checkbox) |
| `duration-fast-02` | 110 | Hover transitions, small fades |
| `duration-moderate-01`| 150 | Dropdown/expand, tab switch |
| `duration-moderate-02`| 240 | Drawer/panel slide, sidebar collapse |
| `duration-slow-01` | 400 | Expressive entrances (rare) |
| `duration-slow-02` | 700 | First-run / hero only |

### 7.2 Easing Tokens
- `ease-productive-standard` `cubic-bezier(0.2, 0, 0.38, 0.9)` — most UI changes.
- `ease-productive-entrance` `cubic-bezier(0, 0, 0.38, 0.9)` — elements entering.
- `ease-productive-exit` `cubic-bezier(0.2, 0, 1, 0.9)` — elements leaving (fast out).
- `ease-expressive-standard` `cubic-bezier(0.4, 0.14, 0.3, 1)` — large expressive moments.

### 7.3 Motion Rules
- Entrances ease-in slowly, exits ease-out quickly — leaving should feel decisive.
- Never animate `width`/`height`/`top`/`left` for layout-critical content; use `transform`/`opacity`.
- **`prefers-reduced-motion: reduce`** disables all non-essential motion (entrances,
  scroll-reveals, parallax); functional state changes become instant.
- Motion never conveys meaning that isn't also conveyed statically.

---

## 8. Iconography

- **Lucide** icon set: 2px stroke, geometric, matches IBM Plex weight.
- Sizes: `16px` (default in dense UI / inline with body), `20px` (buttons, nav), `24px`
  (section headers), `32px` (empty states).
- **Optical alignment:** icons sit on the text baseline; nudge with `space-01` if needed.
- Always pair a status icon with its semantic color *and* a text label — color is never alone.
- Icon-only buttons require an `aria-label` and a tooltip.

---

## 9. Interactive States

Every interactive element documents all of these. States are explicit tokens, not improvisation.

| State | Visual treatment |
|---|---|
| **Default** | Resting token values |
| **Hover** | `--hover-ui` background shift; cursor `pointer`; ≤110ms |
| **Focus** | `2px` `--focus` ring, `2px` offset; visible on keyboard nav (`:focus-visible`) |
| **Active / Pressed** | `--active-ui` / one shade darker; subtle 70ms press |
| **Selected** | `--selected-ui` fill + `2px` left brand indicator (nav/rows) |
| **Disabled** | `--text-disabled` text, `--border-subtle`, 0.4–1.0 opacity, no pointer, `aria-disabled` |
| **Loading** | Spinner or skeleton; control remains its size to avoid layout shift |
| **Error** | `red-60` 1px outline + helper text + `alert-circle`; `aria-invalid` |
| **Read-only** | No border/field fill, `--text-primary`, not focusable as an edit target |

---

## 10. Component Principles

General rules; each component in the live demo shows every applicable state.

- **Buttons.** Variants: `primary` (blue, one per view ideally), `secondary` (outline),
  `tertiary` (text+border-on-hover), `ghost` (text only), `danger` (red). Sizes: `sm 32px`,
  `md 40px`, `lg 48px`. Label is sentence case, verb-first ("Save changes"). Icon optional,
  leading. Full-width only in narrow/mobile or modals.
- **Inputs.** Anatomy is fixed: **label** (top, `label-01`) → **control** (`--field` fill, 1px
  bottom-or-full border) → **helper text** → **error text**. Required marked with "(required)" or
  `*` plus legend, never color alone.
- **Cards / Tiles.** 1px `--border-subtle`, `radius-sm`, `space-06` padding, flat by default.
  KPI tiles: label, big tabular number, delta with directional arrow + semantic color + text.
- **Tables.** The heart of the system. Sticky header, 1px row separators, 40px (default) / 32px
  (compact) / 48px (relaxed) row heights via density toggle, sortable headers, multi-select with
  a batch-action toolbar, right-aligned numerics with tabular figures, conditional color cells
  always paired with text/icon. Document empty, loading, and error states.
- **Navigation.** Left side-nav with selected indicator; breadcrumbs for depth; Cmd/Ctrl-K
  command palette for power users.
- **Feedback.** Inline alerts (banner, in-flow), toasts (transient, top-right, auto-dismiss with
  pause-on-hover), modals (blocking, for confirmation/critical), drawers (non-blocking detail).
- **Empty states.** Icon (32px), one-line cause, one-line next action, a primary action button.
  Never a blank panel.

---

## 11. Data & Business Intelligence

The showcase heart. Meridian is a data product before it is anything else.

- **Charts (Chart.js v4, themed).** Thin 1px gridlines in `--grid-line`; axis/label text in
  `--chart-text` (`gray-70`); categorical series use the fixed palette order in §11.1 so the
  same category keeps its color across charts. Line/area/stacked-bar are the
  defaults; one domain widget per use-case (gauge, heatmap, treemap, sankey-lite, status
  matrix). **Charts must restyle on theme toggle.**
- **Dashboards.** KPI tile grid (with delta + sparkline) → primary chart → secondary charts →
  filter/date-range bar. Freshness indicator on every live panel ("updated 12s ago").
- **Tables.** See §10. Treat the table as a first-class application surface, not a fallback.
- **Number formatting.** Tabular numerals, locale-aware grouping, explicit units, and a
  consistent rule for precision (e.g., currency 2dp, percentages 1dp, large counts abbreviated
  with full value on hover).
- **Color encoding.** Sequential for magnitude, diverging for above/below-target, categorical
  for discrete series — never a rainbow. Always provide a legend and a non-color cue.

### 11.1 Categorical series palette (fixed order)

Discrete series use this order **exactly**, starting at series 1. The Nth category always gets
the Nth color so a category keeps its color across every chart in the product. Do not reorder,
skip, or recolor by aesthetics. After 8 series, switch to grouping/"Other" rather than inventing
new hues.

| # | Light | Dark | Token / note |
|---|---|---|---|
| 1 | `#0f62fe` | `#4589ff` | `--interactive` (brand) |
| 2 | `#42be65` | `#42be65` | `green-50` |
| 3 | `#f1c21b` | `#f1c21b` | `yellow-30` |
| 4 | `#8d8d8d` | `#8d8d8d` | `gray-50` |
| 5 | `#a56eff` | `#be95ff` | purple |
| 6 | `#08bdba` | `#3ddbd9` | teal |
| 7 | `#d2a106` | `#fdd13a` | amber |
| 8 | `#6f6f6f` | `#c6c6c6` | gray (neutral last) |

> Semantic colors are **reserved** outside categorical use: `red-60` = down/error,
> `green-60` = up/healthy. Never use the danger red as a neutral series color. Single-series
> charts use `--interactive`; area fills use the line color at **13% alpha** (`…22` hex suffix).

**Sequential scale** (magnitude / heatmaps): `blue-10 → blue-20 → blue-40 → blue-60 → blue-80`.
**Diverging scale** (below ↔ target ↔ above): `red-60 ← gray-30 → green-60`.

---

## 12. Accessibility

AA is the floor, designed-in (P6).

- **Contrast:** body ≥ 4.5:1, large text & UI components ≥ 3:1. Documented per token (§3.5).
- **Focus:** every interactive element has a visible `2px` `--focus` ring via `:focus-visible`;
  a "Skip to content" link is the first focusable element.
- **Keyboard:** all features operable without a mouse. Menus/tabs/grids follow WAI-ARIA APG
  patterns (arrow keys, Home/End, Esc to dismiss). Focus is trapped in modals and restored on
  close.
- **ARIA:** semantic HTML first; ARIA roles/states (`aria-expanded`, `aria-current`,
  `aria-invalid`, `aria-live` for toasts) where native semantics fall short.
- **Color independence:** status always pairs color with icon + text.
- **Touch:** targets ≥ 44×44px; adequate spacing to prevent mis-taps.
- **Motion:** honor `prefers-reduced-motion` (§7.3).

---

## 13. Content & Microcopy

- **Voice:** plain, direct, second person, present tense. "We couldn't save your changes" not
  "An error has occurred."
- **Buttons:** verb-first, specific. "Delete invoice" beats "OK".
- **Errors:** say what happened, why if useful, and how to fix it — in that order. No blame, no
  jargon, no stack traces in the UI.
- **Empty states:** state the cause and the next step.
- **Numbers & dates:** locale-aware, with units and timezones explicit. Relative time
  ("3 min ago") for recency, absolute on hover.
- **Capitalization:** sentence case. **Terminology:** one word per concept, used consistently
  (don't alternate "client"/"customer").

---

## 14. Theming & Tokens in Practice

Meridian themes by swapping CSS custom properties on a root class — components never hard-code a
hex. Reference implementation:

```css
:root,
.theme-white {
  --bg:#ffffff;  --layer-01:#f4f4f4; --layer-02:#ffffff; --field:#f4f4f4;
  --text-primary:#161616; --text-secondary:#525252; --text-placeholder:#a8a8a8;
  --text-on-color:#ffffff; --text-disabled:#c6c6c6;
  --border-subtle:#e0e0e0; --border-strong:#8d8d8d;
  --interactive:#0f62fe; --hover-ui:#e8e8e8; --active-ui:#c6c6c6; --selected-ui:#e0e0e0;
  --focus:#0f62fe; --grid-line:#e0e0e0; --chart-text:#525252;
}

.theme-g100 {            /* Gray-100 — canonical dark for SOC / observability */
  --bg:#161616;  --layer-01:#262626; --layer-02:#393939; --field:#262626;
  --text-primary:#f4f4f4; --text-secondary:#c6c6c6; --text-placeholder:#6f6f6f;
  --text-on-color:#ffffff; --text-disabled:#6f6f6f;
  --border-subtle:#393939; --border-strong:#8d8d8d;
  --interactive:#4589ff; --hover-ui:#2c2c2c; --active-ui:#6f6f6f; --selected-ui:#393939;
  --focus:#ffffff; --grid-line:#393939; --chart-text:#c6c6c6;
}
```

```js
// Tailwind Play CDN config maps utilities to the same scales.
tailwind.config = {
  darkMode: 'class',
  theme: {
    fontFamily: {
      sans: ['"IBM Plex Sans"','system-ui','sans-serif'],
      mono: ['"IBM Plex Mono"','ui-monospace','monospace'],
    },
    borderRadius: { none:'0', sm:'2px', DEFAULT:'2px', md:'4px', lg:'8px' },
    extend: {
      colors: {
        blue:  {10:'#edf5ff',20:'#d0e2ff',30:'#a6c8ff',40:'#78a9ff',50:'#4589ff',
                60:'#0f62fe',70:'#0043ce',80:'#002d9c',90:'#001d6c',100:'#001141'},
        gray:  {10:'#f4f4f4',20:'#e0e0e0',30:'#c6c6c6',40:'#a8a8a8',50:'#8d8d8d',
                60:'#6f6f6f',70:'#525252',80:'#393939',90:'#262626',100:'#161616'},
        red:   {30:'#ffd7d9',50:'#fa4d56',60:'#da1e28',70:'#a2191f'},
        green: {30:'#a7f0ba',50:'#42be65',60:'#24a148',70:'#0e6027'},
        yellow:{20:'#fdd13a',30:'#f1c21b',40:'#d2a106'},
      },
    },
  },
};
```

**Token discipline rules.** (1) Features consume **role tokens** (`--text-secondary`), not
scale tokens (`gray-70`). (2) Scale tokens are referenced only inside theme definitions. (3) No
raw hex in components, ever. (4) Adding a brand = redefining role tokens, nothing else.

---

## 15. Implementation Checklist

A developer can ship a compliant screen by confirming each line:

- [ ] All color comes from role tokens; no raw hex in feature code.
- [ ] Type uses the Productive scale; numbers use tabular numerals.
- [ ] Every spacing value is on the 2px grid (no 10/15/18px).
- [ ] Radius is 2px (4px nested, 8px overlays only); borders are 1px.
- [ ] Surfaces are flat; shadows only on floating layers.
- [ ] Every interactive element shows hover, focus, active, disabled states.
- [ ] Focus rings visible (`:focus-visible`, 2px, correct `--focus` per theme).
- [ ] Status uses color **plus** icon **plus** text.
- [ ] Contrast verified: body ≥4.5:1, UI/large ≥3:1.
- [ ] Keyboard: full operability, focus trap in modals, Esc dismisses, skip link present.
- [ ] Motion within token durations; `prefers-reduced-motion` honored.
- [ ] Charts/tables: themed, tabular numerals, empty + loading + error states defined.
- [ ] Works at 360px; tables scroll with sticky header; targets ≥44px.
- [ ] Light **and** dark (Gray-90 / Gray-100) verified.

---

## 16. Universal UX Foundations (Heuristics & Laws)

Meridian does not replace the field's durable wisdom — it *implements* it. This section folds in
our base instruction set (`PRINCIPALS.md`) and states, for each universal rule, the **concrete
Meridian decision** that satisfies it. A builder should never have to choose between "the
heuristic" and "the system": here they are the same thing.

### 16.1 Nielsen's 10 Heuristics → Meridian mechanism

| # | Heuristic | How Meridian satisfies it |
|---|---|---|
| 1 | **Visibility of system status** | Freshness stamp on every live panel ("updated 12s ago"); skeletons on load; toasts on save; connection-lost banner; button loading state that holds its size. |
| 2 | **Match the real world** | Microcopy in the operator's domain language (§13); "Delete invoice", not "Submit". No internal/system jargon in labels. |
| 3 | **User control & freedom** | Cancel on every modal, Esc to dismiss, breadcrumb back-path, **undo-over-confirm** for reversible actions; destructive actions confirmed, not trapped. |
| 4 | **Consistency & standards** | One token set, one icon family (Lucide 2px), one word per concept; standard controls (native `<select>`, real `<button>`), never reinvented. |
| 5 | **Error prevention** | Disable genuinely-invalid actions (with explanation), confirm destructive ones, inline validation before submit, smart defaults to keep mistakes hard to make. |
| 6 | **Recognition over recall** | Persistent side-nav + breadcrumb so location is always visible; Cmd-K palette surfaces options rather than demanding memory; visible labels (never placeholder-only). |
| 7 | **Flexibility & efficiency** | Cmd/Ctrl-K command palette, keyboard operability throughout, density toggle, sensible defaults for novices — accelerators that don't penalise beginners. |
| 8 | **Aesthetic & minimalist design** | P1 made literal: flat surfaces, 1px borders instead of decoration, restrained palette, "remove one thing" before ship. |
| 9 | **Recognise, diagnose, recover from errors** | Errors state *cause → fix* in plain voice, keep user input intact, pair `red-60` with `alert-circle` + text, point to the next action (e.g. exception queue). |
| 10 | **Help & documentation** | This document *is* the searchable, task-focused reference; in-product help is contextual and tucked behind progressive disclosure, never blocking the 80% case. |

### 16.2 Interaction laws → Meridian rule

| Law | Statement | Meridian application |
|---|---|---|
| **Hick's Law** | More choices → slower decisions | Group + prioritise; one primary action per view; advanced options behind "More"/settings (progressive disclosure). |
| **Fitts's Law** | Bigger/closer targets are faster | Primary actions are large (40–48px); related controls are adjacent; touch targets ≥44px. |
| **Miller's Law** | ~7±2 items in working memory | Chunk nav and forms into labelled groups; KPI tiles in scannable sets, not walls. |
| **Jakob's Law** | Users expect your app to work like others | Standard shells, tabs, modals, tables — Carbon-familiar; we don't reinvent without reason. |
| **Doherty Threshold** | Keep response < ~400ms | Productive-motion durations cap at 240ms; optimistic UI + skeletons; feedback within 400ms or show progress. |
| **Peak-End Rule** | Judged by peak + ending | Polish the high-stakes moments (error recovery, save confirmation, empty→first-action) and the end of every flow. |
| **Law of Proximity** | Close = related | Spacing (not borders) is the primary grouping signal; the 2px grid encodes proximity. |

### 16.3 Craft rules adopted verbatim

These rules from `PRINCIPALS.md` are **mandatory** and already encoded in earlier sections; they
are restated here so nothing is implicit:

- **Design for real content,** not lorem ipsum — long account names, huge numbers, empty lists,
  failed states all appear in the live demo.
- **Constrain measure** to ~50–75ch for body text (§4).
- **Labels above fields, never placeholder-as-label** (§10); preserve input on error; one-column
  forms; mark the rarer of required/optional.
- **Real punctuation:** curly quotes, em dashes (—), proper ellipses (…).
- **Limit weights** to 300/400/500/600; hierarchy via size/weight/space before color.
- **Soft darks/lights:** large fills use `gray-100 #161616` / `gray-10 #f4f4f4`, not pure
  `#000`/`#fff`.
- **One signature, everything else quiet:** Meridian's signature is the **disciplined data
  surface** (tables + charts + KPI tiles). The chrome stays silent so the data is loud.

---

## 17. Anti-Patterns Meridian Forbids

If a screen exhibits any of these, it is non-compliant — regardless of how it looks:

- **Templated defaults** applied without reason (mood gradients, decorative serif accents, a lone
  acid accent on near-black). Meridian's choices are specific to dense B2B operations.
- **Happy-path-only** design — shipping without loading, empty, error, and offline states.
- **Placeholder-as-label** in forms; clearing user input on a single field error.
- **Inconsistent** spacing, radii, shadows, or mixed filled/outline icons.
- **Too many fonts/weights/colors** — visual noise. (Two families, ≤4 weights, tokenised palette.)
- **Low-contrast "elegant" gray text** below 4.5:1 used for essential information.
- **Mystery-meat navigation** — icon-only controls without `aria-label` + tooltip.
- **Dark patterns** — confirm-shaming, forced continuity, hidden costs, fake urgency. Banned
  outright; they violate the trust P2 exists to build.
- **Motion overload** — everything animating, or animation that blocks input.
- **Tiny/cramped touch targets**; centring long text; removing focus outlines without replacing.
- **Reinvented controls** that drop keyboard/screen-reader support.
- **Walls of options** with no defaults or grouping (Hick's Law violation).
- **Inconsistent terminology** for the same action across a flow.

---

## 18. Pre-Ship Checklist

The §15 list covers Meridian token compliance. This list — adopted from `PRINCIPALS.md` — covers
universal quality. **Both** must pass before a screen ships.

**Visual**
- [ ] Spacing on the 2px scale; everything aligns to the grid.
- [ ] Limited, intentional type scale and tokenised palette.
- [ ] Consistent radii, borders, shadows, one icon set.
- [ ] One clear focal point per screen; hierarchy obvious at a glance.

**Interaction & states**
- [ ] Every interactive element: hover, focus, active, disabled, loading.
- [ ] Loading, empty, error, success, offline states all designed.
- [ ] Feedback within ~400ms for every action.
- [ ] Destructive actions confirmed or undoable.

**Content**
- [ ] Plain, active, user-centred language; consistent vocabulary across the flow.
- [ ] Errors explain cause + fix; empty states invite action.
- [ ] Sentence case, no filler, real punctuation.

**Forms**
- [ ] Visible labels, inline validation, input preserved on error.
- [ ] Minimal fields, smart defaults, correct input types & `autocomplete`.

**Accessibility**
- [ ] Contrast ≥ 4.5:1 text / 3:1 large & UI.
- [ ] Fully keyboard operable, visible focus, logical tab order.
- [ ] Semantic HTML, labels/alt text, meaning never by color alone.
- [ ] `prefers-reduced-motion`, `prefers-color-scheme`, zoom-to-200% respected.
- [ ] Keyboard + screen-reader path traced manually (automated checks catch only ~30–40%).

**Responsive & performance**
- [ ] Works mobile → desktop; reflows rather than shrinks; targets ≥44px.
- [ ] No layout shift (CLS); content keeps stable size while loading.
- [ ] Fast feedback under ~400ms; perceived speed addressed (skeletons, optimistic UI).

**Polish**
- [ ] One signature element; everything else quiet.
- [ ] Removed one unnecessary thing.
- [ ] Inspected rendered output (screenshot) and re-checked against §16–§17.

> *These are operating guidelines, not rigid laws. Break a Meridian rule only deliberately, when
> the brief justifies it and you can state the reason — never by accident or omission.*

---

## 19. Component Specifications & Code

Principle-level rules live in §10. This section pins the **exact dimensions** and gives **copy-
paste markup** so a component can be rebuilt pixel-identically without a single judgement call.
All values are on the 2px grid. Snippets assume the role tokens of §3.4 and the `.btn`/`.field`/
`.tag` classes shipped in the demo.

### 19.1 Buttons

| Size | Height | Padding-x | Gap (icon↔label) | Icon | Font | Min touch target |
|---|---|---|---|---|---|---|
| `sm` | 32px | 12px | 6px | 16px | 12px / 600 | pad row to ≥44px on touch |
| `md` (default) | 40px | 16px | 8px | 16px | 14px / 600 | 44px |
| `lg` | 48px | 20px | 8px | 20px | 16px / 600 | 48px |

Radius `2px`. Icon-only button = the height as a square (32/40/48), icon centered, **mandatory**
`aria-label` + tooltip. Variants and their token mapping:

| Variant | Rest | Hover | Active | Border |
|---|---|---|---|---|
| `primary` | `--interactive` / `#fff` | `--interactive-hover` | `--interactive-active` | none |
| `secondary` | transparent / `--text-primary` | `--hover-ui` | `--active-ui` | 1px `--border-strong` |
| `ghost` | transparent / `--interactive` | `--hover-ui` | `--active-ui` | none |
| `danger` | `red-60 #da1e28` / `#fff` | `red-70 #a2191f` | `red-70` | none |
| `disabled` (any) | `--layer-01` / `--text-disabled` | — | — | none, `cursor:not-allowed` |

```html
<button class="btn btn-primary">Save changes</button>
<button class="btn btn-secondary btn-sm">
  <svg data-lucide="plus" class="w-4 h-4"></svg> Add row
</button>
<button class="btn btn-primary" disabled aria-disabled="true">Save changes</button>
```
```css
.btn{ display:inline-flex; align-items:center; gap:8px; height:40px; padding:0 16px;
  border-radius:2px; font:600 14px/1 "IBM Plex Sans"; border:1px solid transparent;
  transition:background .11s cubic-bezier(.2,0,.38,.9); cursor:pointer; }
.btn-primary{ background:var(--interactive); color:#fff; }
.btn-primary:hover{ background:var(--interactive-hover); }
```

### 19.2 Inputs / fields — anatomy & dimensions

Field anatomy, top to bottom: **label → control → helper text → error text**.

| Part | Spec |
|---|---|
| Label | `12px / 500`, `--text-primary`, margin-bottom `6px`. Required marker `(required)` in `--text-placeholder`. |
| Control height | `40px` default · `32px` compact · `48px` large |
| Control padding-x | `12px` |
| Control fill / border | `--field` bg, **1px bottom border** `--border-strong` (full 1px border acceptable for boxed variant) |
| Focus | `2px` `--focus` ring, `outline-offset:-2px` (inset, so it doesn't shift layout) |
| Error | bottom border `red-60`, `aria-invalid="true"`, error text below |
| Helper / error text | `12px / 400`; helper `--text-placeholder`, error `red-60` + `alert-circle` 14px |

```html
<div>
  <label for="acct" class="block text-[12px] font-medium mb-1.5">Account name</label>
  <input id="acct" class="field" placeholder="e.g. Northwind Trading" />
  <p class="text-[12px] txt-ph mt-1.5">Shown on invoices and statements.</p>
</div>
```
```css
.field{ width:100%; height:40px; padding:0 12px; background:var(--field);
  color:var(--text-primary); border:0; border-bottom:1px solid var(--border-strong); }
.field:focus{ outline:2px solid var(--focus); outline-offset:-2px; }
.field-error{ border-bottom-color:#da1e28; }
```

### 19.3 Badges, tags, status pills

| Spec | Value |
|---|---|
| Height | `24px` (sm `20px`) |
| Padding-x | `8px` (sm `6px`) |
| Gap (dot/icon↔text) | `4px` |
| Font | `12px / 500` |
| Radius | `2px` |
| Status fill / text (light) | success `#defbe6`/`#0e6027` · warning `#fff8e1`/`#d2a106` · danger `#fff1f1`/`#da1e28` · info `#edf5ff`/`#0043ce` · neutral `--layer-01`/`--text-secondary` |

Always icon **+** text (§P6). Dark theme: fill `rgba(255,255,255,.06)`, keep the text hue.

```html
<span class="tag" style="background:#defbe6;color:#0e6027">
  <svg data-lucide="check-circle" class="w-3 h-3"></svg> Settled
</span>
```

### 19.4 Avatars, KPI tiles, overlays

| Component | Key dimensions |
|---|---|
| **Avatar** | `24 / 32 / 40px`; circular; initials `12px/600` on `--interactive`; group overlap `-8px`, white 2px ring |
| **KPI tile** | padding `16px`; label `12px` `--text-secondary`; value `28px / 300` tabular; delta `12px / 500` + 16px arrow + semantic color |
| **Card** | 1px `--border-subtle`, radius `2px`, padding `24px` (`16px` dense), flat |
| **Modal** | max-width `440px` (sm) / `560px` (md); radius `8px`; `elevation-03`; scrim `rgba(0,0,0,.5)`; focus-trapped; Esc closes; returns focus |
| **Drawer** | width `min(420px, 100vw)`; slides from right `240ms` ease-productive-entrance; focus-trapped |
| **Dropdown menu** | min-width `208px`; item height `36px`; `elevation-02`; flips to stay in viewport |
| **Toast** | width `320px` (cap `100vw−2rem`); `elevation-02`; auto-dismiss `~3.2s`, pause on hover; `aria-live="polite"` |
| **Tooltip** | `12px` text, `8px×4px` pad, `--text-primary` bg / `--bg` text; `4px` offset; never the only source of essential info |

```html
<div class="card" style="padding:16px">
  <div class="text-[12px] txt-sec">Transactions / min</div>
  <div class="text-[28px] font-light tnum">14,208</div>
  <div class="text-[12px] font-medium" style="color:#24a148">▲ 8.2% vs prev</div>
</div>
```

---

## 20. Component State Matrix

Every interactive component must implement every applicable state (§9). "—" = not applicable.
✅ = required. This grid is the contract; a component missing a required state is incomplete.

| Component | Default | Hover | Focus | Active | Selected | Disabled | Loading | Error | Empty |
|---|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| Button | ✅ | ✅ | ✅ | ✅ | — | ✅ | ✅ | — | — |
| Link | ✅ | ✅ | ✅ | ✅ | — | ✅ | — | — | — |
| Text input | ✅ | ✅ | ✅ | — | — | ✅ | — | ✅ | — |
| Select / combobox | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Checkbox / radio | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | — | ✅ | — |
| Switch | ✅ | ✅ | ✅ | ✅ | ✅ (on) | ✅ | — | — | — |
| Nav item | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | — | — | — |
| Tab | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | — | — | — |
| Menu item | ✅ | ✅ | ✅ | ✅ | — | ✅ | — | — | — |
| Table row | ✅ | ✅ | ✅ | — | ✅ | — | ✅ | — | ✅ |
| Card / tile | ✅ | ✅* | ✅* | — | ✅* | — | ✅ | ✅ | ✅ |
| Data table (whole) | ✅ | — | — | — | — | — | ✅ | ✅ | ✅ |
| Chart / widget | ✅ | ✅ (tooltip) | — | — | — | — | ✅ | ✅ | ✅ |

\* only when the card is interactive (clickable/selectable). For tables, charts, and any
content surface, the **loading / error / empty** trio is mandatory — never ship the happy path
alone (§13, anti-pattern).

---

## 21. Keyboard Shortcuts

Global accelerators for power users (§ Flexibility & efficiency). All are discoverable in the
command palette, none are required to complete a task by mouse alone.

| Keys | Action | Scope |
|---|---|---|
| `⌘ K` / `Ctrl K` | Open command palette | Global |
| `/` | Focus global search | Global (when no field focused) |
| `Esc` | Close overlay / clear search / cancel inline edit | Any overlay |
| `?` | Open keyboard-shortcut help | Global |
| `g` then `d` | Go to Dashboard | Global (chord) |
| `g` then `t` | Go to Tables | Global (chord) |
| `Tab` / `Shift Tab` | Move focus forward / back | Always |
| `↑ ↓` | Move between list / menu / table-row items | List, menu, grid |
| `Home` / `End` | First / last item | List, menu, table |
| `Enter` | Activate / confirm inline edit | Focused control |
| `Space` | Toggle checkbox / switch / select row | Focused control |
| `⌘ Enter` | Submit form / primary action | Form, modal |
| `x` | Toggle row selection | Data table |
| `⌘ A` | Select all rows (when table focused) | Data table |

**Rules:** never override browser/OS shortcuts; show the chord hint in tooltips and menus
(`⌘K` badge); chords time out after 1s; respect that screen-reader users remap many keys —
shortcuts are additive, never the only path.

---

## 22. Internationalization & RTL

Enterprise software ships globally; localization is designed in, not patched on.

### 22.1 Text & layout
- **No concatenated strings.** Use whole, parameterized messages (`"{n} transactions settled"`)
  so translators control word order. Never build a sentence from fragments in code.
- **Allow for expansion.** German/Finnish run ~35% longer than English; labels, buttons, and
  nav must not truncate or wrap-break at default widths. Test with a pseudo-locale that pads
  strings +40%.
- **Pluralization** uses ICU plural rules (`zero/one/two/few/many/other`), not `if (n===1)`.
- **Never bake meaning into word order or hardcoded units.**

### 22.2 RTL (Arabic, Hebrew, Farsi, Urdu)
- Drive direction from `dir="rtl"` on `<html>`; build layouts with **logical properties**
  (`margin-inline-start`, `padding-inline-end`, `inset-inline-start`) — never physical
  `left/right` — so the UI mirrors automatically.
- **Mirror:** layout, nav, the side-nav side, breadcrumb chevrons, back/forward, progress, and
  directional icons (arrows, chevrons, "next").
- **Do not mirror:** media playback controls, clocks, and **numbers/charts** — quantitative
  axes stay left-to-right even in RTL; only the surrounding chrome flips. Logos and brand marks
  stay as-is.
- The `2px` selected-indicator on nav items moves to the inline-end edge in RTL.

### 22.3 Numbers, dates, currency
- Format via the platform locale layer (`Intl.NumberFormat` / `Intl.DateTimeFormat`), never by
  hand. Currency shows the ISO code where ambiguous (`US$` vs `$`).
- Keep **tabular numerals** for aligned columns in every locale.
- Dates are locale-ordered and timezone-explicit; relative time ("3 min ago") localizes too.

---

## 23. Governance, Versioning & Contribution

A design system is a living product; it needs an operating model, not just tokens.

### 23.1 Versioning (SemVer for the system)
- **MAJOR** — a breaking change: a removed/renamed token or component, or a visual change that
  alters layout/contract. Ships with a migration guide.
- **MINOR** — additive and backward-compatible: a new token, variant, or component.
- **PATCH** — a fix that doesn't change the API: a contrast correction, a bug, docs.
- The system version is single-sourced (the `v1.0` badge in the shell footer reflects it).

### 23.2 Token & component lifecycle
1. **Proposed** — an RFC with the problem, the use-cases it generalizes, and why existing
   tokens don't cover it. New tokens must be *roles*, not one-off values (§P5).
2. **Experimental** — shipped behind an `is-experimental` flag, documented as unstable.
3. **Stable** — promoted after ≥2 real consumers and an a11y + contrast audit.
4. **Deprecated** — kept working for **one MAJOR** with a console warning + documented
   replacement; removed only in the next MAJOR.

### 23.3 Contribution rules
- **Reference role tokens, never raw values** in any contribution (§14). A PR introducing a raw
  hex, off-grid spacing, or a one-off duration is rejected by definition.
- Every new/changed component ships with: all required states (§20), a Do/Don't note, contrast
  evidence, keyboard operability, and the §18 pre-ship checklist passing.
- **Single source of truth.** Design and engineering consume the same tokens; divergence is a
  bug. Prune unused tokens/components deliberately rather than letting them accrete.
- **Decision log.** Non-obvious choices are recorded (an ADR-style note) so later passes don't
  relitigate them — and so this document stays the reason, not just the result.

---

*Meridian Enterprise v1.0 — the line you navigate by. Build calm, build exact, build for the
people who run the business.*
