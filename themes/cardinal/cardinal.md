# Cardinal — Theme Design Specification

> **Version 1.0** · Revenue design system for sales-pipeline software · Daybook + After-hours editions
> Tagline: **"A dashboard is a revenue desk — read the number, then work the board."**

Most sales software buries the one number a revenue leader actually cares about — *are we going to
make the quarter?* — under a grid of equal-weight widgets. **Cardinal puts the money first.** It is
a design system for the revenue desk: pipeline, deals, forecast, and the accounts behind them,
built for the people who live in the number — VPs of Revenue, sales managers, and RevOps. The
signature is a **pipeline stage-board** that reads left-to-right like a deal flowing from Prospect
to Won, and **executive-scale figures** set in a confident display face. It is warm, deliberate,
and opinionated: cardinal red for the decisive action, deep teal for the steady one, on paper that
looks like a well-kept ledger — not a cold SaaS grid.

> **A distinct pole.** The gallery already ships **Meridian** (a flat Carbon instrument panel),
> **Broadsheet** (a flat editorial front page), **Frontline** (a tactile field/ops app), and
> **Vellum** (a premium, entry-first records studio). Cardinal is the **revenue-desk** pole:
> **executive**, **figure-forward**, and **board-driven**, with a warm two-edition palette built on
> cardinal red and deep teal. §2 maps the contrast.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Cardinal vs. the others](#2-cardinal-vs-the-others)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [The Pipeline Stage System](#5-the-pipeline-stage-system)
6. [Typography](#6-typography)
7. [Responsive Layout](#7-responsive-layout)
8. [Elevation, Radius & Surfaces](#8-elevation-radius--surfaces)
9. [Components & Patterns](#9-components--patterns)
10. [Motion](#10-motion)
11. [Accessibility](#11-accessibility)
12. [Tokens in Practice](#12-tokens-in-practice)
13. [Anti-Patterns Cardinal Forbids](#13-anti-patterns-cardinal-forbids)
14. [Pre-Ship Checklist](#14-pre-ship-checklist)

---

## 1. Design Principles

Six principles. When two conflict, the **earlier** wins.

### P1 — The money is the hero
Every screen has one figure that matters most — pipeline value, weighted forecast, ARR — and it is
the largest, boldest thing in view. Executive-scale numbers (28–48px, extra-bold, tabular) are the
first thing the eye lands on. Secondary detail is demoted, deferred, or set in mono at label size.
*If everything is a KPI tile, nothing is.*

### P2 — The pipeline is a board
A deal is not a row in a list; it is a thing that **moves through stages**. Cardinal's signature is
a stage-board that flows left → right (Prospect → Qualified → Proposal → Won), with each column
carrying its count, its value, and its top deals. The funnel is legible at a glance, not
reconstructed from a table.

### P3 — Stage is the system
The five pipeline stages (§5) are the semantic backbone. Each is a fixed pairing of **color +
label**, used identically in board columns, table cells, chips, the value-by-stage bar, and filter
chips. Color reports stage; it is never spent on decoration. Won is green, Lost is *neutralized*
(a warm gray, not an alarm) — losing a deal is data, not an error.

### P4 — Figures are typeset, prose is spoken
Money, percentages, dates, and IDs are set in a **tabular monospace** so columns align and decimals
line up down a table. Labels and prose are set in the display sans. The two never blur: a number
looks like a number, a sentence looks like a sentence.

### P5 — Warm, not clinical
Revenue work is human — negotiation, judgement, relationships. The surface is warm paper, not a
blue-gray dashboard; the ink is near-black brown; the accent is a considered cardinal red, not a
generic SaaS blue. The After-hours edition is warm walnut, not pure black. Premium comes from
restraint and warmth, not gradients and glow.

### P6 — Two editions, one desk
**Daybook** (light) is the trading floor by day; **After-hours** (dark) is the desk after the close
— for late pipeline reviews and low-light rooms. Both are first-class and derive from one token
set, so the switch is a single class on `<html>` and every chart, chip, and figure follows.

---

## 2. Cardinal vs. the others

| Axis | Meridian | Broadsheet | Frontline | Vellum | **Cardinal** |
| --- | --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | Records studio | **The revenue desk** |
| Domain | General enterprise | Data journalism | Field service | BI data entry | **Sales pipeline & forecast** |
| Organizing idea | Density | Editorial hierarchy | Operational status | Entry ergonomics | **Executive figures + a deal board** |
| Surface | Flat, boxed | Flat, ruled | Tactile, elevated | Soft sheets, hairlines | **Warm paper, elevated rounded cards** |
| Palette | Carbon gray | Tinted newsprint | Hi-vis + orange | Porcelain + iris | **Warm paper + cardinal red + teal** |
| Type | IBM Plex | Fraunces/Archivo | Saira + Martian | Hanken + JetBrains | **Sora + Azeret Mono** |
| Accent | Carbon blue | Claret | Safety orange | Iris `#4B45C7` | **Cardinal red `#B4232F`** |
| Signature concern | Governance | Provenance | Connectivity | Data-entry ergonomics | **Pipeline & forecasting** |
| Editions | White / Gray-100 | Day / Evening | Field / Shift | Light only | **Daybook / After-hours** |

Use Cardinal for CRM, sales pipeline, revenue intelligence, forecasting, and any product whose home
screen answers *"where's the number, and where's it coming from?"*

---

## 3. Brand & Voice

Cardinal sounds like a sharp VP of Revenue on a Monday call: **decisive, numerate, and unhurried.**
It names things the way the desk does — "pipeline", "stage", "commit", "best case", "closed-won",
"weighted forecast" — never system jargon. Figures are stated plainly and precisely ("$4.82M",
"28% win rate", "+12.4% vs last quarter"). Feedback is short and factual ("Northwind Traders moved
to Proposal", "Created deal · Harbor Freight Depot"). No hype, no confetti except where a deal is
genuinely won. The brand mark is a single cardinal-red block — one confident stroke, like the desk
itself.

---

## 4. Color System

Two editions, one token set. **Daybook** (light) is tuned for warm daylight; **After-hours** (dark)
is a warm walnut desk for late reviews. Every value is a role token, so the swap is a single class
on `<html>`.

### Daybook edition (light)

| Role | Token | Value |
| --- | --- | --- |
| App background (paper) | `--canvas` | `#FAF8F5` |
| Surface (cards, chrome) | `--surface` | `#FFFFFF` |
| Inset surface | `--surface-2` | `#F6F2EC` |
| Hairline (cards) | `--line` | `#ECE6DD` |
| Structural separator (chrome) | `--line-2` | `#DAD1C4` |
| Primary text | `--ink` | `#1A140E` |
| Secondary text | `--ink-2` | `#6B5F52` |
| Caption | `--ink-3` | `#9E9385` |
| Accent — fill (cardinal red) | `--accent` | `#B4232F` |
| Accent — text/icon on tint | `--accent-ink` | `#A81E2A` |
| Accent — soft tint | `--accent-soft` | `#F7E4E4` |
| Secondary accent (deep teal) | `--teal` | `#0F766E` |
| Positive / Warning | `--pos` / `--warn` | `#157347` / `#9A6410` |

### After-hours edition (dark)

Warm walnut, not pure black: `--canvas #14100C`, `--surface #1E1813`, `--surface-2 #262019`,
hairlines `#322A22` / separators `#453A2E`, `--ink #F3ECE2`. The brand splits so both jobs stay
legible: `--accent #C22F3A` keeps white button text at AA, while `--accent-ink #F1868D` is a
brightened rose for text/icons on dark and tinted surfaces. Teal lifts to `#35C2B1`.

**Rules of use.** Cardinal red is the brand and the *one* primary action — decisive, never a
highlighter. A **dedicated structural separator** (`--line-2`, a touch stronger than card
hairlines) draws the app chrome — the sidebar edge and top bar — so the layout reads clearly; card
borders stay on the lighter `--line`. The accent splits into a **fill** token (`--accent`, always
carries white text at AA) and an **ink** token (`--accent-ink`, for text/icons on tints and on
dark). Stage colors (§5) are reserved for pipeline state.

---

## 5. The Pipeline Stage System

The heart of the system. Five pipeline stages, each a fixed pairing of **color + label**, used
identically in the board, table stage-cells, filter chips, and the value-by-stage bar chart.

| Stage | Token | Daybook | After-hours | Meaning |
| --- | --- | --- | --- | --- |
| Prospect | `--st-prospect` | `#52627D` | `#8FA2C0` | Identified, not yet qualified |
| Qualified | `--st-qualified` | `#0F766E` | `#35C2B1` | Fit confirmed, worth pursuing |
| Proposal | `--st-proposal` | `#935B08` | `#DFA33C` | Offer on the table |
| Won | `--st-won` | `#157347` | `#46C878` | Closed-won |
| Lost | `--st-lost` | `#7A6E5F` | `#A99B88` | Closed-lost — neutralized, not alarmed |

Stage is **never carried by color alone** — the label always travels with it. Chips render the
stage color as text over a low-alpha tint of the *same* color mixed into the surface
(`color-mix(… stage 15%, var(--surface))`), so the pairing is edition-correct in both Daybook and
After-hours while holding AA contrast. A second, smaller **account-health** set (Healthy / Watch /
At risk → `--pos` / `--warn` / `--neg`) uses the identical chip mechanics on the Accounts page.

---

## 6. Typography

Two typefaces, chosen for a modern, executive confidence — geometric enough to feel premium, humane
enough to read all day.

| Role | Typeface | Used for |
| --- | --- | --- |
| UI / display | **Sora** | Headings, executive figures, labels, buttons; its geometric character gives the big numbers presence |
| Figures / codes | **Azeret Mono** | Money, percentages, dates, IDs, table numbers, small-caps labels |

- **Sora** carries the personality: extra-bold (800) for the hero figures, semibold for headings,
  regular for body. The big numbers are the brand's voice — set them large (28–48px), tight, tabular.
- **Azeret Mono** gives tabular alignment and an instrument feel to every figure and identifier, and
  sets the tracked, uppercase micro-labels (`.lbl`) that title each module.
- Hierarchy is by **size and weight first**, color second — a screen should be scannable in a glance
  before a single word is read.

---

## 7. Responsive Layout

One app shell, two shapes — driven by breakpoints, not a separate build.

- **Desktop (≥ 1024px):** persistent left **sidebar** + sticky **top bar** + fluid content. The
  dashboard is a multi-column grid: KPI tiles → the pipeline board → charts → tables.
- **Tablet (≥ 640px):** grids relax to two columns; the board and tables scroll horizontally within
  their cards; the sidebar persists.
- **Phone (< 1024px):** the sidebar becomes a **left nav drawer** behind a hamburger; content stacks
  to one column; KPI tiles go two-up; the board scrolls sideways; primary actions stay reachable.
  Targets ≥ 44px.

The same tokens, components, and stage system render in both — only the arrangement changes. A phone
mock floating in a desktop window is a failure, not a feature.

## 8. Elevation, Radius & Surfaces

Cardinal is **softly elevated** — enough depth to feel premium and physical, never heavy.

- **Three shadow levels:** `--shadow-sm` for resting cards, `--shadow-md` for hovers, `--shadow-lg`
  for overlays (drawer, modal, toasts) that lift clearly above the page.
- **Radius:** `--radius` 14px for cards and surfaces, `--radius-sm` 9px for controls, pill (999px)
  for chips and toggles. Rounded enough to feel considered, not playful.
- **Surfaces:** three warm levels — `--canvas` (paper page) → `--surface` (cards & chrome) →
  `--surface-2` (insets, fields, board columns, table zebra). Structural separators (`--line-2`)
  define the chrome; card hairlines (`--line`) sit a step lighter.

## 9. Components & Patterns

- **Executive KPI tile** — micro-label + oversized tabular figure + trend delta + inline sparkline.
- **Pipeline stage-board** *(signature)* — five flowing columns; each carries stage chip, count,
  total value, a value-share bar, and its top deals; a deal chip opens the edit drawer.
- **Charts** — area (bookings vs target), bar (value by stage), doughnut (pipeline by region), a
  cumulative forecast-vs-quota line, and KPI sparklines — all styled to the edition and re-rendered
  on edition swap and on tab activation (hidden canvases guarded via `offsetParent === null`).
- **Data table** — small-caps mono headers with **clickable sort**, stage cells, zebra + hover,
  responsive horizontal scroll, an **inline-editable stage `<select>`**, and a **click-to-edit
  amount** cell that swaps to a numeric input with Enter/Esc/blur.
- **Edit drawer (right)** — open a deal, edit account, stage, owner, amount, close date, and a
  probability slider in place; Save/Cancel.
- **Nav drawer (left)** — the mobile navigation surface behind a hamburger.
- **Modal** — centered "New deal" dialog with scrim and Esc-to-close; Create adds a row and fires a
  toast.
- **Inline edit** — a click-to-edit profile name and the click-to-edit table amount (two distinct
  patterns), plus the inline stage select.
- **Inputs** — text, search, select, textarea, toggle switch (`role="switch"`), segmented control,
  stepper (+/−), filter chips, range slider, and inline numeric fields — all keyboard-usable with a
  2px accent focus ring.
- **Account card**, **activity timeline**, **task checklist**, **status/health chip**, and **toast**.

## 10. Motion

Motion is functional and quick (**120–280ms**, standard ease): a press-nudge on the primary button,
a slide-in for the drawer, a fade-scale for the modal, and a soft rise for toasts. It confirms an
action landed and shows where a surface came from — never decorative. `prefers-reduced-motion` is
honored (all animation/transition collapses to near-instant), and chart animations stay short so a
figure the reader needs is never gated behind a reveal.

## 11. Accessibility

- **AA on real surfaces, both editions** — body, label, figure, and stage-chip text clear WCAG 2.1
  AA on their actual tinted backgrounds in **Daybook and After-hours**; the accent splits into fill
  vs. ink tokens precisely so red never fails on a dark surface.
- **Never color-only** — every stage and health state pairs color with a text label.
- **Keyboard-first** — a 2px accent focus ring on every interactive element; overlays close on Esc;
  toggles use `role="switch"` with `aria-checked`; icon-only buttons carry `aria-label`.
- **Touch** — targets ≥ 44px; steppers, chips, and nav are comfortably tappable.
- **Live feedback** — toasts render in an `aria-live="polite"` region so changes are announced.
- **Honest states** — empty (filtered-to-nothing), zebra tables, and success confirmations are all
  designed, not just the happy path.

## 12. Tokens in Practice

Light under `:root`, dark under `html.dark`; the Daybook → After-hours edition is one class swap:

```css
:root     { --canvas:#FAF8F5; --surface:#FFFFFF; --ink:#1A140E; --accent:#B4232F;
            --accent-ink:#A81E2A; --line:#ECE6DD; --line-2:#DAD1C4; /* … Daybook */ }
html.dark { --canvas:#14100C; --surface:#1E1813; --ink:#F3ECE2; --accent:#C22F3A;
            --accent-ink:#F1868D; --line:#322A22; --line-2:#453A2E; /* … After-hours */ }
```

Stage colors are tokens too (`--st-prospect … --st-lost`), so a board column, a table cell, a
filter chip, and a chart bar all read the same source. Chips derive their fill from that one token
with `color-mix`, so there is no second palette to keep in sync. No raw hex in components, no magic
spacing, no one-off durations.

> **Note — chrome separators.** The app chrome (sidebar edge, top bar) is drawn with `--line-2` via
> a CSS class (`.sidebar`, `.topbar`), a step stronger than card `--line`. Keep structural borders
> in classes, not in framework-bound inline `:style`, so a dynamic binding can't clobber them.

## 13. Anti-Patterns Cardinal Forbids

- ❌ **A wall of equal-weight KPI tiles** with no hero figure — kills the glance layer (P1).
- ❌ **A pipeline shown only as a table** — the board is the point (P2).
- ❌ **Color-only stage** with no label, or **Lost styled as an alarm** — losing is data, not error.
- ❌ **Cardinal red as decoration** — it is the brand and the one primary action.
- ❌ **A cold blue-gray SaaS grid** — Cardinal is warm paper and warm walnut.
- ❌ **Proportional figures in tables** — money and percentages are tabular mono, right-aligned.
- ❌ **A phone mock floating in a desktop window** — the demo must be a real responsive layout.
- ❌ **Red text on a dark surface below AA** — use the `--accent-ink` token, never the fill token.

## 14. Pre-Ship Checklist

- [ ] One hero figure per screen; executive numbers are the focal point.
- [ ] The pipeline board reads Prospect → Won at a glance, with counts and values.
- [ ] Every nav item routes to a real, populated page (Overview, Deals, Accounts, Forecast,
      Activities, Settings).
- [ ] BI dashboard: KPI tiles, area + bar + doughnut charts, and a data table.
- [ ] Stage system consistent (color + label) across board, table, chips, and charts.
- [ ] Inline edits work (stage select + click-to-edit amount + click-to-edit name); edit drawer,
      nav drawer, and "New deal" modal all function; create adds a row + toast.
- [ ] Full input range present (text, search, select, textarea, toggle, segmented, stepper, chips,
      slider, inline numeric), all keyboard-usable with visible focus.
- [ ] Targets ≥ 44px; never color-only; AA contrast in Daybook **and** After-hours.
- [ ] Both editions polished; charts and chips re-render on swap; hidden canvases guarded.
- [ ] `prefers-reduced-motion` respected; chrome separators use a class-based `--line-2`.

---

> **Colophon.** Set in Sora and Azeret Mono. Cardinal is one theme in the
> [`my-themes`](../../README.md) gallery — the warm, figure-forward, revenue-desk counterpart to the
> instrument panel, the front page, the field app, and the records studio.
