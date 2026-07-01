# Sage — Theme Design Specification

> **Version 1.0** · A humane, airy design system for HR & people-ops software · Daylight + Lamplight editions
> Tagline: **"People software that reads like a roster, not a spreadsheet."**

Most HR software treats people as rows in a database — dense grids, system jargon, and the visual
warmth of a payroll export. **Sage treats the org as a roster you tend to.** It is a design system
for people teams — HR business partners, recruiters, people-ops leads, and the managers they
support — built around the calm, considered work of hiring, onboarding, retaining, and caring for
a workforce. Sage is set on cream paper, voiced in a soft moss green with a clay counterpoint, and
spaced to breathe. Numbers are honest and legible; status is humane; nothing shouts.

> **A distinct pole.** This repository ships **Meridian Enterprise** (a flat Carbon instrument
> panel), **Broadsheet** (a flat editorial front page), and **Frontline** (a tactile, hi-vis field
> app). Sage is a different pole again: **warm and paper-like** rather than cool or hi-vis,
> **airy and low-density** rather than packed, and organized around **people and employment
> status** rather than instruments, editorial hierarchy, or operational state. §2 maps the contrast.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Sage vs. the others](#2-sage-vs-the-others)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [The Employment-Status System](#5-the-employment-status-system)
6. [Typography](#6-typography)
7. [Responsive Layout](#7-responsive-layout)
8. [Elevation, Radius & Surfaces](#8-elevation-radius--surfaces)
9. [Components & Patterns](#9-components--patterns)
10. [Motion](#10-motion)
11. [Accessibility](#11-accessibility)
12. [Tokens in Practice](#12-tokens-in-practice)
13. [Anti-Patterns Sage Forbids](#13-anti-patterns-sage-forbids)
14. [Pre-Ship Checklist](#14-pre-ship-checklist)

---

## 1. Design Principles

Six principles. When two conflict, the **earlier** wins.

### P1 — The roster is the metaphor
People ops is the ongoing act of tending a roster: who's here, who's joining, who's away, who's
leaving. Every surface — the directory, the pipeline, the leave list — is a view onto that roster,
and the person (name, face, status) is always the primary object. We never reduce a colleague to a
faceless row of cells.

### P2 — Humane before dense
An HR screen is read slowly and thoughtfully, not scanned under time pressure. Sage chooses
generous spacing, a comfortable type size, and one idea per region over maximum data density. The
whitespace is deliberate; it signals that people are not inventory.

### P3 — Status is the system
Employment state — **Active, Onboarding, On leave, Offboarding** — is the backbone of the
interface. Color, dot, and label always travel together and mean the same thing in a chip, a table
cell, a filter, and a chart legend (§5). Color is never spent on decoration; it reports state.

### P4 — Honest, legible numbers
Headcount, attrition, tenure, balances — the figures people ops runs on — are set in a mono face
with tabular alignment so they line up and read true. A number never lies through rounding or hides
behind a gradient; a trend is labelled with its direction and magnitude, not just a color.

### P5 — Quiet, warm, and calm
Sage spends its boldness on a single moss-green accent and a warm cream paper. Everything else stays
quiet: soft radii, hairline borders, low-contrast chrome. The palette is warm rather than clinical
because the subject is human. Saturated color appears only in small, meaningful doses.

### P6 — Responsive, never mobile-only
One app shell, two shapes. On a desktop it is a full people console — sidebar, BI dashboard, roster
tables. On a phone it reflows to a single column with a nav drawer and thumb-reachable actions.
*A phone mock centered in a desktop window is a failure, not a feature.*

---

## 2. Sage vs. the others

| Axis | Meridian | Broadsheet | Frontline | **Sage** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **The roster** |
| Domain | Generic enterprise BI | Enterprise data | Field service / dispatch | **HR / people ops** |
| Surface | Flat, boxed | Flat, ruled | Tactile, hi-vis | **Warm cream paper, softly raised** |
| Density | High | Editorial | Glanceable | **Low — airy and humane** |
| Palette | Cool Carbon gray | Tinted newsprint | Hi-vis + safety orange | **Cream + moss green + clay** |
| Type | IBM Plex Sans/Mono | Fraunces/Archivo/Spline | Saira + Martian Mono | **Schibsted Grotesk + Overpass Mono** |
| Accent | Carbon blue | Claret | Safety orange | **Moss green `#4F7A4E`** |
| Organizing idea | Density | Editorial hierarchy | Operational status | **People + employment status** |
| Modes | White / Gray-100 | Day / Evening | Field / Shift | **Daylight / Lamplight** |

Use Sage for HRIS, people directories, recruiting/ATS, onboarding, performance, and any product
where the data is *people* and the tone should be humane rather than industrial.

---

## 3. Brand & Voice

Sage sounds like a thoughtful people partner: **warm, plain, and direct without being corporate.**
It uses the language people actually use — "the roster," "joining," "on leave," "offboarding" —
not HR-system jargon ("FTE requisition disposition"). Actions are concrete verbs ("Add person,"
"Submit request," "Save changes") and confirmations mirror them ("Added to roster," "Request
submitted"). No cheerful filler, no shaming, no dark patterns — people-ops software touches
sensitive moments (leaves, exits) and must stay respectful. The brand mark is a **sprout** in a
moss-green tile: growth, care, tending. The wordmark is Schibsted Grotesk, humanist and friendly.

---

## 4. Color System

Two editions, one token set. **Daylight** (light) is warm cream paper for the working day;
**Lamplight** (dark) is a warm olive-charcoal for late reviews and low light — deliberately warm,
never a cold pure-black invert. Every value is a role token, so the swap is a single class on `<html>`.

### Daylight edition (light)

| Role | Token | Value |
| --- | --- | --- |
| App canvas (cream paper) | `--canvas` | `#F4F2EB` |
| Surface (cards, chrome) | `--surface` | `#FFFFFF` |
| Inset surface | `--surface-2` | `#F7F5EE` |
| Primary text | `--ink` | `#23261F` |
| Secondary text | `--ink-2` | `#5C6152` |
| Caption / micro-label | `--ink-3` | `#6E7460` |
| Hairline (cards) | `--line` | `#E7E3D8` |
| Structural separator (chrome) | `--line-2` | `#D5CFC0` |
| Accent (moss green) | `--accent` | `#4F7A4E` |
| Accent pressed | `--accent-press` | `#446B43` |
| Accent tint | `--accent-soft` | `#E4EEDF` |
| Accent text-on-tint | `--accent-ink` | `#2F5C30` |
| Counterpoint (clay) | `--clay` | `#C1683C` |
| Text on accent | `--on-accent` | `#FFFFFF` |

### Lamplight edition (dark)

Warm-leaning deep olive, not black: `--canvas #191B14`, `--surface #22251C`, `--surface-2 #2A2E23`,
`--ink #ECEADF`, hairlines `#333829` / separators `#454C38`. The accent **lightens** to `#86B27F`
so moss stays legible on dark, and text-on-accent flips to a deep olive `#17210F`. Clay warms to
`#D98E60`.

**Rules of use.** Moss green is the accent and primary action — used decisively but not sprayed
across the UI (P5). A **dedicated structural separator** (`--line-2`, a touch stronger than card
hairlines) defines the app chrome — the sidebar edge and top bar — so the layout reads clearly;
card borders stay on the lighter `--line`. Status colors (§5) are reserved for state, never decoration.

---

## 5. The Employment-Status System

The heart of the system. Four employment states, each a fixed pairing of **color + label (+ dot)**,
used identically in the roster's inline status cell, filter chips, and anywhere a person's state
appears.

| State | Token | Daylight | Meaning |
| --- | --- | --- | --- |
| Active | `--s-active` | `#3F7A4E` | Employed and working |
| Onboarding | `--s-onboarding` | `#B7791F` | Hired, ramping up / pre-start |
| On leave | `--s-leave` | `#5F7793` | Away — parental, sick, sabbatical |
| Offboarding | `--s-offboarding` | `#C0492E` | Notice period / exiting |

Status is **never carried by color alone** — a text label (and a dot) always accompanies it. Chips
tint the state color at low alpha (`color-mix … 14%`) for the fill, add a `30%` border, and use the
color at full strength for text and dot, keeping AA contrast. In Lamplight all four lighten in step
(`--s-active #83BC86`, `--s-onboarding #DBA94E`, `--s-leave #93A6C4`, `--s-offboarding #E28A6E`).

A parallel, smaller triad governs **leave requests** — Approved (`--pos`), Pending (`--warn`),
Declined (`--neg`) — rendered with the same chip recipe so the whole product reads one visual
language of state.

---

## 6. Typography

Two typefaces, chosen for a humane, readable calm — friendly enough for a people product, precise
enough for figures.

| Role | Typeface | Used for |
| --- | --- | --- |
| UI / display | **Schibsted Grotesk** | Headings, names, labels, buttons, body — a warm humanist grotesk |
| Figures / codes | **Overpass Mono** | Headcount, attrition, dates, IDs, table numbers, micro-labels |

- **Schibsted Grotesk** carries the personality: humanist, slightly friendly, confident without
  being corporate. Hierarchy is built from size and weight (400/500/600/700), not from many faces.
- **Overpass Mono** gives tabular alignment and an honest, instrument feel to every figure, plus the
  uppercase, letter-spaced **micro-labels** (`.lbl`) that quietly caption each region.
- Body sits at a comfortable 14px with 1.5 line-height; display headings run 17–32px with tight
  tracking. Numbers use `font-variant-numeric: tabular-nums` so columns line up.

---

## 7. Responsive Layout

One app shell, two shapes — driven by breakpoints, not by a separate build.

- **Desktop (≥ 1024px):** persistent left **sidebar** (collapsible to icons) + sticky **top bar** +
  a max-1400px content column. The dashboard is a multi-column grid (KPI tiles → charts → table).
- **Tablet (≥ 640px):** grids relax to two columns; tables keep priority columns and scroll
  horizontally; the sidebar persists.
- **Phone (< 1024px):** the sidebar becomes a **left nav drawer** behind a hamburger; content stacks
  to one column; a full-width search appears at the top; primary actions stay reachable; tables drop
  lower-priority columns and scroll. Touch targets ≥ 44px.

The same tokens, components, and status system render in both — only the arrangement changes.

## 8. Elevation, Radius & Surfaces

Sage is **softly raised paper** — present but never glossy; depth is gentle, in service of calm.

- **Restrained elevation:** `--shadow-sm` for resting cards (a whisper of lift), `--shadow-lg` for
  overlays (drawers, modals, toasts) that float clearly above the page. No heavy drop shadows.
- **Radius:** `--r` 16px for cards and surfaces, `--r-sm` 10px for controls, pill (99px) for chips
  and toggles. Rounded enough to feel humane and soft, never playful.
- **Surfaces:** three warm levels — `--canvas` (cream paper page) → `--surface` (cards & chrome) →
  `--surface-2` (insets, fields, zebra rows). Borders are hairline; separation comes from tint and
  space more than from lines.

## 9. Components & Patterns

- **KPI tile** — micro-label + oversized tabular figure + a labelled, directional trend delta; the
  dashboard's glance layer.
- **Charts** — headcount growth (line/area), hires-vs-exits (grouped bar), headcount-by-department
  (doughnut), styled to the edition and **re-rendered on edition swap and tab activation** (hidden
  canvases are guarded with `offsetParent === null`).
- **Roster table** — small-caps mono header with **sortable columns**, zebra rows, hover tint,
  responsive column-dropping, and an **inline-editable status `<select>`** inside a status chip that
  updates the row optimistically. A second table (Hiring) carries an **inline stage `<select>`**.
- **Edit drawer (right)** — open a person, edit their fields in place (name, email, department,
  status, title, location, manager, notes), Save/Cancel. Edits are staged on a clone and committed
  on Save, so Cancel is truly non-destructive.
- **Nav drawer (left)** — the mobile navigation surface behind the hamburger.
- **Modal** — centered "Add person" dialog with scrim and Esc-to-close; creating unshifts a real row
  onto the roster and toasts.
- **Inline edit** — the editable status cell **and** a click-to-edit name in Settings (click → input
  with Save on Enter, Escape to cancel).
- **Inputs** — text, search, `<select>`, textarea, toggle/switch, segmented control, **stepper**
  (+/−, on the time-off request), filter chips, and inline-editable numeric fields — all touch-sized
  with visible focus.
- **Status chip**, **leave chip**, **toast** (action feedback via a live region), and a **collapsible
  sidebar** with a persistent account footer.

## 10. Motion

Motion is soft and quick (**120–280ms**, standard ease): a gentle press on buttons, a drawer slide,
a modal fade-scale, a toast that rises. It confirms an action landed and shows where a surface came
from — never decorative loops or long entrances. `prefers-reduced-motion` collapses all of it to
near-instant. Number changes are immediate, never animated, so a reading is never delayed.

## 11. Accessibility

- **Contrast on real surfaces** — body and status text clear WCAG 2.1 AA on their actual tinted and
  paper backgrounds in **both** editions; `--ink-3` micro-labels are tuned to hold ≥ 4.5:1.
- **Never color-only** — every status pairs color with a text label and a dot.
- **Full keyboard operability** — a 2px moss focus ring (`:focus-visible`) on every interactive
  element; logical order; Escape closes the modal, edit drawer, and nav drawer; toggles are reachable
  and operable with Enter.
- **Labelled controls** — icon-only buttons carry `aria-label`; each status/dept/stage select has an
  accessible name; toasts announce via an `aria-live="polite"` region.
- **Touch first** — targets ≥ 44px on nav, buttons, steppers, and chips.
- **Honest states** — loading-safe rendering, a real empty state on the roster (with a clear reset),
  and success confirmations for every action.

## 12. Tokens in Practice

Light under `:root`, dark under `html.dark`; the Daylight → Lamplight edition is one class swap:

```css
:root     { --canvas:#F4F2EB; --surface:#FFFFFF; --ink:#23261F; --accent:#4F7A4E;
            --line:#E7E3D8; --line-2:#D5CFC0; --on-accent:#FFFFFF; /* … Daylight */ }
html.dark { --canvas:#191B14; --surface:#22251C; --ink:#ECEADF; --accent:#86B27F;
            --line:#333829; --line-2:#454C38; --on-accent:#17210F; /* … Lamplight */ }
```

Status colors are tokens too (`--s-active … --s-offboarding`), so a chip, a table cell, and a filter
all read the same source, and chip fills derive from them with `color-mix` rather than hand-picked
hex. No raw hex in markup, no magic spacing, no one-off durations.

> **Note — chrome separators.** App chrome (sidebar edge, top bar) uses `--line-2` via a CSS class
> (`.sidebar`, `.topbar`), a touch stronger than card hairlines, so the layout reads clearly. Keep
> structural borders in classes rather than clobberable inline styles.

## 13. Anti-Patterns Sage Forbids

- ❌ **A spreadsheet of people** — dense, faceless grids that treat colleagues as inventory rows.
- ❌ **Color-only status** with no label or dot.
- ❌ **Cold pure-black dark mode** — Lamplight is warm olive, designed intentionally, not inverted.
- ❌ **HR-system jargon** where a plain human word exists.
- ❌ **Decorative use of the moss accent** — it is the brand/primary action, not a highlighter.
- ❌ **Shaming or pressuring copy** around sensitive moments (leave, offboarding).
- ❌ **Cramped, airless density** — Sage breathes; whitespace is a feature, not waste.
- ❌ **Numbers without direction** — a trend needs a labelled magnitude, not just a red/green tint.

## 14. Pre-Ship Checklist

- [ ] Excellent on desktop **and** phone; reflows at ~375 / ~768 / ≥1280px; no phone-in-a-window.
- [ ] Every nav item routes to a real, populated page (Dashboard, People, Hiring, Time off, Settings).
- [ ] BI dashboard with KPI tiles, line/area + bar + doughnut charts, and a data table.
- [ ] Status system consistent (color + dot + label) across the inline cell, chips, and filters.
- [ ] Inline edits (status cell + click-to-edit name), edit drawer, nav drawer, and modal all work.
- [ ] Full input range present: text, search, select, textarea, toggle, segmented, stepper, chips.
- [ ] Targets ≥ 44px; visible focus; never color-only; AA contrast in Daylight **and** Lamplight.
- [ ] Both editions polished; charts re-render on edition swap **and** tab activation.
- [ ] Chrome separators use a class-based `--line-2`, not a clobberable inline style.

---

> **Colophon.** Set in Schibsted Grotesk and Overpass Mono. Sage is one theme in the
> [`my-themes`](../../README.md) gallery — the warm, airy, people-first counterpart to the cool
> Meridian, the editorial Broadsheet, and the hi-vis Frontline.
</content>
</invoke>
