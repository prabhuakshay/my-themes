# Tessera — Theme Design Specification

> **Version 1.0** · Modular, tile-driven design system for procurement & inventory · Floor + Nightshift editions
> Tagline: **"The warehouse mosaic — every SKU in its place."**

Most inventory software is a wall of tables. **Tessera treats the console like a warehouse: a grid of
tiles, each one a bin with a known place, a known count, and a known state.** It is a design system for
the people who move stock and cut purchase orders — buyers, warehouse leads, planners, and the managers
watching fill rate and turns from a desk. The organizing idea is the **tessera**: a single tile in a
mosaic. Every KPI, every SKU, every PO occupies a discrete, legible cell in a modular grid. The surface
is **true-neutral zinc** so the data does the talking, and a **single cobalt accent** marks the one path
forward on any screen. Two editions — **Floor** (light, for the daylight warehouse) and **Nightshift**
(dark, for dim docks and late planning) — resolve from one token set.

> **A distinct pole.** This repository ships **Meridian** (a Carbon instrument panel), **Broadsheet**
> (an editorial front page), and **Frontline** (a tactile field-ops app). Tessera is the **modular
> procurement pole**: not an instrument, not a newspaper, not a phone-first field tool, but a
> **tiled mosaic of stock** — neutral, grid-driven, and figure-dense. §2 maps the contrast.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Tessera vs. the others](#2-tessera-vs-the-others)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [The Status Systems — Stock & PO](#5-the-status-systems--stock--po)
6. [Typography](#6-typography)
7. [Responsive Layout](#7-responsive-layout)
8. [Elevation, Radius & Surfaces](#8-elevation-radius--surfaces)
9. [Components & Patterns](#9-components--patterns)
10. [The Mosaic — the signature](#10-the-mosaic--the-signature)
11. [Motion](#11-motion)
12. [Accessibility](#12-accessibility)
13. [Tokens in Practice](#13-tokens-in-practice)
14. [Anti-Patterns Tessera Forbids](#14-anti-patterns-tessera-forbids)
15. [Pre-Ship Checklist](#15-pre-ship-checklist)

---

## 1. Design Principles

Six principles. When two conflict, the **earlier** wins.

### P1 — Everything is a tile
The mosaic is the layout. KPIs, charts, alerts, and records each sit in a discrete, self-contained cell
with consistent padding and radius. A bento grid on the dashboard, card mosaics for suppliers, and evenly
gridded tables everywhere else. Nothing floats; everything has a place. *If it can't be a tile, it
probably doesn't belong on the screen.*

### P2 — True-neutral, so the data is the color
The surface is a **zinc grayscale with no temperature** — not warm, not cool. Neutral chrome keeps
attention on the numbers and the status colors. The only hue with a job in the layout is the single
**cobalt** accent. Saturated color is spent exclusively on state (§5), never on decoration.

### P3 — One accent, one path forward
Cobalt marks the primary action and the active location — the New PO button, the current nav item, the
selected control, the chart's lead series. Because there is only ever one accent, the eye always knows
where the next click is. Two competing primaries is a bug.

### P4 — Figures are first-class
Procurement runs on numbers: counts, reorder points, values, lead times, turns. Every figure is set in a
**monospace** with tabular alignment so columns line up, deltas are scannable, and a stockout reads as a
hard zero. Numbers never wobble between rows.

### P5 — Status is a fixed vocabulary
A SKU is *in stock / low / backordered / out*; a PO is *draft / sent / partial / received / cancelled*.
Each state is a fixed pairing of **color + label** used identically in chips, table cells, drawers, and
charts. Color never travels without its word (§5, §12).

### P6 — Edit in place, confirm with feedback
The list is the workspace. Adjust a stock count with a stepper, change a state from a table `<select>`,
click a reorder point to edit it, open a record in a right-hand drawer — all without leaving the page.
Every change returns an immediate toast. The worker stays in flow.

---

## 2. Tessera vs. the others

| Axis | Meridian | Broadsheet | Frontline | **Tessera** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **Warehouse mosaic** |
| Domain | Governance / BI | Enterprise data | Field service | **Procurement & inventory** |
| Structure | Boxed 2px grid | Hairline columns | Elevated cards | **Modular tile bento** |
| Surface | Cool gray | Tinted newsprint | Hi-vis concrete | **True-neutral zinc** |
| Type | IBM Plex Sans/Mono | Fraunces/Archivo | Saira/Martian | **Familjen Grotesk + Geist Mono** |
| Accent | Carbon blue | Claret | Safety orange | **Cobalt `#2563EB`** |
| Organizing idea | Density | Editorial hierarchy | Status + glance | **Tiles + figures** |
| Signature | Governance rails | Provenance | Connectivity | **The mosaic grid** |
| Editions | White / Gray-100 | Day / Evening | Field / Shift | **Floor / Nightshift** |

Use Tessera for procurement, inventory, warehouse management, supply-chain planning, catalog and SKU
tooling — anywhere the job is counting stock and cutting orders across many discrete items.

---

## 3. Brand & Voice

Tessera sounds like a good inventory lead: **precise, plain, and quantified.** It names things the way a
buyer does — "SKU", "on hand", "reorder point", "lead time", "purchase order" — and it always attaches a
number. Feedback is short and factual: "Created PO-8867", "M4 Washer → 24,110 on hand", "Reorder point
updated". No cheerful filler, no abstraction: the number *is* the message. The brand mark is a literal
mosaic — a cobalt tile with a 2×2 grid glyph — and the name is set tight and confident. Where a state
matters, the word rides with the color, never the color alone.

---

## 4. Color System

Two editions, one token set. **Floor** (light) is a bright, true-neutral warehouse; **Nightshift** (dark)
is a deep zinc for low-light planning. Every value is a role token, so the swap is one class on `<html>`.

### Floor edition (light)

| Role | Token | Value |
| --- | --- | --- |
| App canvas | `--canvas` | `#F4F4F5` (zinc-100) |
| Surface (cards, chrome) | `--surface` | `#FFFFFF` |
| Inset surface | `--surface-2` | `#FAFAFA` |
| Sunken surface | `--surface-3` | `#F4F4F5` |
| Hairline (cards) | `--line` | `#E4E4E7` |
| Structural separator (chrome) | `--line-2` | `#D4D4D8` |
| Primary text | `--ink` | `#18181B` (zinc-900) |
| Secondary text | `--ink-2` | `#52525B` (zinc-600) |
| Caption / label | `--ink-3` | `#6B6B74` |
| Accent (brand, text/icon/chart) | `--accent` | `#2563EB` |
| Accent (text on tint) | `--accent-strong` | `#1D4ED8` |
| Accent (button fill) | `--accent-solid` | `#2563EB` |
| Accent tint (nav, selection) | `--accent-soft` | `#E4ECFD` |

### Nightshift edition (dark)

Deep, true-neutral zinc — not blue-black: `--canvas #09090B`, `--surface #18181B`, `--surface-2 #212124`,
`--surface-3 #27272A`, hairlines `#27272A` / separators `#3F3F46`, `--ink #FAFAFA`, `--ink-2 #B0B0B8`,
`--ink-3 #8F8F99`. The accent brightens for dark surfaces (`--accent #3B82F6`, `--accent-strong #60A5FA`)
while the **button fill stays `#2563EB`** so white button text keeps a 5.1:1 ratio in both editions.

**Rules of use.** Cobalt is the brand and the single primary action — used decisively, never sprayed. A
**dedicated structural separator** (`--line-2`, a step stronger than card hairlines) draws the app chrome
— the sidebar edge and top bar — so the layout reads as a frame; card borders stay on the lighter
`--line`. The neutral is *true* zinc (no hue) so status color (§5) is the only saturation on screen.

### Semantic figure colors

Status colors exist as **text-legible tokens** (dark enough to pass AA as small colored text on their
surface) and separate **graph tokens** (brighter, for chart fills where 3:1 suffices):

| Meaning | Text token (Floor) | Graph token (Floor) |
| --- | --- | --- |
| OK / in stock / received | `--ok #15803D` | `--ok-graph #16A34A` |
| Low | `--low #C2410C` | `--low-graph #EA580C` |
| Warning / backordered / partial | `--warn #B45309` | `--warn-graph #D97706` |
| Critical / out / cancelled | `--crit #DC2626` | `--crit-graph #DC2626` |
| Neutral / draft | `--neutral #52525B` | — |

In Nightshift all six lighten in step (`--ok #22C55E`, `--low #FB923C`, `--warn #FBBF24`, `--crit #F87171`).

## 5. The Status Systems — Stock & PO

Two fixed vocabularies, each a triplet of **color + label (+ dot)**, used identically in chips, table
`<select>`s, drawer state pickers, and the dashboard doughnut.

**Stock state** — the condition of a SKU on the shelf:

| State | Token | Meaning |
| --- | --- | --- |
| In stock | `--ok` | On hand above the reorder point |
| Low | `--low` | On hand at or below reorder |
| Backordered | `--warn` | Ordered but not yet received |
| Out of stock | `--crit` | Zero on hand |

**PO state** — the lifecycle of a purchase order:

| State | Token | Meaning |
| --- | --- | --- |
| Draft | `--neutral` | Being written, not sent |
| Sent | `--accent` | Issued to supplier |
| Partial | `--warn` | Some lines received |
| Received | `--ok` | Fully received |
| Cancelled | `--crit` | Voided |

Stepping a stock count **auto-recomputes** the stock state (out → low → in) so the badge never lies; a
manual `<select>` still allows an override to *backordered*. Status is **never carried by color alone** —
the label always accompanies it, and dots are paired with text. Chips tint the state color at ~14% alpha
for the fill and use it at full strength for the label, holding AA in both editions.

## 6. Typography

Two typefaces: one humanist grotesk for voice, one engineered monospace for figures.

| Role | Typeface | Used for |
| --- | --- | --- |
| UI / display | **Familjen Grotesk** | Headings, labels, body, buttons, nav — a warm, slightly quirky Scandinavian grotesk that keeps a neutral system from feeling sterile |
| Figures / codes | **Geist Mono** | Counts, reorder points, values, SKU codes, lead times, PO IDs, timestamps, all table numbers |

- Familjen Grotesk carries the personality so the palette doesn't have to — its open apertures and subtle
  character read cleanly at label sizes and hold up in dense tables.
- **Geist Mono** with `tabular-nums` gives every figure a fixed cell: columns align, a `24,100` and a `0`
  occupy comparable rhythm, and deltas scan vertically. Numbers are the product; they get the mono.
- Hierarchy is by **size and weight**, not color: page titles 22–26px bold, section headers 14px
  semibold, body 14px, small-caps labels 11px at `.05em` tracking. A restrained scale, reused everywhere.

## 7. Responsive Layout

One app shell, reflowed by breakpoint — never a phone mock in a desktop window.

- **Desktop (≥ 1024px):** persistent left **sidebar** + sticky **top bar** + a fluid content column
  capped at 1440px. The dashboard is a **4-column bento mosaic** (a 2×2 hero tile beside stat tiles,
  then chart and alert tiles); tables run full width.
- **Tablet (≥ 640px):** the bento relaxes to 2 columns; supplier cards go 2-up; tables keep priority
  columns and scroll horizontally within their tile.
- **Phone (< 1024px):** the sidebar becomes a **left nav drawer** behind a hamburger; the bento stacks to
  a single column; supplier cards go 1-up; tables scroll horizontally with a min-width so columns never
  crush. Every control is ≥ 44px; steppers, chips, and selects stay thumb-sized.

The same tokens, tiles, and status systems render at every width — only the grid's column count changes.

## 8. Elevation, Radius & Surfaces

Tessera is **quiet and crisp** — mostly flat, with just enough shadow to lift overlays. Depth is a tool,
not a texture.

- **Two-level elevation:** `--shadow-card` (a barely-there resting shadow that keeps tiles crisp against
  the canvas) and `--shadow-pop` (a clear lift for drawers, the modal, and toasts).
- **Radius:** `--r-card` / `--r-tile` 10px for tiles and surfaces, `--r-ctrl` 8px for inputs and buttons,
  `--r-chip` 6px for chips. Rounded enough to feel modern, square enough to tile cleanly. Pills (99px) are
  reserved for status badges and toggles.
- **Surfaces:** four steps — `--canvas` (the grout between tiles) → `--surface` (tiles & chrome) →
  `--surface-2` (insets, fields, stepper wells) → `--surface-3` (sunken/hover). Consistent internal
  padding (16–20px) makes every tile a sibling of every other.

## 9. Components & Patterns

- **KPI tile** — small-caps label + monospace figure + sparkline + delta; the mosaic's glance layer.
- **Bento hero** — a 2×2 tile pairing a headline figure (on a faint mosaic panel) with the value/turns
  area chart and a segmented range control.
- **Charts** — area (value & turns, dual-axis), bar (stock by warehouse), doughnut (PO status), each
  styled from the edition tokens and re-rendered on edition swap and tab activation; animation off for
  instant, flicker-free redraws.
- **Data table** — monospace small-caps sticky header, sort-affordant headers with direction arrows,
  zebra rows, cobalt-tint hover, responsive horizontal scroll; carries an **inline-editable stepper**
  (on-hand +/−), a **click-to-edit** reorder point, and an **inline status `<select>`**.
- **Edit drawer (right)** — open a SKU or a PO, edit its fields in place (name, category, supplier,
  counts, state chips, notes), Save/Cancel. Edits apply on save with a toast.
- **Nav drawer (left)** — the mobile navigation surface behind the hamburger.
- **Modal** — a centered "New purchase order" dialog with scrim, Esc-to-close, focus on open, and a
  working create that prepends the PO and routes to the list. A second **confirm** dialog guards the
  destructive data reset.
- **Inputs** — text, search, `<select>`, textarea, **toggle/switch**, **segmented control**, **stepper**
  (+/−), **filter chips**, and inline-editable numeric fields — all keyboard-operable with a visible
  cobalt focus ring.
- **Status badge**, **toast** (action feedback), and a full-height **sidebar** with a profile footer.

## 10. The Mosaic — the signature

The one place Tessera spends boldness. The dashboard hero figure sits on a **faint tile grid** — a
22px CSS-gradient mosaic drawn in `--line`, evoking a bin wall or a warehouse floor plan. It is subtle
(≈60% opacity, hairline weight) and appears exactly once, so it reads as a signature rather than a
texture. Everything else stays disciplined and flat. Remove-one-thing restraint applies: the mosaic earns
its keep by naming the metaphor at a glance; nowhere else is decoration allowed.

## 11. Motion

Motion is functional and brief (**100–220ms**, standard ease): press-scale on tap targets and steppers,
drawer slide-in, modal fade-scale, toast rise, chip and segment state transitions. It confirms a click
landed and shows where a surface came from. **Charts do not animate** — a dashboard redraw should be
instant and stable, never a wobbling entrance. `prefers-reduced-motion` collapses all transitions to
near-zero. Forbidden: decorative loops, long entrances, and number count-ups that delay a figure the
buyer needs now.

## 12. Accessibility

- **AA on real surfaces, both editions.** Body, caption, label, and status text clear WCAG 2.1 AA on
  their actual backgrounds — including tinted chips and the faint mosaic panel — in Floor **and**
  Nightshift. Verified against the rendered computed colors, not just the swatches.
- **Never color-only.** Every stock and PO state pairs its color with a label (and a dot); the doughnut
  legend lists each state by name.
- **Keyboard-complete.** Every action — nav, stepper, select, chip, toggle, drawer, modal — is reachable
  and operable by keyboard with a visible 2px cobalt focus ring; Esc closes every overlay; the modal
  focuses its first field on open.
- **Semantic + labelled.** Real `<button>`, `<select>`, `<input>`, and `<table>` elements; icon-only
  buttons carry `aria-label`; toggles use `role="switch"` + `aria-checked`; sortable headers expose
  `aria-sort`; toasts announce via an `aria-live` region.
- **Honest states.** Empty (filtered-to-nothing with a reset), inline-edit, and destructive-confirm
  states are all designed, not just the happy path.
- **Touch + zoom.** Targets ≥ 44px; layout reflows (not shrinks) to 375px and survives 200% zoom.

## 13. Tokens in Practice

Light under `:root`, dark under `html.dark`; Floor → Nightshift is one class swap:

```css
:root     { --canvas:#F4F4F5; --surface:#FFFFFF; --ink:#18181B; --accent:#2563EB;
            --line:#E4E4E7; --line-2:#D4D4D8; /* … Floor */ }
html.dark { --canvas:#09090B; --surface:#18181B; --ink:#FAFAFA; --accent:#3B82F6;
            --line:#27272A; --line-2:#3F3F46; /* … Nightshift */ }
```

Both status systems are tokens too (`--ok … --crit` for text, `--*-graph` for charts), so a chip, a table
cell, a drawer picker, and a chart slice all read the same source. No raw hex in markup, no magic spacing,
no one-off durations.

> **Note — chrome separators.** App chrome (sidebar edge, top bar) uses `--line-2` via a CSS **class**
> (`.sidebar`, `.topbar`), not a clobberable inline `:style`. Keep structural borders in classes so a
> framework's dynamic binding can never wipe them.
>
> **Note — selects.** Table-row `<select>`s use **static `<option>`s**, not an `x-for` template, because
> `x-model` + looped options inside a row loop can fail to reflect the bound value on first paint. The
> single-instance drawer selects keep `x-for` but force-sync with `x-effect`.

## 14. Anti-Patterns Tessera Forbids

- ❌ **A wall of undifferentiated table** — the dashboard must be a tiled mosaic, not one giant grid.
- ❌ **A warm or cool gray** pretending to be neutral — the zinc is *true* neutral by design.
- ❌ **Cobalt as a highlighter** — it is the single primary action and active state, nothing else.
- ❌ **Color-only status** with no label.
- ❌ **Proportional figures** in tables — numbers are monospace and tabular, always.
- ❌ **A status badge that contradicts the count** — stepping a count recomputes its state.
- ❌ **Modal-as-dumping-ground** — modals are for focused create/confirm only.
- ❌ **Decorative motion** — no chart entrances, no count-ups, no loops.

## 15. Pre-Ship Checklist

- [ ] Excellent on desktop **and** phone; reflows at ~375 / ~768 / ≥1280px; no phone-in-a-window.
- [ ] Every nav item (Overview, Inventory, Purchase orders, Suppliers, Settings) routes to a real,
      populated page.
- [ ] BI dashboard with tiled KPIs, area + bar + doughnut charts, and a data table.
- [ ] Stock and PO status systems consistent (color + label) across chips, tables, drawers, and charts.
- [ ] Inline edits work: stepper cell, click-to-edit reorder point, status selects, and a click-to-edit
      profile name; the edit drawer and the nav drawer both open/close (incl. Esc).
- [ ] Modal (New PO) creates + toasts; the destructive reset is confirm-guarded.
- [ ] Full input range present and keyboard-operable with visible focus.
- [ ] Targets ≥ 44px; never color-only; AA contrast verified in Floor **and** Nightshift.
- [ ] Charts re-render on edition swap **and** tab activation; hidden canvases guarded; no console errors.
- [ ] Chrome separators use class-based `--line-2`; `prefers-reduced-motion` respected.

---

> **Colophon.** Set in Familjen Grotesk and Geist Mono. Tessera is one theme in the
> [`my-themes`](../../README.md) gallery — the modular, figure-dense, procurement-first counterpart to
> Meridian, Broadsheet, and Frontline. The warehouse mosaic — every SKU in its place.
