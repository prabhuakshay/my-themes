# Frontline — Theme Design Specification

> **Version 1.0** · Responsive design system for field & operations software · Field + Shift editions
> Tagline: **"Enterprise software for the people who don't sit at a desk."**

Most enterprise UI assumes a desk, a mouse, two screens, and a steady connection. **Frontline
assumes one hand, a glove, direct sunlight, and a flaky signal.** It is a design system for the
people who run operations *in the world* — field technicians, drivers, inspectors, warehouse and
utility crews — and for the dispatchers and managers coordinating them from a desk. The same
tokens serve both: a full operations console on a monitor and a glanceable, thumb-driven app on a
phone. Frontline is high-contrast, tactile, status-driven, and built to keep working when the
network doesn't.

> **A third pole.** This repository ships **Meridian Enterprise** (a flat Carbon instrument panel)
> and **Broadsheet** (a flat editorial front page). Both are light, desktop-first, and *flat*.
> Frontline is the deliberate third pole: **tactile and elevated** (real depth and rounded
> surfaces), **responsive-first** (desktop *and* phone, equally), and **hi-vis** rather than
> restrained. §2 maps the contrast.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Frontline vs. the others](#2-frontline-vs-the-others)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [The Operational Status System](#5-the-operational-status-system)
6. [Typography](#6-typography)
7. [Responsive Layout](#7-responsive-layout)
8. [Elevation, Radius & Surfaces](#8-elevation-radius--surfaces)
9. [Components & Patterns](#9-components--patterns)
10. [Connectivity & Offline](#10-connectivity--offline)
11. [Motion](#11-motion)
12. [Accessibility](#12-accessibility)
13. [Tokens in Practice](#13-tokens-in-practice)
14. [Anti-Patterns Frontline Forbids](#14-anti-patterns-frontline-forbids)
15. [Pre-Ship Checklist](#15-pre-ship-checklist)

---

## 1. Design Principles

Seven principles. When two conflict, the **earlier** wins.

### P1 — Designed for the thumb, not the cursor
Primary actions sit where a thumb can reach them; targets are ≥ 44px; nothing critical hides
behind hover. The phone is a first-class target, not a shrunk-down desktop. *Hover is an
enhancement, never a requirement.*

### P2 — Legible in daylight
High contrast is the baseline, not an accessibility afterthought. Type is sturdy and large enough
to read at arm's length on a bright loading dock. The palette is **hi-vis** — saturated functional
colors that survive glare — over subtle grays that wash out in the sun.

### P3 — Status is the system
The operational state of a job (Scheduled, En route, On site, Blocked, Done) is the backbone of
the interface. Color, icon, and label always travel together and mean the same thing everywhere
(§5). Color is never spent on decoration; it reports state.

### P4 — Resilient to bad signal
The field has dead zones. Frontline is offline-aware by default: changes are captured optimistically,
a **sync state is always visible**, and "Saved offline · will sync" is a designed state, not an
error. The worker is never blocked by the network.

### P5 — Responsive, never mobile-only
One system, two shapes. On a desktop it is a full dispatch console — sidebar, BI dashboard, dense
tables. On a phone it reflows to a single column with a nav drawer and thumb-reachable actions.
*A phone mock centered in a desktop window is a failure, not a feature.*

### P6 — Glanceable density
The one thing that matters right now — the next stop, the due time, the blocker — is the largest
thing on screen. Secondary detail is demoted or deferred to a tap. A worker should get the answer
in a two-second glance.

### P7 — Tactile and immediate
Elevation and rounded surfaces signal what is tappable; every action returns immediate feedback
(press state, toast, status change). The interface feels physical and responsive because the work
is physical and the stakes are real.

---

## 2. Frontline vs. the others

| Axis | Meridian | Broadsheet | **Frontline** |
| --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | **Field / operations app** |
| Primary device | Desktop | Desktop | **Phone *and* desktop, equally** |
| Surface treatment | Flat, boxed | Flat, ruled | **Tactile — elevated, rounded** |
| Palette | Cool Carbon gray | Tinted newsprint | **Hi-vis concrete + safety orange** |
| Type | IBM Plex Sans/Mono | Fraunces/Archivo/Spline | **Saira + Martian Mono** |
| Accent | Carbon blue | Claret | **Safety orange `#FB5A1F`** |
| Organizing idea | Density | Editorial hierarchy | **Operational status + glanceability** |
| Signature concern | Governance | Provenance | **Connectivity / offline** |
| Modes | White / Gray-100 | Day / Evening | **Field / Shift** |

Use Frontline for field service, dispatch, logistics, inspections, utilities, and any product used
as much on a phone in the field as on a screen at a desk.

---

## 3. Brand & Voice

Frontline sounds like a good dispatcher: **clear, direct, and calm under pressure.** Short
imperatives ("Arrive", "Complete", "Sync now"), plain operational nouns ("work order", "stop",
"on van"), and honest system states ("Saved offline · will sync", "2 queued"). No cheerful filler,
no jargon, no ambiguity — a worker reading on the move needs the fact, not the flourish. The brand
mark is utilitarian and high-vis: a safety-orange block, an engineered typeface, a hard hat.

---

## 4. Color System

Two editions, one token set. **Field** (light) is tuned for daylight; **Shift** (dark) for night
crews and low-light cabs. Every value is a role token, so the swap is a single class on `<html>`.

### Field edition (light)

| Role | Token | Value |
| --- | --- | --- |
| App background (concrete) | `--bg` | `#EDF0F3` |
| Surface (cards, chrome) | `--surface` | `#FFFFFF` |
| Inset surface | `--surface-2` | `#F5F7F9` |
| Primary text | `--ink` | `#13171C` |
| Secondary text | `--ink-2` | `#586069` |
| Caption | `--ink-3` | `#8B95A0` |
| Hairline (cards) | `--line` | `#E5E9ED` |
| Structural separator (chrome) | `--line-2` | `#D3D9E0` |
| Brand (safety orange) | `--brand` | `#FB5A1F` |
| Brand pressed | `--brand-press` | `#E2470F` |

### Shift edition (dark)

Warm-leaning deep slate, not pure black: `--bg #0A0D11`, `--surface #161B21`, `--surface-2 #1D232B`,
`--ink #EAEEF2`, hairlines `#262D35` / separators `#323B45`, brand brightens to `#FF6A2E` so hi-vis
orange stays punchy on dark.

**Rules of use.** Safety orange is the brand and primary action — used decisively but not
sprayed across the UI. A **dedicated structural separator** (`--line-2`, a touch stronger than
card hairlines) defines the app chrome — the sidebar edge and top bar — so the layout reads
clearly; card borders stay on the lighter `--line`. Status colors (§5) are reserved for state.

## 5. The Operational Status System

The heart of the system. Five operational states, each a fixed triplet of **color + label (+ icon)**,
used identically in chips, table cells, timeline dots, and the dashboard doughnut.

| State | Token | Field | Meaning |
| --- | --- | --- | --- |
| Scheduled | `--s-sched` | `#5B6B7B` | Assigned, not started |
| En route | `--s-enroute` | `#2563EB` | Travelling to site |
| On site | `--s-onsite` | `#0D9488` | Arrived, working |
| Blocked | `--s-blocked` | `#E11D48` | Cannot proceed |
| Done | `--s-done` | `#16A34A` | Complete |

Status is **never carried by color alone** — the label (and icon where space allows) always
accompanies it. Chips tint the state color at low alpha for the fill and use it at full strength
for text, keeping AA contrast. In Shift edition all five lighten in step.

## 6. Typography

Two typefaces, chosen for an engineered, signage-like legibility that reads at a glance and on the
move.

| Role | Typeface | Used for |
| --- | --- | --- |
| UI / display | **Saira** + **Saira Semi Condensed** | Headings, labels, buttons; the condensed cut packs dense field data (codes, times) without shrinking type |
| Figures / codes | **Martian Mono** | Readings, IDs, SKUs, timestamps, table numbers |

- Saira's transit/signage character is the system's voice — confident and operational, not
  neutral. The **semi-condensed** cut earns horizontal space on phones and dense tables.
- **Martian Mono** gives tabular alignment and an instrument feel to every number and identifier.
- Hierarchy is by size and weight, with generous, glanceable headings (24–30px) and a sturdy
  14px body — larger than a typical desktop app, because it is read at arm's length.

## 7. Responsive Layout

One app shell, two shapes — driven by breakpoints, not by a separate build.

- **Desktop (≥ 1024px):** persistent left **sidebar** (collapsible to icons) + sticky **top bar** +
  fluid content. The dashboard is a multi-column grid (KPI tiles → charts → tables).
- **Tablet (≥ 640px):** grids relax to two columns; tables keep priority columns and scroll
  horizontally; the sidebar persists.
- **Phone (< 1024px):** the sidebar becomes a **left nav drawer** behind a hamburger; content
  stacks to one column; primary actions stay reachable; tables reflow or scroll. Targets ≥ 44px.

The same tokens, components, and status system render in both — only the arrangement changes.

## 8. Elevation, Radius & Surfaces

Where Meridian and Broadsheet are flat, Frontline is **tactile** — depth is how it signals what is
interactive.

- **Two-level elevation:** `--shadow` for resting cards (soft, close), `--shadow-lg` for overlays
  (drawers, modals, toasts) that lift clearly above the page.
- **Radius:** `--r` 14px for cards and surfaces, `--r-sm` 10px for controls, pill (99px) for chips
  and toggles. Rounded enough to feel physical and touch-friendly, not playful.
- **Surfaces:** three levels — `--bg` (concrete page) → `--surface` (cards & chrome) → `--surface-2`
  (insets, fields, steppers). Tap targets get a press-scale to feel responsive under a thumb.

## 9. Components & Patterns

- **KPI tile** — label + oversized figure + trend delta; the dashboard's glance layer.
- **Charts** — line/area (performance trend), bar (volume), doughnut (status mix), styled to the
  edition and re-rendered on edition swap.
- **Data table** — sticky small-caps header, status cells, hover rows, responsive scroll; supports
  an **inline-editable status `<select>`** that updates the row optimistically.
- **Edit drawer (right)** — open a record, edit its fields in place, Save/Cancel. The "app drawer
  edit" pattern for quick record changes without leaving the list.
- **Nav drawer (left)** — the mobile navigation surface.
- **Modal** — centered dialog for create/confirm flows, with scrim and Esc-to-close.
- **Inline edit** — click-to-edit fields (e.g. a name or meter reading) that swap to an input with
  Save/Cancel; editable table cells.
- **Inputs** — text, search, select, textarea, toggle, segmented control, **stepper** (+/−),
  filter chips — all touch-sized with visible focus.
- **Status chip / priority chip**, **toast** (action feedback, incl. offline states), and a
  **collapsible sidebar**.

## 10. Connectivity & Offline

A first-class, Frontline-specific concern.

- **Always show sync state.** A persistent indicator reports "Synced", "N queued", or "Offline".
- **Optimistic by default.** Edits apply immediately to the UI and queue for sync; the worker is
  never made to wait on the network.
- **Offline is a designed state, not an error.** Submitting while offline returns "Saved offline ·
  will sync" with a distinct (warn-toned) treatment — informative, not alarming.
- **Recover loudly, fail safe.** Sync completion and conflicts are surfaced explicitly; nothing is
  silently dropped.

## 11. Motion

Motion is functional and quick (**120–220ms**, standard ease): press-scale on tap, drawer slide,
modal fade-scale, toast in/out, sidebar collapse. It confirms a tap landed and shows where a
surface came from. Forbidden: decorative loops, long entrances, and number animations that delay a
reading the worker needs *now*.

## 12. Accessibility

- **Daylight contrast as the baseline** — body and status text clear WCAG 2.1 AA on their actual
  surfaces in **both** editions; the hi-vis palette is chosen for glare resilience.
- **Touch first** — targets ≥ 44px; no hover-only affordances; large hit areas on steppers,
  chips, and nav.
- **Never color-only** — status always pairs color with a label (and icon where space allows).
- **Visible focus** — a 2px brand outline on every interactive element; full keyboard operability
  on desktop; logical order.
- **Honest states** — loading, empty, offline, error, and success are all designed.

## 13. Tokens in Practice

Light under `:root`, dark under `html.dark`; the Field → Shift edition is one class swap:

```css
:root     { --bg:#EDF0F3; --surface:#FFFFFF; --ink:#13171C; --brand:#FB5A1F;
            --line:#E5E9ED; --line-2:#D3D9E0; /* … Field */ }
html.dark { --bg:#0A0D11; --surface:#161B21; --ink:#EAEEF2; --brand:#FF6A2E;
            --line:#262D35; --line-2:#323B45; /* … Shift */ }
```

Status colors are tokens too (`--s-sched … --s-done`), so a chip, a table cell, and a chart slice
all read the same source. No raw hex, no magic spacing, no one-off durations.

> **Note — chrome separators.** App chrome (sidebar edge, top bar) uses `--line-2`, set via a CSS
> class, *not* an inline style. Binding layout with a framework's dynamic `:style` while also
> setting borders inline can clobber the border — keep structural styling in classes.

## 14. Anti-Patterns Frontline Forbids

- ❌ **A phone mock floating in a desktop window** — the demo must be a real responsive layout.
- ❌ **Subtle low-contrast grays** that vanish in sunlight.
- ❌ **Color-only status** with no label.
- ❌ **Blocking the worker on the network** — no spinner-walls where an optimistic save would do.
- ❌ **Hover-dependent actions** or sub-44px targets on touch surfaces.
- ❌ **Decorative use of safety orange** — it is the brand/primary action, not a highlighter.
- ❌ **Equal-weight everything** — no glance layer, no hierarchy.

## 15. Pre-Ship Checklist

- [ ] Excellent on desktop **and** phone; reflows at ~375 / ~768 / ≥1280px; no phone-in-a-window.
- [ ] Every nav item routes to a real, populated page.
- [ ] BI dashboard with KPI tiles, line + bar + doughnut charts, and a data table.
- [ ] Status system consistent (color + label) across chips, tables, timeline, and charts.
- [ ] Inline edit (table cell + click-to-edit field), edit drawer, nav drawer, and modal all work.
- [ ] Sync/offline state is always visible; offline save is a designed, non-error state.
- [ ] Targets ≥ 44px; visible focus; never color-only; AA contrast in Field **and** Shift.
- [ ] Field **and** Shift editions both polished; charts re-render on swap.
- [ ] Chrome separators use a class-based `--line-2`, not a clobberable inline style.

---

> **Colophon.** Set in Saira and Martian Mono. Frontline is one theme in the
> [`my-themes`](../../README.md) gallery — the tactile, responsive, field-first counterpart to the
> flat desktop systems Meridian and Broadsheet.
