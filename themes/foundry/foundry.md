# Foundry — Theme Design Specification

> **Version 1.0** · Design system for data-pipeline & ETL orchestration consoles · Blueprint + Control Room editions
> Tagline: **"Watch the metal move through the plant."**

Most data tools show you a table of runs and call it observability. **Foundry treats the pipeline
as a plant** — raw material enters at a source, flows through extract, transform, and load stages,
and comes out refined. The interface is the shop floor: a **blueprint grid** underlies every
surface, molten-**amber** flow animates the live edges of the execution graph, and every number,
run ID, and log line is set in **monospace** so it aligns like a spec sheet. It is a console for
the people who build and babysit pipelines — data and platform engineers watching throughput,
chasing a failed run, and reading stdout at 2 a.m.

> **An engineering pole.** This repository already ships an instrument panel (**Meridian**), an
> editorial front page (**Broadsheet**), a field-ops app (**Frontline**), and an entry-first BI
> system (**Vellum**). Foundry is the deliberate **orchestration / observability** pole:
> developer-facing, **blueprint-technical**, monospace-forward, and equally at home in a **dark
> control room**. §2 maps the contrast.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Foundry vs. the others](#2-foundry-vs-the-others)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [The Run-State System](#5-the-run-state-system)
6. [Typography](#6-typography)
7. [Responsive Layout](#7-responsive-layout)
8. [Elevation, Radius & Surfaces](#8-elevation-radius--surfaces)
9. [The Blueprint Grid](#9-the-blueprint-grid)
10. [Components & Patterns](#10-components--patterns)
11. [Motion](#11-motion)
12. [Accessibility](#12-accessibility)
13. [Tokens in Practice](#13-tokens-in-practice)
14. [Anti-Patterns Foundry Forbids](#14-anti-patterns-foundry-forbids)
15. [Pre-Ship Checklist](#15-pre-ship-checklist)

---

## 1. Design Principles

Six principles. When two conflict, the **earlier** wins.

### P1 — The pipeline is the picture
The organizing metaphor is a **plant**: material flows source → extract → transform → load. The
dashboard leads with the **execution graph**, not a wall of tiles. Flow is shown, not just tallied
— live edges animate, running nodes pulse, and the eye follows the material downstream.

### P2 — State is the system
Every run is in exactly one of six states (§5). Color, label, and icon travel together and mean
the same thing in a chip, a table cell, a graph node, a run-list row, and the dashboard doughnut.
Color is **never** decorative; it reports where a run is in its life.

### P3 — Numbers are monospace, and they align
Throughput, durations, row counts, run IDs, cursors, and timestamps are **tabular monospace** so
columns line up and a changing figure doesn't reflow its neighbours. An orchestration console is
read like a spec sheet — the type has to behave like one.

### P4 — The log is a first-class surface
Debugging happens in stdout. Foundry gives the **run log** a real console — fixed-width lines,
timestamped, with `INFO / OK / WARN / ERROR / DEBUG` colour-keyed to the state system — not a
tooltip or a truncated cell. Reading a failure should feel like reading the terminal you trust.

### P5 — Blueprint, not chrome
The surface is engineered, not decorated: a faint **blueprint grid** under the canvas, hairline
rules, a single molten-**amber** accent spent only on the brand, the primary action, and the flow
of material. One signature (amber flow); everything else is quiet slate.

### P6 — Two rooms, one plant
The same tokens light a **Blueprint** edition for daytime desks and a **Control Room** edition for
the night shift — a deep-navy slate room where the grid glows faintly and the amber reads like a
furnace. It is a single class swap, not a second design; both are tuned to WCAG AA.

---

## 2. Foundry vs. the others

| Axis | Meridian | Broadsheet | Frontline | Vellum | **Foundry** |
| --- | --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | Premium BI entry | **Data plant / ETL** |
| Audience | Analysts | Executives | Field crews | BI consumers | **Data & platform engineers** |
| Surface | Flat, boxed | Flat, ruled | Tactile, rounded | Soft, editorial | **Blueprint-grid slate** |
| Palette | Carbon gray | Tinted newsprint | Hi-vis + orange | Warm neutral | **Slate + molten amber** |
| Type | IBM Plex | Fraunces/Archivo | Saira/Martian | Serif + sans | **Chivo + Sometype Mono** |
| Organizing idea | Density | Editorial hierarchy | Operational status | Reading flow | **Pipeline flow + run state** |
| Signature | Governance | Provenance | Connectivity | First impression | **Execution graph + run logs** |
| Modes | White / Gray | Day / Evening | Field / Shift | Light / Dark | **Blueprint / Control Room** |

Use Foundry for ETL/ELT orchestration, data-pipeline observability, job schedulers, warehouse
ops, stream processing dashboards, and any developer-facing console where **what's flowing and
what failed** is the whole job.

---

## 3. Brand & Voice

Foundry sounds like a **staff data engineer writing a runbook**: precise, lowercase, unhurried,
allergic to hype. Nouns are the real ones engineers use — `pipeline`, `run`, `stage`, `cursor`,
`schedule`, `connection`, `throughput`. States are honest (`retrying`, `queued`, `failed`), and
numbers carry units (`18.4M rows`, `4m 12s`, `12ms`). Log lines read like real stdout
(`source handshake ok · schema fingerprint 9f21ac unchanged`). No exclamation marks, no "oops," no
cheerful filler — an engineer scanning a failure wants the fact and the fix. The mark is
utilitarian: a dark hexagon (a bolt head / a node) with a molten-amber core.

---

## 4. Color System

Two editions, one token set. **Blueprint** (light) is a cool concrete-slate room for daytime;
**Control Room** (dark) is a deep-navy operations desk for the night shift. Every value is a role
token, so the swap is a single class on `<html>`.

### Blueprint edition (light)

| Role | Token | Value |
| --- | --- | --- |
| App background (concrete) | `--canvas` | `#E9EEF2` |
| Surface (cards, chrome) | `--surface` | `#FFFFFF` |
| Inset surface | `--surface-2` | `#F1F5F8` |
| Hairline (cards) | `--line` | `#DCE3EA` |
| Structural separator (chrome) | `--line-2` | `#C2CDD8` |
| Primary text | `--ink` | `#0F1B2A` |
| Secondary text | `--ink-2` | `#46586B` |
| Caption | `--ink-3` | `#78899A` |
| Brand (molten amber) | `--accent` | `#F97316` |
| Accent tint | `--accent-soft` | `#FDEAD9` |
| Flow / steel | `--steel` | `#2563EB` |

### Control Room edition (dark)

Deep navy-slate, not pure black, so the blueprint grid can glow faintly and amber reads like a
furnace: `--canvas #0A111E`, `--surface #111C2E`, `--surface-2 #17253A`, hairlines `#22334D` /
separators `#35496B`, `--ink #E7EEF7`, `--ink-2 #99ABC4`, `--ink-3 #6E829B`. The brand brightens
to `--accent #FB8A3C` and steel to `#4C8DF6` so both stay punchy on the dark desk.

**Rules of use.** Molten amber is the **brand, the primary action, and the flow of material** —
spent decisively, never sprayed as a highlighter. A **dedicated structural separator** (`--line-2`,
a touch stronger than card hairlines) defines the app chrome — the sidebar edge and top bar — via a
CSS **class**, so the layout reads clearly and dynamic `:style` bindings can't clobber it. Card
borders stay on the lighter `--line`. Run-state colors (§5) are reserved for state.

## 5. The Run-State System

The heart of the system. Six run states, each a fixed triplet of **color + label + icon**, used
identically in table cells, list rows, graph nodes, chips, log-level keys, and the dashboard
doughnut.

| State | Token | Blueprint | Meaning |
| --- | --- | --- | --- |
| Queued | `--r-queued` | `#64748B` | Enqueued, waiting for a worker |
| Running | `--r-running` | `#2563EB` | Executing now |
| Success | `--r-success` | `#059669` | Completed, cursor advanced |
| Failed | `--r-failed` | `#DC2626` | Errored after retries |
| Retrying | `--r-retrying` | `#B45309` | Backing off, will re-attempt |
| Skipped | `--r-skipped` | `#94A3B8` | Upstream unmet, not run |

State is **never carried by color alone** — the label (and icon where space allows) always rides
with it. Chips tint the state color at ~14% alpha for the fill and use it at full strength for
text, holding AA contrast on both editions. In Control Room all six lighten in step
(`--r-running #4C8DF6`, `--r-success #10B981`, `--r-failed #F87171`, `--r-retrying #F59E0B`, …).
The **run-log levels** map onto the same palette: `INFO`→running-blue, `OK`→success-green,
`WARN`→retrying-amber, `ERROR`→failed-red, `DEBUG`→caption-gray.

## 6. Typography

Two typefaces, chosen for an engineered, spec-sheet legibility.

| Role | Typeface | Used for |
| --- | --- | --- |
| UI / display | **Chivo** (400/500/700/900) | Headings, page titles, labels, buttons, body |
| Figures / logs / codes | **Sometype Mono** (400/500/700) | Every number, run ID, timestamp, schedule, and the run-log console |

- **Chivo** is a grotesque with a mechanical, slightly industrial cut — confident and neutral
  enough to carry a dense console without shouting; its `900` weight anchors page titles.
- **Sometype Mono** gives tabular alignment and a terminal feel to every figure and identifier;
  `.tnum` (tabular numerals) keeps changing values from reflowing their neighbours.
- Hierarchy is by **size and weight** first, color second: page titles 22–26px/900, section
  headings 14–15px/700, a 13–14px body, and 10–11px monospace small-caps labels
  (`letter-spacing: .12em`) for the technical kicker line.

## 7. Responsive Layout

One app shell, two shapes — driven by breakpoints, not a separate build.

- **Desktop (≥ 1024px):** persistent left **nav sidebar** (Console + Datasets, with a scheduler
  status footer) + sticky **top bar** (environment switcher, global search, edition toggle, Run
  all) + fluid content. The dashboard is a multi-column grid: KPI strip → execution graph →
  charts → recent-runs table.
- **Tablet (≥ 640px):** KPI and chart grids relax to two columns; tables keep priority columns and
  scroll horizontally; the graph lane scrolls within its panel.
- **Phone (< 1024px):** the sidebar becomes a **left nav drawer** behind a hamburger; content
  stacks to one column; the Runs page stacks the run list above the log console; the execution
  graph scrolls horizontally. Targets stay ≥ 44px.

## 8. Elevation, Radius & Surfaces

Foundry is **flat and engineered** — depth is used sparingly and only to lift what floats.

- **Two-level elevation:** `--shadow-card` for resting cards (soft, 1–3px, barely there) and
  `--shadow-pop` for overlays (drawer, modal, dropdown, toasts) that clearly lift above the plant.
- **Radius:** `--radius` 6px for cards, controls, and chips; `--radius-sm` 4px for inner
  elements. Tight, mechanical corners — a spec sheet, not a pill.
- **Surfaces:** three levels — `--canvas` (blueprint concrete) → `--surface` (cards & chrome) →
  `--surface-2` (insets, fields, steppers). The run-log console goes one step darker still in
  Control Room (`#0C1524`) to read like a real terminal.

## 9. The Blueprint Grid

Foundry's signature texture — a Foundry-specific concern.

- **A faint engineering grid** underlies the canvas (`.blueprint`) and the execution-graph panel
  (`.blueprint-panel`), drawn from the `--line` token so it **re-tints per edition** and glows
  faintly in Control Room. It is always *behind* content, never competing with it.
- **The grid is tasteful, not literal graph paper.** 28px cells on the canvas, 24px inside the
  graph panel, hairline weight, low contrast — enough to say "engineering surface," never enough
  to reduce legibility.
- **Flow lives on the grid.** The execution graph draws nodes on the grid and animates molten-amber
  **flow dots** along the edges between them, with running nodes pulsing — the one place boldness
  is spent.

## 10. Components & Patterns

- **Execution graph (DAG lane)** — the dashboard hero: source → extract → transform → load nodes,
  each state-bordered, with animated flow edges and a pulsing running node.
- **KPI tile** — small-caps label + oversized monospace figure + trend delta + inline sparkline;
  the glance layer above the graph.
- **Charts** — line/area (throughput), bar (run duration), doughnut (runs by state), styled to the
  edition, re-coloured from tokens and re-rendered on edition swap and tab activation.
- **Data table** — small-caps sortable-looking headers (with real click-to-sort), state cells,
  zebra + hover, responsive scroll; supports **two inline-editable cells** — a schedule `<select>`
  and a state `<select>` — that update the row optimistically and toast.
- **Run log console** — fixed-width, timestamped, colour-keyed stdout with its own darker surface.
- **Edit drawer (right)** — open a pipeline, edit name/route/schedule/state/concurrency/description
  in place, Save/Cancel. The "app drawer edit" pattern for quick changes without leaving the list.
- **Nav drawer (left)** — the mobile navigation surface behind a hamburger.
- **Modal** — centered "new pipeline" dialog with scrim and Esc-to-close, wired to create + toast.
- **Inline edit** — click-to-edit fields (settings display name, connection name) that swap to an
  input with Enter/Esc; plus the two editable table cells.
- **Inputs** — text, search, select, textarea, toggle/switch, segmented control, **stepper** (+/−),
  filter chips, and numeric inline fields — all keyboard-usable with a 2px amber focus ring.
- **Run-state chip**, **environment switcher**, **toast** (action feedback), and a persistent
  **scheduler-status** footer.

## 11. Motion

Motion is functional and quick (**120–240ms**, standard ease): the flow dots along graph edges,
the running-node pulse, drawer slide, modal fade-scale, toast in/out, dropdown origin-transitions,
and control hovers. The one sustained animation — **amber material flowing downstream** — is the
signature and earns its keep by showing the plant is live. Forbidden: decorative loops elsewhere,
long entrances, and number animations that delay a figure an engineer needs *now*.
`prefers-reduced-motion` collapses all of it to near-instant.

## 12. Accessibility

- **AA on both editions** — body, caption, and state text clear WCAG 2.1 AA on their actual
  surfaces (including tinted chips and the blueprint grid) in Blueprint **and** Control Room.
- **Never color-only** — every run state pairs its color with a label (and icon where space
  allows); log levels are spelled out (`ERROR`, not just red).
- **Full keyboard operability** — a 2px amber focus outline on every interactive element; Esc
  closes modal, drawer, nav, and the environment dropdown; toggles are reachable and Enter-usable;
  logical tab order.
- **Semantic + labelled** — icon-only buttons carry `aria-label`, selects carry per-row labels,
  toggles use `role="switch"` with `aria-checked`, toasts live in an `aria-live` region, and the
  nav marks the current page with `aria-current`.
- **Targets ≥ 44px** on touch; the grid never traps focus or blocks zoom.

## 13. Tokens in Practice

Light under `:root`, dark under `html.dark`; the Blueprint → Control Room edition is one class swap:

```css
:root     { --canvas:#E9EEF2; --surface:#FFFFFF; --ink:#0F1B2A; --accent:#F97316;
            --line:#DCE3EA; --line-2:#C2CDD8; /* … Blueprint */ }
html.dark { --canvas:#0A111E; --surface:#111C2E; --ink:#E7EEF7; --accent:#FB8A3C;
            --line:#22334D; --line-2:#35496B; /* … Control Room */ }
```

Run-state colors are tokens too (`--r-queued … --r-skipped`), so a chip, a table cell, a graph
node, a log-level key, and a chart slice all read the same source. Charts re-read the computed
tokens on every render, and a `MutationObserver` on the `<html>` class re-renders them (and
re-runs `lucide.createIcons()`) the instant the edition flips. No raw hex in markup, no magic
spacing, no one-off durations.

> **Note — chrome separators.** App chrome (sidebar edge, top bar, drawers) uses `--line-2` via a
> CSS **class**, not an inline style. Binding layout with Alpine's dynamic `:style` while also
> setting a border inline can clobber the border — structural styling stays in classes.

> **Note — Alpine `<select>` options.** State/schedule `<option>`s are written **statically**, not
> generated with `x-for`. `x-model` initializes before an `x-for` option list exists, so the
> control would render its first option for every row — static options bind correctly.

## 14. Anti-Patterns Foundry Forbids

- ❌ **A table of runs as the whole dashboard** — lead with the flow, the execution graph.
- ❌ **Proportional numbers** — every figure, ID, and timestamp is tabular monospace.
- ❌ **Color-only state** with no label or icon.
- ❌ **Amber as decoration** — it is the brand, the primary action, and the flow, nothing else.
- ❌ **A log stuffed into a tooltip or a truncated cell** — stdout gets a real console.
- ❌ **Graph-paper so loud it fights the content** — the blueprint grid stays a whisper.
- ❌ **A dark mode that's just an inverted light mode** — Control Room is designed, AA-tuned tokens.
- ❌ **Motion everywhere** — one signature (amber flow); everything else is still.

## 15. Pre-Ship Checklist

- [ ] Excellent on desktop **and** phone; reflows at ~375 / ~768 / ≥1280px; no phone-in-a-window.
- [ ] Every nav item routes to a real, populated page (Dashboard, Pipelines, Runs, Connections, Settings).
- [ ] BI dashboard with KPI tiles, line/area + bar + doughnut charts, and a data table.
- [ ] Run-state system consistent (color + label + icon) across chips, tables, graph, list, logs, and charts.
- [ ] Two inline edits (editable table cell + click-to-edit field), edit drawer, nav drawer, and modal all work.
- [ ] Run log is a real monospace console with colour-keyed levels.
- [ ] Full input range present and keyboard-usable; visible amber focus; Esc closes overlays.
- [ ] Blueprint **and** Control Room editions both polished; charts re-colour and re-render on swap.
- [ ] Targets ≥ 44px; never color-only; AA contrast in both editions incl. tinted surfaces.
- [ ] Chrome separators use a class-based `--line-2`; `<select>` options are static.

---

> **Colophon.** Set in Chivo and Sometype Mono. Foundry is one theme in the
> [`my-themes`](../../README.md) gallery — the blueprint-technical, monospace-forward,
> orchestration-and-observability counterpart to the analyst, executive, field, and BI systems
> alongside it.
