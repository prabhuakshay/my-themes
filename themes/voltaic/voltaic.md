# Voltaic — Theme Design Specification

> **Version 1.0** · Dark-forward control-room design system for grid & energy operations · Control Room + Day Board editions
> Tagline: **"The control gauge — every reading at a glance, every alarm in its place."**

Most enterprise UI is a form on a white page. **Voltaic is an instrument.** It is a design system
for the people who watch the grid — dispatch operators, substation engineers, and energy-network
control desks — where a number is never just a number but a *reading against a limit*, and where a
colour on screen means a breaker is about to trip. Voltaic is built around **the control gauge**:
radial load dials, a five-level alarm-severity system, and a charcoal SCADA chrome lit by electric
lime and amber. It is **dark-forward** — the Control Room edition is the hero, tuned for a dim
24/7 desk — with a fully legible Day Board edition for daylight walkthroughs.

> **A new pole.** The gallery already ships **Meridian** (a flat Carbon instrument panel),
> **Broadsheet** (a flat editorial front page), and **Frontline** (a tactile, hi-vis field app —
> light-forward). Voltaic is the deliberate **dark, monitoring** pole: a charcoal control surface
> where light content sits on a dark frame, gauges are the hero, and severity — not workflow
> status — is the organizing system. §2 maps the contrast.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Voltaic vs. the others](#2-voltaic-vs-the-others)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [The Alarm-Severity System](#5-the-alarm-severity-system)
6. [Typography](#6-typography)
7. [Responsive Layout](#7-responsive-layout)
8. [Elevation, Radius & Surfaces](#8-elevation-radius--surfaces)
9. [Components & Patterns](#9-components--patterns)
10. [The Gauge](#10-the-gauge)
11. [Motion](#11-motion)
12. [Accessibility](#12-accessibility)
13. [Tokens in Practice](#13-tokens-in-practice)
14. [Anti-Patterns Voltaic Forbids](#14-anti-patterns-voltaic-forbids)
15. [Pre-Ship Checklist](#15-pre-ship-checklist)

---

## 1. Design Principles

Seven principles. When two conflict, the **earlier** wins.

### P1 — The gauge is the interface
A grid is monitored, not browsed. The primary object is a **reading against a limit** — load
versus firm capacity, frequency versus nominal, margin versus minimum. Voltaic makes that
relationship the hero: radial gauges and bounded bars show *where a value sits in its safe range*
at a glance, before any digit is read.

### P2 — Dark-forward, built for the desk
The Control Room edition is the default, not an afterthought. A 24/7 monitoring desk runs in low
light; a dark surface reduces glare and lets the electric-lime accent and severity colours *emit*
rather than sit flat. Day Board (light) is a first-class alternate — never a downgrade — for
daylight and shared screens.

### P3 — Severity is the system
Every stateful thing — a substation, an asset, an alarm, a gauge — carries one of **five severity
levels** (Normal, Warning, Alarm, Critical, Offline). Colour, label, and shape always travel
together and mean exactly the same thing in a chip, a table cell, a banner, and a gauge (§5).
Colour is never decorative; it reports condition.

### P4 — Calm until it matters
A control room that cries wolf gets ignored. At rest, Voltaic is quiet, dim, and even. Attention is
*earned* by severity: an active alarm raises a banner, a badge, and a bright edge — and nothing
else competes for it. The louder the state, the louder the pixel; a nominal grid is nearly silent.

### P5 — Instrument-grade legibility
Readings are set in a monospaced face with **tabular figures** so digits line up and never jitter
as they tick. Numbers, codes, timestamps, and setpoints are all mono; prose is not. Alignment is
how an operator scans a wall of values without reading each one.

### P6 — Responsive, never mobile-only
One console, two shapes. On a monitor it is a full dispatch board — sidebar, gauge cluster, dense
tables. On a phone it reflows to a single column with a nav drawer and thumb-reachable actions, so
an on-call engineer gets the same truth from a bedside phone. *A desktop mimic squeezed onto a
phone is a failure.*

### P7 — Live and honest
The board reads as live — a polling frequency, a ticking clock, a pulsing SCADA-link dot — and it
never fakes it. Offline sites show `OFFLINE`, not a stale value; empty queues say "grid nominal";
staged changes say "apply at next dispatch window". The operator always knows what is real.

---

## 2. Voltaic vs. the others

| Axis | Meridian | Broadsheet | Frontline | **Voltaic** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **The control gauge** |
| Primary surface | Flat, light | Flat, light | Tactile, light-forward | **Dark, charcoal SCADA** |
| Default edition | Light | Light | Field (light) | **Control Room (dark)** |
| Organizing system | Density | Editorial hierarchy | Operational status | **Alarm severity** |
| Hero element | Data grid | Headline | Status + glance | **Radial load gauges** |
| Palette | Carbon gray | Tinted newsprint | Hi-vis + safety orange | **Charcoal + electric lime + amber** |
| Type | IBM Plex Sans/Mono | Fraunces/Archivo | Saira + Martian Mono | **Red Hat Display + Red Hat Mono** |
| Domain | Enterprise BI | Financial editorial | Field service / logistics | **Grid & energy monitoring** |

Use Voltaic for SCADA-style monitoring, energy and utility dashboards, NOC/telemetry consoles,
industrial control, and any product whose job is to watch live values against limits.

---

## 3. Brand & Voice

Voltaic sounds like a **calm dispatcher on a night desk**: precise, terse, unalarmed even while
reporting an alarm. Readings are stated as facts against limits ("81% capacity", "118 °C",
"min 15%"). Actions are single imperatives ("Acknowledge", "Save changes", "New rule"). States are
honest and specific ("grid nominal", "queue clear", "apply at next dispatch window"). No cheer, no
jargon, no exclamation — an operator reading a wall of numbers needs the fact, not the flourish.
The brand mark is an **electric-lime bolt on charcoal**: a live circuit, energized.

---

## 4. Color System

Two editions, one token set. **Control Room** (dark) is the hero; **Day Board** (light) the
daylight alternate. Every value is a role token, so the swap is a single class on `<html>`.

### Control Room edition (dark) — default

| Role | Token | Value |
| --- | --- | --- |
| App background | `--canvas` | `#0C0F13` |
| Surface (cards) | `--surface` | `#14181D` |
| Inset surface (fields, steppers) | `--surface-2` | `#1B2129` |
| Hairline (cards) | `--line` | `#262D35` |
| Structural separator (chrome) | `--line-2` | `#333C46` |
| Primary text | `--ink` | `#E7ECEF` |
| Secondary text | `--ink-2` | `#9CA7B0` |
| Caption | `--ink-3` | `#6C7783` |
| Chrome (sidebar + top bar) | `--chrome` | `#090C0F` |
| Chrome seam | `--chrome-line` | `#20262E` |
| Brand (electric lime) | `--accent` | `#A3E635` |
| Lime text on dark | `--accent-ink` | `#A3E635` |
| Text/icon on a lime fill | `--on-accent` | `#0C0F13` |

### Day Board edition (light) — alternate

The chrome stays **dark charcoal** even in Day Board — a lit SCADA frame around light content, so
the identity survives the edition swap:
`--canvas #F7F9FA`, `--surface #FFFFFF`, `--surface-2 #F0F3F5`, `--ink #14181D`,
hairlines `#E4E9ED` / separators `#C7D0D7`, `--chrome #14181D`. The lime brand darkens to
`--accent #84CC16` for fills and to **`--accent-ink #4D7C0F`** for text on white so it clears AA.

**Rules of use.** Electric lime is the brand and primary action — used decisively (the logo, the
primary button, gauge arcs, focus rings) and never sprayed as a highlighter. A **dedicated
structural separator** (`--line-2`, applied via the `chrome-seam` class) defines the chrome — the
sidebar edge and top-bar underline — a touch stronger than card hairlines so the frame reads
clearly. Severity colours (§5) are reserved for condition and nothing else.

## 5. The Alarm-Severity System

The heart of Voltaic. **Five severity levels**, each a fixed triplet of **colour + label (+ shape)**,
used identically in severity tags, table cells, the alarm banner, gauge chips, alarm rules, and
asset condition — one vocabulary, everywhere.

| Level | Token | Control Room | Day Board | Meaning |
| --- | --- | --- | --- | --- |
| Normal | `--sev-normal` | `#4ADE80` | `#16A34A` | Nominal, within limits |
| Warning | `--sev-warning` | `#FBBF24` | `#D97706` | Watch — approaching a limit |
| Alarm | `--sev-alarm` | `#FB923C` | `#EA580C` | Action needed — over a soft limit |
| Critical | `--sev-critical` | `#F87171` | `#DC2626` | Fault / trip — over a hard limit |
| Offline | `--sev-offline` | `#94A3B8` | `#64748B` | No data / de-energized |

The tag fill is the level colour tinted at low alpha (`color-mix(... 15% ...)`) with the level
colour at full strength for text and a square status dot — so a single source token drives fill,
text, and dot, and the whole set lightens in step when the edition changes. **Severity is never
carried by colour alone**: the mono uppercase label (and the square dot) always accompany it, so
it survives colour-blindness and glare. The five levels form a strict ordering, so a filter chip
bar, a sort, and an escalation floor all speak the same scale.

## 6. Typography

Two cuts of one superfamily, chosen for a clean, engineered, instrument-panel legibility.

| Role | Typeface | Used for |
| --- | --- | --- |
| UI / display | **Red Hat Display** (400–900) | Headings, labels, buttons, body — a humanist geometric with a confident, technical voice |
| Figures / codes | **Red Hat Mono** (400–700) | Every reading, ID, code, timestamp, setpoint, table number, and severity/label tag |

- Red Hat Display's engineered geometry is the system's voice — modern, calm, and industrial
  without novelty. Headings run heavy (800–900) and tight; body sits at a sturdy 14px.
- **Red Hat Mono with `tabular-nums`** gives every number a fixed cell, so live values, gauge
  readouts, and table columns align to the pixel and never jitter as they tick.
- Hierarchy comes from **size and weight first**, colour last — the minimum contrast needed to make
  the scan order obvious. Mono uppercase micro-labels (`.lbl`, `.sev`) read as instrument legends.

## 7. Responsive Layout

One console, two shapes — driven by breakpoints, not a separate build.

- **Desktop (≥ 1024px):** persistent left **sidebar** + sticky **top status strip** (frequency,
  clock, alarm bell, edition, operator) + fluid content. The dashboard is a multi-column grid
  (KPI strip → gauge cluster → alarm banner → charts → table).
- **Tablet (≥ 640px):** grids relax to two columns; the gauge cluster wraps 2×2; tables keep
  priority columns and scroll horizontally; the sidebar persists.
- **Phone (< 1024px):** the sidebar becomes a **left nav drawer** behind a hamburger; content
  stacks to one column; the gauge cluster stacks; tables scroll horizontally with a min-width;
  every target is ≥ 44px.

The same tokens, components, gauges, and severity system render in both — only the arrangement
changes.

## 8. Elevation, Radius & Surfaces

Voltaic uses **depth sparingly and layering deliberately** — the dark edition builds hierarchy by
stacking near-black surfaces, not by heavy shadow.

- **Layered surfaces:** four steps — `--chrome` (darkest, the frame) → `--canvas` (page) →
  `--surface` (cards) → `--surface-2` (insets, fields, steppers). In Control Room these read as
  rising planes of charcoal; in Day Board as concrete → white → gray.
- **Two-level elevation:** `--shadow` for resting cards (soft, close), `--shadow-lg` for overlays
  (drawers, modals, toasts) that lift clearly above the board.
- **Radius:** `--r` 8px for cards, `--r-sm` 5px for controls, 4px for severity tags and chips —
  boxy and instrument-like rather than playful. Severity tags are deliberately rectangular: they
  read as engraved legends, not bubbles.

## 9. Components & Patterns

- **Radial gauge (§10)** — the signature: a 270° dial showing a value against its range, animated
  on load, arc colour from a token.
- **KPI tile** — mono label + oversized mono figure + trend delta (severity-coloured).
- **Charts** — area (load vs firm capacity, 24h), doughnut (energy mix), bar (generation by
  source), styled to the edition and **re-rendered on edition swap and tab activation**.
- **Data table** — sticky mono header with **click-to-sort** columns, severity cells, zebra + hover
  rows, responsive horizontal scroll; supports an **inline-editable severity `<select>`** and an
  **inline-editable numeric setpoint** that update the row optimistically.
- **Edit drawer (right)** — open a substation, edit its fields (name, region, condition, load,
  setpoint stepper, note) in place, Save/Cancel.
- **Nav drawer (left)** — the mobile navigation surface behind a hamburger.
- **Modal** — centered "New alarm rule" dialog with scrim and Esc-to-close, wiring a real create.
- **Inline edits** — an editable table cell (severity select + setpoint number) *and* a
  click-to-edit field (operator name → input with Save/Cancel).
- **Inputs** — text, search, `<select>`, textarea, toggle, segmented control, **stepper** (+/−),
  filter chips, and a numeric inline field — all touch-sized with a visible lime focus ring.
- **Severity tag**, **alarm banner**, **toast** (action feedback), and a live **SCADA-link** /
  frequency / clock indicator cluster.

## 10. The Gauge

The one place Voltaic spends boldness. Each gauge is an SVG **270° arc** (a track plus a value
arc), rotated so the gap sits at the bottom, with the reading centered in monospace. The value arc
animates from zero to its fill on mount for an instrument "power-on" sweep, and its colour is a
bound token — brand lime for energy quantities (load, renewable share), severity green for
health readings (frequency, reserve). Below sits a severity tag naming the condition in words. The
gauge answers *"where is this value in its safe range?"* before the digits are even read. Everything
around the gauge stays quiet so the dial carries the screen.

## 11. Motion

Motion is functional and quick (**120–300ms**, natural easing): the gauge power-on sweep (once, on
load), drawer slide, modal fade-scale, toast in/out, and the pulsing SCADA-link/frequency dot that
signals *live*. Transitions confirm a state change and show where a surface came from. Forbidden:
decorative loops, long entrances, and number animations that delay a reading the operator needs
now. Everything collapses under `prefers-reduced-motion` — the gauges simply render filled.

## 12. Accessibility

- **AA in both editions** — body and severity text clear WCAG 2.1 AA on their actual surfaces in
  Control Room *and* Day Board; lime is `--accent` on dark and darkens to `--accent-ink #4D7C0F`
  for text on light so it never fails.
- **Never colour-only** — severity always pairs colour with a mono uppercase label and a square
  dot; gauge readings pair the arc with the digit.
- **Keyboard-operable** — a 2px lime focus ring on every interactive element; nav items, toggles,
  and inline edits are reachable and actionable by keyboard; **Esc closes** every overlay.
- **Touch-first** — targets ≥ 44px; steppers, chips, selects, and nav all have large hit areas.
- **Announced & honest** — toasts use a polite live region; loading, empty ("queue clear"),
  offline, and error states are all designed, not left to chance.

## 13. Tokens in Practice

Dark under `html.dark` (and `:root` as the default), light under `html.light`; the Control Room →
Day Board edition is one class swap:

```css
html.dark, :root { --canvas:#0C0F13; --surface:#14181D; --ink:#E7ECEF; --accent:#A3E635;
                   --line:#262D35; --line-2:#333C46; /* … Control Room */ }
html.light       { --canvas:#F7F9FA; --surface:#FFFFFF; --ink:#14181D; --accent:#84CC16;
                   --accent-ink:#4D7C0F; --chrome:#14181D; /* … Day Board */ }
```

Severity colours are tokens too (`--sev-normal … --sev-offline`), so a tag, a table cell, a gauge
chip, and an alarm banner all read the same source — and a single `sevStyle()` helper derives the
tag's fill, text, and dot from that one variable. No raw hex in components, no magic spacing, no
one-off durations.

> **Note — chrome separators.** The chrome (sidebar edge, top-bar underline) uses `--line-2` via
> the `chrome-seam` class, *not* an inline style. Binding layout with a framework's dynamic
> `:style` while also setting borders inline can clobber the border — keep structural styling in
> classes.

## 14. Anti-Patterns Voltaic Forbids

- ❌ **A desktop mimic squeezed onto a phone** — the demo must be a real responsive layout.
- ❌ **Decorative colour** — lime and severity hues report state and action, never garnish.
- ❌ **Colour-only severity** with no label or dot.
- ❌ **Proportional figures for readings** — live values must be monospaced and tabular so they
  don't jitter.
- ❌ **A pure-black void** — the dark edition is layered charcoal, not `#000`, so surfaces read.
- ❌ **Crying wolf** — a nominal grid must be calm; attention is reserved for real severity.
- ❌ **Faking live** — offline sites show `OFFLINE`, never a stale reading.
- ❌ **Illegible lime on white** — text-on-light uses the darkened `--accent-ink`, not raw lime.

## 15. Pre-Ship Checklist

- [ ] Excellent on desktop **and** phone; reflows at ~375 / ~768 / ≥1280px; no mimic-in-a-window.
- [ ] Every nav item routes to a real, populated page (Dashboard, Substations, Alarms, Assets, Settings).
- [ ] BI dashboard with KPI tiles, ≥1 gauge readout, area + doughnut + bar charts, and a data table.
- [ ] Severity system consistent (colour + label + dot) across tags, tables, banner, gauges, rules.
- [ ] Inline edits (severity cell + numeric setpoint + click-to-edit name), edit drawer, nav
      drawer, and modal all work.
- [ ] Full input range present: text, search, select, textarea, toggle, segmented, stepper, chips.
- [ ] Charts re-render on edition swap **and** tab activation; hidden canvases guarded.
- [ ] Control Room **and** Day Board both polished; AA contrast in both, incl. lime on each surface.
- [ ] Targets ≥ 44px; visible lime focus; Esc closes overlays; never colour-only.
- [ ] Chrome separators use a class-based `--line-2`, not a clobberable inline style.
- [ ] `prefers-reduced-motion` respected — gauges render filled, no loops.

---

> **Colophon.** Set in Red Hat Display and Red Hat Mono. Voltaic is one theme in the
> [`my-themes`](../../README.md) gallery — the dark, control-room, severity-driven counterpart to
> the light desktop systems Meridian and Broadsheet and the light field app Frontline.
