# Vellum — Theme Design Specification

> **Version 1.0** · A premium design system for BI apps built around data entry · Single light edition
> Tagline: **"The record is the hero."**

Most "data apps" treat entry as a chore bolted onto a dashboard — a cramped modal, a wall of gray
inputs, a Save button you hope worked. **Vellum inverts that.** It is a premium design system for
business software where *entering* data is a first-class craft and *reading* it back is a pleasure:
a records studio where every field is a satisfying thing to fill and every figure is typeset, not
just printed. Warm porcelain paper, deep **iris ink**, generous whitespace, and one restrained
jewel accent — the calm, expensive feel of a well-kept ledger, wired to real BI.

> **A fourth pole.** This repository already ships **Meridian Enterprise** (a flat Carbon
> instrument panel), **Broadsheet** (a flat editorial front page), and **Frontline** (a tactile,
> hi-vis field app). Vellum is the deliberate fourth pole: **premium and quiet** (restraint, not
> density or hi-vis), **entry-first** (the sheet is a page, not a dialog), and **single-light by
> design** — a calm luxury surface rather than a working console. §2 maps the contrast.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Vellum vs. the others](#2-vellum-vs-the-others)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [The Records Pipeline (status system)](#5-the-records-pipeline-status-system)
6. [Typography](#6-typography)
7. [Layout & Responsive Behavior](#7-layout--responsive-behavior)
8. [Elevation, Radius & Surfaces](#8-elevation-radius--surfaces)
9. [Components & Patterns](#9-components--patterns)
10. [Data-Entry Ergonomics (the Entry Sheet)](#10-data-entry-ergonomics-the-entry-sheet)
11. [Motion](#11-motion)
12. [Accessibility](#12-accessibility)
13. [Tokens in Practice](#13-tokens-in-practice)
14. [Anti-Patterns Vellum Forbids](#14-anti-patterns-vellum-forbids)
15. [Pre-Ship Checklist](#15-pre-ship-checklist)

---

## 1. Design Principles

Seven principles. When two conflict, the **earlier** wins.

### P1 — The record is the hero
Data entry is the primary craft, not an afterthought. The **entry sheet is a full page** — a
sectioned surface with a live summary rail — not a cramped modal. Every input is generously sized,
clearly labelled, and pleasant to fill. If capturing a record feels like friction, the design has
failed at its one job.

### P2 — Premium is what you leave out
Restraint carries the luxury. Whitespace, hairlines, tabular figures, and **one** jewel accent do
the work; there are no gradients-for-decoration, no competing colors, no chartjunk. The interface
should feel considered and expensive because almost nothing on screen is unnecessary.

### P3 — A pipeline you can read
Every record has a lifecycle — **Draft → In review → Approved → Posted**, plus **Flagged** — and
that state is the spine of the product (§5). Color + label always travel together and mean the
same thing in a chip, a table cell, a review card, and the dashboard doughnut. Color reports
state; it is never spent on decoration.

### P4 — Numbers are typeset, not just printed
Money and metrics are set in a **tabular monospace**, right-aligned, decimals aligned, so any two
figures compare at a glance. Identifiers, dates, and codes share that instrument voice. A ledger
that you can't scan column-down isn't a ledger.

### P5 — Enter, then read — one system, both directions
Vellum is symmetrical: **excellent data entry *and* excellent BI on the same tokens.** The ledger
you write into is the ledger you chart. Dashboards, tables, forms, and the review queue are all
built from one type scale, one palette, one status system — so moving between capturing and
analysing never feels like two different apps.

### P6 — Calm, not clinical
Warm porcelain paper and iris ink give the system warmth; it is premium and human, not a cold gray
enterprise dashboard. Density is deliberate and breathable — the answer is easy to find because the
page isn't shouting ten things at once.

### P7 — Light by design, token by construction
Vellum ships a **single, deliberate light edition** — a calm, paper-like surface, chosen over a
dark mode rather than lacking one. Yet every visual value still resolves to a CSS custom property,
so the system stays fully themeable and a future edition would be a token swap, not a rewrite.

---

## 2. Vellum vs. the others

| Axis | Meridian | Broadsheet | Frontline | **Vellum** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **Records studio (a premium ledger)** |
| Primary device | Desktop | Desktop | Phone *and* desktop | **Desktop-first, fully responsive** |
| Surface treatment | Flat, boxed | Flat, ruled | Tactile, elevated | **Soft sheets, hairline dividers, whisper shadow** |
| Palette | Cool Carbon gray | Tinted newsprint | Hi-vis concrete | **Warm porcelain + iris ink** |
| Type | IBM Plex Sans/Mono | Fraunces/Archivo/Spline | Saira + Martian Mono | **Hanken Grotesk + JetBrains Mono** |
| Accent | Carbon blue | Claret | Safety orange | **Iris `#4B45C7`** |
| Organizing idea | Density | Editorial hierarchy | Operational status | **Data entry as craft + a legible pipeline** |
| Signature concern | Governance | Provenance | Connectivity / offline | **Entry ergonomics & premium restraint** |
| Modes | White / Gray-100 | Day / Evening | Field / Shift | **Light only (by design)** |

Use Vellum for spend & expense management, invoicing and AP/AR, CRM and records systems, admin
consoles, internal tools — anywhere people **enter** structured data all day and **read** it back
as BI, and where the product is meant to feel premium.

---

## 3. Brand & Voice

Vellum sounds like a precise, unhurried studio: **clear, quietly confident, never loud.** Plain
record nouns ("record", "vendor", "split", "memo"), calm imperatives ("Submit for review", "Save
as draft", "Approve"), and honest, specific states ("Splits don't match the total — off by
$40.00", "All caught up"). No exclamation marks, no hype, no filler. The mark is a single
iris-inked tile — a **V** set in the display sans — restrained and premium, the way good stationery
is.

---

## 4. Color System

**One deliberate light edition.** The palette is a warm near-neutral "porcelain" with a single
cool jewel accent — iris — so the composition reads like fountain-pen ink on fine paper. Every
value is a role token, so a theme change is a single edit at the source, never a component rewrite.

### Neutrals (porcelain)

| Role | Token | Value |
| --- | --- | --- |
| App background (porcelain) | `--canvas` | `#F1EFEA` |
| Surface (sheets, cards, chrome) | `--surface` | `#FFFFFF` |
| Inset surface | `--surface-2` | `#F7F6F2` |
| Deep inset / track | `--surface-3` | `#EFEDE7` |
| Primary text (ink) | `--ink` | `#211E1A` |
| Secondary text | `--ink-2` | `#5D584F` |
| Caption / label | `--ink-3` | `#948E83` |
| Hairline (cards, dividers) | `--line` | `#E7E3DA` |
| Structural separator (chrome) | `--line-2` | `#D6D0C4` |

### Accent (iris ink) & semantics

| Role | Token | Value |
| --- | --- | --- |
| Accent (iris) | `--accent` | `#4B45C7` |
| Accent pressed | `--accent-press` | `#3B3699` |
| Accent text-on-tint | `--accent-ink` | `#3A3596` |
| Accent tint | `--accent-soft` | `#ECEBFA` |
| Positive | `--pos` / `--pos-ink` | `#1E8A5A` / `#146C46` |
| Negative | `--neg` / `--neg-ink` | `#C63A45` / `#A62B35` |
| Warning | `--warn` | `#B26A0E` |

**Rules of use.** Iris is the brand and the primary action — used decisively (the primary button,
the active nav, the sparkline, the key data series) but never sprayed around. **Green / red / amber
are reserved for data semantics** (up/down, positive/negative, over-budget, off-balance) so the
accent never has to double as "good" or "bad". A **dedicated structural separator** (`--line-2`, a
touch stronger than card hairlines) draws the app chrome — the sidebar edge and top bar — so the
layout reads clearly; card and row hairlines stay on the lighter `--line`. Each semantic color
carries a darker `*-ink` variant for text on its own tint, keeping AA contrast.

## 5. The Records Pipeline (status system)

The spine of the product. Five lifecycle states, each a fixed pair of **color + label**, used
identically in filter chips, table status cells, review cards, and the dashboard "Records by
status" doughnut.

| State | Token | Value | Meaning |
| --- | --- | --- | --- |
| Draft | `--s-draft` | `#8A8579` | Captured, not yet submitted |
| In review | `--s-review` | `#3A6DD6` | Submitted, awaiting approval |
| Approved | `--s-approved` | `#1E8A5A` | Cleared by an approver |
| Posted | `--s-posted` | `#4B45C7` | Committed to the ledger (final) |
| Flagged | `--s-flagged` | `#C63A45` | Needs attention / correction |

Status is **never carried by color alone** — the label always accompanies it. Chips tint the state
color at low alpha for the fill and use the full-strength color for the dot and text. The order is
meaningful (it is the lifecycle), and the same `statusOrder` drives the filter chips, the doughnut
slices, and the legend so counts always reconcile.

## 6. Typography

Two typefaces: a premium humanist grotesque for everything human-readable, and a precise monospace
for everything countable.

| Role | Typeface | Used for |
| --- | --- | --- |
| UI / display | **Hanken Grotesk** (400–800) | Headings, body, labels, buttons, big KPI figures (heavy weight, tight tracking) |
| Figures / codes | **JetBrains Mono** (400–600) | Amounts, record IDs, dates, table numbers, micro-labels/eyebrows |

- **Hanken Grotesk** is warm, modern, and expensive-feeling without being trendy — distinct from
  the gallery's IBM Plex, Fraunces/Archivo, and Saira voices. Big numbers use the 800 weight with
  `-0.02em` tracking and tabular figures (the `.num` role) for a confident, premium headline number.
- **JetBrains Mono** gives tabular alignment to money and identifiers, and — set small, uppercase,
  wide-tracked — becomes the system's **eyebrow / micro-label** (`.lbl`), a signature of the look.
- Hierarchy is by size and weight on a calm scale; body is a comfortable 14px with 1.5 line-height.
  The type does the structural work so borders and color can stay minimal.

## 7. Layout & Responsive Behavior

One app shell, reflowing by breakpoint — never a separate mobile build.

- **Desktop (≥ 1024px):** persistent left **sidebar** (collapsible to icons, with a period-budget
  card) + a sticky, subtly-blurred **top bar** + fluid content. The dashboard is a multi-column
  grid; the entry page is a two-column **sheet + summary rail**.
- **Tablet (≥ 640px):** grids relax to two columns; tables keep priority columns and scroll
  horizontally; the sidebar persists.
- **Phone (< 1024px):** the sidebar becomes a **left nav drawer** behind a hamburger; content
  stacks to one column; the entry sheet's summary rail drops below the sheet; tables scroll. Touch
  targets ≥ 44px. A hairline **iris keyline** rides the very top edge on every size.

The same tokens, components, and status system render at every width — only the arrangement changes.

## 8. Elevation, Radius & Surfaces

Vellum is **soft, not tactile** — depth is a whisper that separates a sheet from the paper, not a
lift that says "press me."

- **Two-level elevation:** `--shadow` — a barely-there resting shadow — for sheets and cards;
  `--shadow-lg` for overlays (drawer, modal, toast) that lift clearly above the page.
- **Radius:** `--r` 12px for sheets/cards, `--r-sm` 10px for controls, `--r-xs` 8px for chips/insets,
  pill (99px) for status chips, filter chips, and toggles. Rounded enough to feel refined, never
  playful.
- **Surfaces:** four calm levels — `--canvas` (porcelain page) → `--surface` (white sheets & chrome)
  → `--surface-2` (insets, ghost buttons) → `--surface-3` (progress tracks, deep insets). Inputs
  sit on white with a hairline; focus is a 3px iris **ring** (soft), not a heavy outline.

## 9. Components & Patterns

- **KPI tile** — mono eyebrow + oversized `.num` figure + a semantic delta and a tiny CSS
  **sparkline** (or an inline progress bar for ratios); the dashboard's glance layer.
- **Charts** — area/line (spend trend, iris gradient), horizontal bar (by category), doughnut
  (status mix), grouped line (budget vs actual), and a utilization bar column — all Chart.js, drawn
  in the palette and **re-rendered on tab activation** (hidden canvases are guarded via
  `offsetParent`).
- **Data table** — sticky mono small-caps header, tabular figures, hover rows, responsive scroll;
  an **inline-editable status `<select>`** (color reflects the state) and a **click-to-edit amount**
  cell that both update the row optimistically.
- **The Entry Sheet** — the signature surface (§10).
- **Review queue** — approval cards with record detail, quoted memo, amount, and inline
  **Approve / Flag** actions; an **"All caught up"** empty state when the queue clears.
- **Edit drawer (right)** — open a record, edit its fields in place, Save/Cancel.
- **Nav drawer (left)** — the mobile navigation surface behind a hamburger.
- **Modal** — a centered **quick-capture** dialog with scrim and Esc-to-close.
- **Inputs** — text, search (with datalist suggestions), select, textarea, toggle/switch, segmented
  control, **stepper** (+/−) with quick-add chips, filter chips, and inline-editable numeric fields
  — all keyboard-usable with a visible iris focus ring.
- **Status chip**, **toast** (action feedback), a **density toggle** (comfortable ↔ compact rows,
  a real setting), and a **collapsible sidebar**.

## 10. Data-Entry Ergonomics (the Entry Sheet)

Vellum's signature concern — the thing it does that the other three themes don't.

- **Entry is a page, not a dialog.** The New Entry route is a full **sheet**: a titled surface
  divided by hairlines into legible sections — *Record details*, *Amount*, *Split allocation*,
  *Notes & flags* — beside a **live summary rail**. Capturing a record is a considered task with
  room to breathe, not a scramble inside a 480px modal.
- **The number is the moment.** The amount field is oversized, right-aligned, monospace, with
  **steppers** and **quick-add chips** (+50 / +100 / +500 / +1000) for fast, low-error capture.
- **Show the math as it happens.** The summary rail mirrors the record live and warns when **splits
  don't reconcile to the total** ("off by $40.00") — validation as gentle guidance, in place,
  before submit, never a post-hoc error wall.
- **Two honest exits.** Every capture offers **Submit for review** (into the pipeline) and **Save
  as draft** — the lifecycle is respected from the first keystroke.
- **A quick path too.** For speed there's a **quick-capture modal** (vendor, category, department,
  amount) that drops a Draft into the ledger — the sheet is the craft surface, the modal is the
  shortcut, and both write the same record.
- **Every field is reachable and labelled.** Real `<label>`s, datalist suggestions on vendor,
  segmented controls for small enumerations, selectable tag chips — touch-sized, keyboard-usable,
  with a visible focus ring.

## 11. Motion

Motion is quiet and quick (**120–200ms**, standard ease): a soft press on buttons, the drawer
slide, the modal fade-scale, the toast in/out, the sidebar collapse, and a single fill on progress
bars. It confirms an action landed and shows where a surface came from. Forbidden: decorative
loops, long entrances, parallax, and number count-ups that delay a figure the user wants to read
now.

## 12. Accessibility

- **AA on the actual surfaces** — body, labels, and status text clear WCAG 2.1 AA on porcelain,
  white, and tinted chip backgrounds; each semantic color has a darker `*-ink` for text on its tint.
- **Never color-only** — status always pairs color with a label; deltas pair color with a ▲/▼ and a
  number.
- **Visible focus** — a 3px iris focus ring / 2px outline on every interactive element; full
  keyboard operability; logical order; nav items are keyboard-activatable.
- **Touch-friendly** — targets ≥ 44px; large hit areas on steppers, chips, and toggles; no
  hover-only affordances.
- **Honest states** — loading, empty ("No records match", "All caught up"), and success (toasts)
  are all designed, not left to chance.

## 13. Tokens in Practice

Everything resolves to a CSS custom property under `:root`. There is one edition by design, but
the construction is edition-ready — a future theme is a second selector, not a refactor:

```css
:root{
  --canvas:#F1EFEA; --surface:#FFFFFF; --surface-2:#F7F6F2; --surface-3:#EFEDE7;
  --ink:#211E1A; --ink-2:#5D584F; --ink-3:#948E83;
  --line:#E7E3DA; --line-2:#D6D0C4;
  --accent:#4B45C7; --accent-press:#3B3699; --accent-ink:#3A3596; --accent-soft:#ECEBFA;
  --pos:#1E8A5A; --neg:#C63A45; --warn:#B26A0E;
  --s-draft:#8A8579; --s-review:#3A6DD6; --s-approved:#1E8A5A; --s-posted:#4B45C7; --s-flagged:#C63A45;
  --r:12px; --r-sm:10px; --r-xs:8px;
}
```

The five pipeline colors are tokens too, so a chip, a table cell, a review card, and a chart slice
all read the same source. No raw hex in components, no magic spacing, no one-off durations.

> **Note — chrome separators.** App chrome (sidebar edge, top bar) uses `--line-2`, applied via a
> CSS class, *not* an inline style. Binding layout width with a framework's dynamic `:style` while
> also setting borders inline can clobber the border — keep structural styling in classes.

> **Note — icons + framework attributes.** Icon libraries that copy an element's attributes onto
> the generated SVG will choke on framework event bindings (e.g. Alpine's `@click`) placed directly
> on the icon node. Keep event handlers on a wrapping element, and guard the icon-render call so a
> stray attribute can never abort the rest of the boot (charts included).

## 14. Anti-Patterns Vellum Forbids

- ❌ **Entry crammed into a modal** as the primary path — the sheet is a page.
- ❌ **A dashboard that can't be typed into** — read-only BI with no first-class capture.
- ❌ **Accent overload** — iris is the action and the key series, not a highlighter; keep green/red/amber for meaning.
- ❌ **Proportional figures in tables** — money and IDs are tabular monospace, aligned.
- ❌ **Color-only status or deltas** with no label / arrow.
- ❌ **Decorative gradients, chartjunk, and busy borders** — restraint is the brand.
- ❌ **A phone mock floating in a desktop window** — the demo is a real responsive layout.
- ❌ **Post-hoc error walls** where in-place, as-you-type validation would guide instead.

## 15. Pre-Ship Checklist

- [ ] The **entry sheet is a full page** with a live summary rail; splits reconcile with an in-place warning.
- [ ] Every nav item routes to a real, populated page (Overview, Records, New Entry, Review, Analytics, Settings).
- [ ] BI on **two** surfaces: KPI tiles + line/area, bar, and doughnut charts, plus tables; charts re-render on tab activation.
- [ ] Pipeline status consistent (color + label) across chips, table cells, review cards, and the doughnut.
- [ ] Inline edits work: an editable table **amount** cell and an inline status **select**, plus a click-to-edit name in Settings.
- [ ] Edit drawer, mobile nav drawer, quick-capture modal, and toasts all work.
- [ ] Money and identifiers are tabular monospace; deltas carry an arrow + number, never color alone.
- [ ] Excellent on desktop **and** phone; reflows at ~375 / ~768 / ≥1280px; no phone-in-a-window.
- [ ] AA contrast on porcelain, white, and tinted surfaces; visible iris focus; targets ≥ 44px.
- [ ] Chrome separators use a class-based `--line-2`; the icon-render call is guarded.

---

> **Colophon.** Set in Hanken Grotesk and JetBrains Mono; iris ink on porcelain. Vellum is one
> theme in the [`my-themes`](../../README.md) gallery — the premium, entry-first, single-light
> counterpart to the flat desktop systems Meridian and Broadsheet and the tactile field app
> Frontline.
