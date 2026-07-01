# Beacon — Theme Design Specification

> **Version 1.0** · Design system for customer-support & helpdesk software · Daylight + Nightwatch editions
> Tagline: **"A calm signal in the queue."**

A support queue is a stressful place: the clock is always running, the customer is already
frustrated, and the agent is juggling a dozen open conversations at once. Most helpdesk UIs answer
that stress with *more* — more red, more badges, more density, more noise. **Beacon answers it with
calm.** It is a soft-lilac, rounded, human-first console built so the one thing that matters right
now — the next reply, the ticket about to breach, the customer who is unhappy — is the clearest
thing on screen, and everything else stays quiet. It treats support as a human craft, not a ticket
factory: real names, real faces, CSAT, and a plain, warm voice.

> **A distinct pole.** The gallery's flat, desk-bound systems (**Meridian**, **Broadsheet**) and
> its tactile field system (**Frontline**) are all *operational* in tone. Beacon is the deliberate
> **calm, human, service** pole: a friendly violet accent on soft lilac, generous rounding, and a
> signature that is the absence of noise rather than a loud mark. §2 maps the contrast.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Beacon vs. the others](#2-beacon-vs-the-others)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [The Signal System (priority & status)](#5-the-signal-system-priority--status)
6. [Typography](#6-typography)
7. [Responsive Layout](#7-responsive-layout)
8. [Elevation, Radius & Surfaces](#8-elevation-radius--surfaces)
9. [Components & Patterns](#9-components--patterns)
10. [Motion](#10-motion)
11. [Accessibility](#11-accessibility)
12. [Tokens in Practice](#12-tokens-in-practice)
13. [Anti-Patterns Beacon Forbids](#13-anti-patterns-beacon-forbids)
14. [Pre-Ship Checklist](#14-pre-ship-checklist)

---

## 1. Design Principles

Seven principles. When two conflict, the **earlier** wins.

### P1 — Calm over loud
A support console is read under pressure. Beacon spends its visual energy on *reducing* noise:
plenty of whitespace, a single soft accent, muted chrome, and colour reserved for meaning. There is
**one focal point per screen** and it is never fighting three badges for attention. The absence of
clutter is the feature.

### P2 — Status is a shared language
Every ticket carries two orthogonal facts — its **priority** (how much it matters) and its
**status** (where it is in its life). Both are a fixed triplet of **colour + label (+ dot)** used
identically in chips, table cells, inline `<select>`s, and the dashboard doughnut (§5). An agent
learns the language once and reads it everywhere.

### P3 — The human is the product
Support is people helping people. Beacon shows **names and faces**, not just ticket IDs; it surfaces
**CSAT** and account health as first-class metrics; and it writes in a warm, plain voice. The
metaphor is a helpful colleague, never a machine spitting out case numbers.

### P4 — Glance, then act
Time-to-first-response is the currency of support, so the thing an agent needs *now* — the subject,
the wait time, the SLA state — is the largest, and the controls to act on it (change status,
reassign, open the record) sit **inline, where the eye already is**. No hunting, no round-trips.

### P5 — Two editions, one system
Support runs around the clock. **Daylight** (light) is the bright, calm day shift; **Nightwatch**
(dark) is a deep violet-slate tuned for low-light night desks. Every value is a role token, so the
swap is a single class on `<html>` — including the priority and status colours.

### P6 — Responsive, never mobile-only
One app shell, two shapes. On a monitor it is a full support console — sidebar, BI dashboard, dense
tables. On a phone it reflows to a single column with a nav drawer and thumb-reachable actions.
*A phone mock floating in a desktop window is a failure, not a feature.*

### P7 — Accessible calm
Soft does not mean low-contrast. Body and status text clear WCAG 2.1 AA on their **actual tinted
surfaces** in both editions; status is never carried by colour alone; focus is always visible; every
overlay closes on `Esc`.

---

## 2. Beacon vs. the others

| Axis | Meridian | Broadsheet | Frontline | **Beacon** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **Support console — a calm signal** |
| Domain | Enterprise BI | Financial / editorial | Field service | **Customer support / helpdesk** |
| Tone | Precise, neutral | Authoritative | Rugged, operational | **Calm, warm, human** |
| Surface | Flat, boxed | Flat, ruled | Tactile, hi-vis | **Soft lilac, rounded, gently elevated** |
| Palette | Carbon gray | Tinted newsprint | Concrete + safety orange | **Soft lilac + friendly violet + SLA amber** |
| Type | IBM Plex Sans/Mono | Fraunces/Archivo/Spline | Saira + Martian Mono | **Manrope + DM Mono** |
| Accent | Carbon blue | Claret | Safety orange | **Violet `#6D5CE7`** |
| Organizing idea | Density | Editorial hierarchy | Operational status | **Calm + the human in the queue** |
| Signature concern | Governance | Provenance | Connectivity / offline | **CSAT, SLA & tone of voice** |
| Editions | White / Gray-100 | Day / Evening | Field / Shift | **Daylight / Nightwatch** |

Use Beacon for helpdesks, contact centres, success/CSM tools, community inboxes, ITSM desks — any
product where a human is answering another human under a clock.

---

## 3. Brand & Voice

Beacon sounds like a **good support lead: warm, plain, and unhurried.** It names things the way a
customer would ("ticket", "reply", "wait time", "satisfaction"), not the way a database does. It
never blames, never pressures, never pads with "please" or "simply". Confirmations are quiet and
specific ("Created #4823", "Display name updated"); warnings are gentle, not alarming ("Add a
subject first"). The brand mark is a soft-cornered violet tile holding a small **beacon/signal**
glyph — a light in the queue — paired with the Manrope wordmark and the quiet tagline *Support
console*. The one flourish the system allows itself is the **signal ring**: a slow, low-opacity
pulse that marks something genuinely live. Everything else stays still.

---

## 4. Color System

Two editions, one token set. **Daylight** is tuned for bright rooms; **Nightwatch** for low-light
night desks — a deep violet-tinted slate, never pure black. Every value is a role token, so the swap
is one class on `<html>`.

### Daylight edition (light)

| Role | Token | Value |
| --- | --- | --- |
| App background (soft lilac) | `--canvas` | `#F6F6FB` |
| Surface (cards, chrome) | `--surface` | `#FFFFFF` |
| Inset surface (fields, insets) | `--surface-2` | `#F2F1FA` |
| Hairline (cards) | `--line` | `#E9E7F3` |
| Structural separator (chrome) | `--line-2` | `#D6D2EA` |
| Primary text | `--ink` | `#1C1A2E` |
| Secondary text | `--ink-2` | `#565273` |
| Caption / muted | `--ink-3` | `#918DA8` |
| Brand (violet) | `--accent` | `#6D5CE7` |
| Brand light | `--accent-2` | `#8574F0` |
| Brand tint | `--accent-soft` | `#ECE9FC` |
| SLA amber | `--amber` | `#E8990C` |
| Success | `--ok` | `#17B26A` |
| Warning | `--warn` | `#F79009` |
| Critical | `--crit` | `#F04438` |

### Nightwatch edition (dark)

Deep violet-slate, not black: `--canvas #0E0D18`, `--surface #1A1826`, `--surface-2 #232134`,
hairline `#2C2A3E` / separator `#3B3853`, `--ink #ECEAF6`, `--ink-2 #A9A4C6`. The accent brightens
to `#8B7BF0` so violet stays luminous on dark, and every semantic colour lightens in step
(`--ok #3DD68C`, `--amber #F5B44A`, `--warn #FBA94C`, `--crit #FB7185`).

**Rules of use.** Violet is the brand and the single primary action — used decisively, never
sprayed as decoration. A **dedicated structural separator** (`--line-2`, a touch stronger than the
card hairline `--line`) draws the app chrome — the sidebar edge and top bar — so the layout reads
clearly; card borders stay on the lighter `--line`. The soft-lilac canvas (`--canvas`, a hair off
white) is what gives Beacon its calm; large fills never use saturated colour.

### Signal-pair tokens (the key to two editions)

Chips and inline selects need a **fill** *and* a **text** colour that both hold AA in either
edition. Beacon ships them as paired tokens rather than raw hex, so a chip is edition-correct for
free:

| Pair | Daylight fill / ink | Nightwatch fill / ink |
| --- | --- | --- |
| Accent | `#ECE9FC` / `#5A48C9` | `#2A2547` / `#BDB2F8` |
| Amber | `#FDF1DC` / `#B54708` | `#3A2D16` / `#F5C77E` |
| Success | `#DFF6EA` / `#0B7A47` | `#12301F` / `#6EE7A8` |
| Critical | `#FDE7E6` / `#B42318` | `#3A1D24` / `#FCA5A5` |

Neutral chips (Low / On hold) use `--surface-2` / `--ink-2`, which are already edition-aware.

## 5. The Signal System (priority & status)

The heart of Beacon. Two small, fixed vocabularies — each a triplet of **colour + label + dot** —
render identically in chips, table cells, inline `<select>`s, and charts.

**Priority** — *how much it matters:*

| Priority | Dot token | Meaning |
| --- | --- | --- |
| Urgent | `--crit` | Breaching or critical; act now |
| High | `--warn` | Important; next up |
| Normal | `--accent` | Standard queue |
| Low | `--ink-3` | Can wait |

**Status** — *where it is in its life:*

| Status | Dot token | Meaning |
| --- | --- | --- |
| Open | `--accent` | Awaiting an agent reply |
| Pending | `--amber` | Waiting on the customer |
| On hold | `--ink-3` | Parked, blocked on something |
| Solved | `--ok` | Resolved |

Status and priority are **never carried by colour alone** — the label (and dot) always travel with
the colour. Chips use the low-alpha *fill* token behind the full-strength *ink* token, keeping AA on
tinted lilac. Both selects are **inline-editable** in the queue: changing one updates the row,
re-tints the control, and fires a toast. In Nightwatch every pair lightens together.

## 6. Typography

Two typefaces, chosen for a friendly-but-precise voice.

| Role | Typeface | Used for |
| --- | --- | --- |
| UI / display | **Manrope** (400–800) | Headings, labels, buttons, body — a warm, low-contrast geometric sans with soft terminals |
| Figures / codes | **DM Mono** (400–500) | Ticket IDs, wait times, percentages, table numbers, SLA readouts |

- **Manrope** is the calm human voice of the system: rounded enough to feel approachable, even
  enough to stay quiet at 13–14px in dense tables, confident at 24–26px on KPIs. Hierarchy is built
  from **size and weight** (700/800 for emphasis) before colour is ever spent.
- **DM Mono** gives every number and identifier tabular alignment and a subtle "instrument" texture,
  so IDs, wait times, and CSAT read as data, not prose.
- Body sits at a comfortable **13.5–14px**; captions and small-caps table headers at 11–12px with
  loosened tracking. Real punctuation throughout (em dashes, curly quotes, `·` separators).

## 7. Responsive Layout

One app shell, two shapes — driven by breakpoints, not a separate build.

- **Desktop (≥ 1024px):** persistent **248px sidebar** (brand, nav, a live SLA card, user) + sticky
  **top bar** (title, search, New ticket, edition toggle, notifications) + fluid content. The
  dashboard is a multi-column grid: KPI tiles → charts → agents/SLA → a data table.
- **Tablet (≥ 640px):** grids relax to two columns; tables keep priority columns and scroll
  horizontally; the sidebar persists.
- **Phone (< 1024px):** the sidebar becomes a **left nav drawer** behind a hamburger; content stacks
  to one column; the search collapses; primary actions stay reachable; tables scroll horizontally.
  Targets ≥ 44px.

The same tokens, components, and signal system render in both — only the arrangement changes.

## 8. Elevation, Radius & Surfaces

Beacon is **gently elevated** — soft, close shadows that suggest a calm, well-lit room, never harsh
drop shadows.

- **Three-level elevation:** `--shadow-sm` for resting cards, `--shadow-md` for hovers and toasts,
  `--shadow-lg` for overlays (drawer, modal) that lift clearly above the page.
- **Radius:** `--r-lg` 14px for cards and surfaces, `--r-md` 10px for controls, `--r-sm` 8px for
  chips-in-cells and small tiles, pill (999px) for chips, filter buttons, and toggles. Rounded
  enough to read as friendly, disciplined enough to stay professional.
- **Surfaces:** three levels — `--canvas` (soft-lilac page) → `--surface` (cards & chrome) →
  `--surface-2` (fields, insets, zebra rows). Colour separates surfaces sparingly; spacing and the
  hairline system do most of the work.

## 9. Components & Patterns

- **KPI tile** — small-caps label + oversized DM Mono figure + a sparkline and a signed trend delta.
- **Charts** (Chart.js) — line/area (created vs. resolved, CSAT trend), bar (channel volume,
  resolution time), doughnut (priority mix, satisfaction mix), plus a conic **SLA gauge**. All read
  their colours from tokens and **re-render on edition swap and tab activation**; hidden canvases are
  guarded via `offsetParent === null`.
- **Data table** — small-caps sortable headers, zebra rows, hover, status/priority cells, horizontal
  scroll on mobile, and **inline-editable** priority *and* status `<select>`s that update the row.
- **Edit drawer (right)** — open a ticket, edit its fields against a **draft copy**, then
  Save (commit) / Cancel (discard). The "app drawer edit" pattern for quick changes without leaving
  the queue.
- **Nav drawer (left)** — the mobile navigation surface behind the hamburger.
- **Modal** — a centred "New ticket" dialog with scrim, `Esc`-to-close, and a working create that
  adds a row, routes to the queue, and fires a toast.
- **Inline edit** — two kinds: editable table cells (the selects) and a **click-to-edit** field
  (the display name in Settings swaps to an input with Save/Cancel).
- **Inputs** — text, search, `<select>`, textarea, **toggle switch**, **segmented control**,
  **stepper** (+/−), and **filter chips** — all keyboard-usable with visible focus.
- **Status / priority chip**, **toast** (semantic, auto-dismiss), **SLA card & gauge**, and the
  **agent load** bars.

## 10. Motion

Motion is quiet and quick (**160–280ms**, natural easing): a fade on page change, a slide for the
drawers, a fade-scale for the modal, a spring-in for toasts, and press feedback on buttons. The one
expressive touch is the **signal ring** — a slow 2.4s pulse on genuinely live markers. Everything is
transform/opacity for smoothness, and **`prefers-reduced-motion` collapses all of it** (including the
pulse) to near-instant. Motion never gates input.

## 11. Accessibility

- **Calm, not faint** — body and status text clear WCAG 2.1 AA on their real tinted surfaces in
  **both** editions; the signal-pair tokens are chosen so a chip's ink holds on its own fill.
- **Never colour-only** — priority and status always pair colour with a label (and dot).
- **Full keyboard operability** — logical order, a visible 2px violet focus ring on every
  interactive element, `Esc` closes modal/drawer/nav, native `<select>`/`<button>` throughout.
- **Labelled** — icon-only buttons carry `aria-label`; toggles use `role="switch"` + `aria-checked`;
  toasts are `role="status"` live regions; the search and every field are labelled.
- **Touch first on mobile** — targets ≥ 44px; no hover-only affordances.
- **Honest states** — empty (filtered queue / no accounts), success, and gentle-warning states are
  all designed.

## 12. Tokens in Practice

Light under `:root`, dark under `html.dark`; the Daylight → Nightwatch edition is one class swap:

```css
:root     { --canvas:#F6F6FB; --surface:#FFFFFF; --ink:#1C1A2E; --accent:#6D5CE7;
            --line:#E9E7F3; --line-2:#D6D2EA;
            --accent-bg:#ECE9FC; --accent-ink:#5A48C9; /* … Daylight */ }
html.dark { --canvas:#0E0D18; --surface:#1A1826; --ink:#ECEAF6; --accent:#8B7BF0;
            --line:#2C2A3E; --line-2:#3B3853;
            --accent-bg:#2A2547; --accent-ink:#BDB2F8; /* … Nightwatch */ }
```

Priority, status, amber, ok and critical are all **paired tokens** (`--x-bg` / `--x-ink`), so a
chip, an inline `<select>`, a table cell, and a chart slice all read the same source and stay AA in
both editions. No raw hex in components, no magic spacing, no one-off durations.

> **Note — chrome separators & inline styles.** App chrome (sidebar edge, top bar) uses `--line-2`
> via a CSS rule, and the inline `<select>` colours are set with **`background-color` / `color` /
> `border-color`** (never the `background` shorthand), so the class-based dropdown-chevron
> `background-image` is not clobbered. Keep structural borders in classes; keep dynamic status tints
> as discrete properties.

## 13. Anti-Patterns Beacon Forbids

- ❌ **A wall of red badges.** Colour is reserved for the signal system; urgency is shown once, not
  everywhere.
- ❌ **Ticket numbers instead of people.** Names, faces, and CSAT are first-class; IDs are secondary.
- ❌ **Colour-only status** with no label or dot.
- ❌ **Saturated colour on large fills** — the calm comes from the soft-lilac canvas; big surfaces
  stay quiet.
- ❌ **A phone mock floating in a desktop window** — the demo is one responsive layout.
- ❌ **Placeholder-as-label** in forms, or clearing a form on a validation miss.
- ❌ **Decorative violet** — it is the brand and primary action, not a highlighter.
- ❌ **Motion overload** — one signal ring, quiet transitions, and reduced-motion honoured.

## 14. Pre-Ship Checklist

- [ ] Excellent on desktop **and** phone; reflows at ~375 / ~768 / ≥1280px; no phone-in-a-window.
- [ ] Every nav item (Overview, Tickets, Customers, Reports, Settings) routes to a real, populated page.
- [ ] BI dashboard with KPI tiles, line + bar + doughnut charts, an SLA gauge, and a data table.
- [ ] Signal system consistent (colour + label + dot) across chips, tables, inline selects, and charts.
- [ ] Inline edits work: editable priority **and** status cells + click-to-edit display name.
- [ ] Edit drawer (draft Save/Cancel), mobile nav drawer, and New-ticket modal all work; modal adds a
      row + toast.
- [ ] Full input range present: text, search, select, textarea, toggle, segmented, stepper, chips.
- [ ] Targets ≥ 44px; visible focus; never colour-only; AA contrast in Daylight **and** Nightwatch.
- [ ] Charts re-render on edition swap and tab activation; hidden canvases guarded.
- [ ] `Esc` closes overlays; toasts are live regions; `prefers-reduced-motion` respected.

---

> **Colophon.** Set in Manrope and DM Mono. Beacon is one theme in the
> [`my-themes`](../../README.md) gallery — the calm, human, support-desk counterpart to the
> operational systems Meridian, Broadsheet, and Frontline.
