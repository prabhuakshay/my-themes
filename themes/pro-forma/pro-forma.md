# Pro Forma — Theme Design Specification

**The model is the product.** Pro Forma is a driver-based financial-modeling design system for
**FP&A** — the people who build the plan, not the ones who close the books. It is built for the
analyst who lives in a spreadsheet: where a number is never typed, it is **derived**; where the
organizing truth is not a statement but an **assumption**; and where the hero surface is not a
report but a **live worksheet** — an editable driver grid whose every keystroke recomputes revenue,
EBITDA, cash, and a sensitivity tornado in real time.

- **Metaphor:** the spreadsheet re-imagined — a graph-paper worksheet of assumptions → outputs, with
  a live formula bar across the top.
- **Editions:** **Model** (light, hero — modeling is worksheet-first) and **Terminal** (dark,
  after-hours). One class swap on `<body>`.
- **Type:** DM Sans (UI) + DM Mono (every figure, formula, and driver cell).
- **Signature:** the **live formula bar** and an **editable driver grid** that recomputes a 12-month
  model on every edit; formula-indigo is the brand; mint/rose positive/negative is the semantic core.

---

## Table of Contents

1. Design Principles
2. Pro Forma vs. the others
3. Brand & Voice
4. Color System
5. The Driver Model (signature)
6. Typography
7. Responsive Layout
8. Elevation, Radius & Surfaces
9. Components & Patterns
10. The Driver Grid
11. Motion
12. Accessibility
13. Tokens in Practice
14. Anti-Patterns Pro Forma Forbids
15. Pre-Ship Checklist

---

## 1. Design Principles

### P1 — The model is the interface
The centerpiece is not a chart or a statement — it is a **worksheet of assumptions**. Drivers are
editable cells; outputs are formulas. You steer the business by editing a value, not by reading a
report. Every screen is downstream of the driver grid.

### P2 — Everything recomputes, live
No value is hard-typed. Revenue is `Price × Volume × (1 − Churn) + New logos × Price`; EBITDA falls
out of gross margin less headcount load; cash rolls from EBITDA less capex. Edit any driver and the
KPI tiles, the projection, the cost mix, and the sensitivity tornado all recompute in the same frame.
A **"Balances"** badge is a promise the formula bar keeps.

### P3 — Assumptions are first-class objects
A driver isn't a number in a cell — it's a record with a name, a unit, a role in the formula, bounds
(min/base/max), a category, and a note. It can be edited in place (the cell), managed in a register
(the Drivers page), or opened in full (the edit drawer). The plan is only as good as its assumptions,
so assumptions get the respect of real objects.

### P4 — Worksheet-first, but terminal-capable
Modeling happens on graph paper in a bright room. **Model (light)** is the hero — a literal
graph-paper canvas. **Terminal (dark)** is a first-class alternate for late-night scenario work — a
full token swap, never a dimmed screenshot.

### P5 — Tabular, never jittery
Figures, formulas, and driver cells are monospaced and tabular-lined, so a column of numbers never
shifts as values change. Negatives use a true minus (−); the formula bar reads like code.

### P6 — Sensitivity is the second signature
A plan without a sensitivity read is a guess. Every driver carries an inline EBITDA-swing bar, and a
**tornado** ranks drivers by how far a ±10% move pushes EBITDA. What-if is one stepper away.

### P7 — Responsive, never mobile-only
The same tokens power a full modeling console on a monitor and a glanceable app on a phone: the
driver grid scrolls horizontally, KPI tiles reflow, and navigation collapses to a drawer.

---

## 2. Pro Forma vs. the others

The gallery already holds an *instrument panel* (Meridian), a *financial front page* (Broadsheet),
and a *field/operations app* (Frontline). Pro Forma is the **FP&A / driver-model** pole — the plan
being built, not the actuals being reported.

| | Meridian | Broadsheet | Frontline | **Pro Forma** |
| --- | --- | --- | --- | --- |
| Domain | Enterprise ops | Enterprise data / editorial | Field operations | **FP&A / financial modeling** |
| Metaphor | Instrument panel | Financial front page | Ops app | **The spreadsheet / worksheet** |
| Organizing system | Modules & meters | Columns & rules | Work orders | **Drivers → outputs** |
| Hero element | Dashboard grid | Front page | Job cards | **Live driver grid + formula bar** |
| Default edition | Light (cool gray) | Light (newsprint) | Light (hi-vis) | **Model (light, graph paper)** |
| Palette | Carbon gray + blue | Tinted newsprint + claret | Concrete + safety orange | **Graph-paper green-gray + formula indigo** |
| Type | IBM Plex Sans/Mono | Fraunces + Archivo + mono | Saira + Martian Mono | **DM Sans + DM Mono** |

Pro Forma is the only theme whose hero is an **editable, live-recomputing worksheet** — not a
dashboard, a page, or a job list. Its metaphor (spreadsheet), its type voice (DM Sans/Mono), its
structure (assumptions → outputs), and its palette (graph-paper green-gray + indigo) are each a
distinct pole from the existing three.

---

## 3. Brand & Voice

- **Name:** *Pro Forma* — the accounting term for a projected, "as-if" statement. The plan, not the
  actuals.
- **Voice:** precise, analytical, unfussy. Labels are FP&A English (ARPU, churn, EBITDA, sensitivity,
  driver, scenario). No hype, no emoji. Figures are always "illustrative · not guidance."
- **Tagline:** *The model is the product.*
- **Logo:** a spreadsheet-cell glyph in formula indigo on worksheet-ink — a grid with a `→` output
  arrow, the assumption-to-output pipeline in one mark. The header carries an `fx` badge.

---

## 4. Color System

Every value is a CSS custom property. The edition class lives on `<body>` (bare `.light` / `.dark`),
so the tokens cascade to the whole subtree — including overlays like the modal, the edit drawer, and
Chart.js (which reads them through `getComputedStyle(document.body)`).

### Model edition (light) — default
```css
--canvas:#F6F8F4;  --surface:#FFFFFF;  --surface-2:#EFF3EB;
--grid:#E9EFE3;    --line:#E1E8DB;     --line-2:#C8D3BF;    /* the graph paper */
--ink:#1A1F17;     --ink-2:#54604B;    --ink-3:#8B9682;
--chrome:#181C13;  --chrome-2:#242A1D; --chrome-line:#31382A;  /* worksheet ink chrome */
--accent:#3B5BDB;  --accent-2:#2F49B0; --accent-ink:#2F49B0;   /* formula indigo */
--link:#2F49B0;
--pos:#0F8F80;     --neg:#C43A4D;      --flat:#6C7860;  --warn:#9A7413;
```

### Terminal edition (dark) — alternate
```css
--canvas:#10130C;  --surface:#171B11;  --surface-2:#1F2418;
--grid:rgba(255,255,255,.032); --line:#272E1D; --line-2:#38412A;
--ink:#EAEEE2;     --ink-2:#A4AF97;    --ink-3:#6E7962;
--chrome:#0C0F08;  --chrome-2:#171B11; --chrome-line:#242A1A;
--accent:#6C86F0;  --accent-2:#87A0F5; --accent-ink:#8DA2F3;
--link:#8DA2F3;
--pos:#2CC4B0;     --neg:#E7677A;      --flat:#96A188;  --warn:#DFB24E;
```

**Contrast (WCAG 2.1 AA).** Body ink on both canvases clears 4.5:1. The indigo fill uses white text
(`--on-accent`) for AA; indigo *text* uses the darker `--accent-ink` on light surfaces. Positive and
negative are validated on their own soft-tinted chip backgrounds in both editions, and never carry
meaning by hue alone — a sign (+/−) and an arrow icon accompany the color.

---

## 5. The Driver Model (signature)

Pro Forma's semantic core is **assumption → output**, computed once and read everywhere.

```js
// each driver is a record; the model is a pure function of the driver values
calc(d) {
  const months = simSeries(d, 12);              // month-by-month customer recursion
  const rev = months.reduce((s,x)=>s+x, 0);
  const grossPct = clamp(78 + (d.volume-4200)/4200*4 - (d.churn-2.4)*1.6, 66, 86);
  const opex = d.headcount * d.salaryLoad;
  const ebitda = rev*grossPct/100 - opex;
  const netIncome = (ebitda - da) * (1 - d.taxRate/100);
  const cashEOP = 15000 + ebitda*0.68 - d.capex;
  return { rev, months, grossPct, opex, ebitda, netIncome, cashEOP, /* … */ };
}
```

Because `model`, `kpis`, `sens`, `costMix`, `pnl`, and `scenarioRows` are all **getters** over the
same `calc`, one keystroke in a driver cell flows to every surface. Sensitivity is the same function
run twice per driver (±10%); a scenario is the same function run over a **preset** of driver values.
The **formula bar** renders that formula literally, ending in the live modeled revenue — the code and
the result on one line.

---

## 6. Typography

- **UI / display:** DM Sans (400–700). A geometric, engineered grotesk — precise without being cold,
  distinct from the gallery's Plex, Fraunces, and Saira voices.
- **Figures / mono / formulas:** DM Mono, `font-variant-numeric: tabular-nums`, slight negative
  tracking. Every currency figure, driver value, unit, formula token, and axis tick is mono so
  worksheet columns line up.
- **Labels:** mono, 10px, uppercase, `.13em` tracking — the field labels of a model schedule.
- **Formula bar:** mono, with operators in indigo and operands in bordered "token" chips — the plan's
  governing equation, set like code.

---

## 7. Responsive Layout

- **≥1280px:** worksheet-ink sidebar (240px) + top bar; driver grid + sensitivity in a 3-col grid;
  KPI tiles in a 4-up strip; the graph-paper canvas behind it all.
- **768–1279px:** sidebar persists; grids fold to 1–2 columns; tiles 2-up.
- **<768px:** sidebar → **mobile nav drawer** (hamburger); tiles 2-up; every grid/table gets a
  horizontal scroll container so driver cells never crush; the edit drawer and modal go full-width.
- Shell is `h-screen` with an internally-scrolling `<main>`, so the ink chrome stays pinned and no
  panel grows unbounded. Touch targets ≥ 44px; the +/− stepper cells are thumb-sized.

---

## 8. Elevation, Radius & Surfaces

- **Radius:** `--r: 9px` (cards, panels), `--r-sm: 6px` (controls, chips, cells). Calm, worksheet-neat.
- **Surfaces:** `--canvas` (graph paper) → `--surface` (cards/grid) → `--surface-2` (insets, fields,
  cells, zebra). Hairlines use `--line`; structural rules and cell borders use the stronger
  `--line-2`; the grid backdrop uses the dedicated `--grid` token; chrome seams use `--chrome-line`.
- **Shadow:** low and cool on light; deeper on dark. Overlays (modal, drawer) use `--shadow-lg`.

---

## 9. Components & Patterns

- **App shell** — pinned worksheet-ink sidebar + top bar with a period segmented control
  (Monthly/Quarterly), a plan-period chip, a "MODEL v3.2 · recomputed live" pill, a global **New
  driver** button, the edition toggle, and a scenario selector. Every one of the 7 nav items routes
  to a distinct, populated page.
- **KPI tiles** — value, a vs-prior chip, and a vs-prior sparkline — all recomputed from the model.
- **Formula bar** — the signature: the governing equation set as indigo-operator tokens, ending in
  the live modeled revenue and a "Balances" badge.
- **Driver grid** — the editable worksheet (see §10).
- **Data tables** — the driver register and the scenario/sensitivity tables: mono figures, status
  chips, zebra + hover, responsive scroll, sortable-looking headers, and inline-editable cells.
- **Inputs** — text (rename, driver name, recipients), search (driver register), `<select>` (scenario,
  category, currency), textarea (notes), **toggle switch** (apply-to-forecast, lock, auto-recompute),
  **segmented control** (period, horizon, units), **+/− stepper** (driver cells, base value, shock,
  decimals), **filter chips** (driver category, driver tags), and numeric/inline-editable driver
  cells. All keyboard-usable with a visible indigo focus ring.
- **Modal** — a centered **New Driver** dialog: scrim, Esc-to-close, name, category, unit, a stepper
  base value, a growth stepper, a note textarea, tag chips, a lock/recurring toggle, and a working
  **Add driver** → appends to the grid + recomputes + toast.
- **Edit drawer** — a right-hand **Edit driver** drawer opened by clicking a register row: editable
  name, unit, category, base value (stepper), min/max bounds, formula fragment, an in-range check, a
  note textarea, an apply-to-forecast toggle, and Save/Cancel that writes back and triggers the
  12-month recompute.
- **Inline edits** — the editable numeric driver cells (with +/− steppers), plus a **click-to-edit
  model name** (Overview heading and Settings) that becomes an input with Save/Cancel.
- **Feedback** — toasts for every action; positive/negative/warn/neutral **chips** from one token
  set; inline sensitivity mini-bars.

---

## 10. The Driver Grid

The hero pattern. Each row is an **assumption record**; each numeric cell is a live spreadsheet cell:

- **The cell** (`.cell`) — a bordered `--surface-2` group with a `−` button, a right-aligned mono
  numeric input, and a `+` button. It shows an indigo focus ring when active; +/− respect the
  driver's `step`, `min`, and decimal precision.
- **Role in formula** — a mono fragment (e.g. `× per customer / mo`) with the operator in indigo, so
  you read how the driver enters the equation.
- **vs prior** — a context-aware chip: for a "good-up" driver an increase is positive; for churn or
  cost an increase is negative; headcount is directional-neutral.
- **EBITDA sensitivity** — an inline mini-bar plus the dollar swing, scaled to the largest driver.
- **Footer** — the reconciled outputs: modeled revenue, gross margin, EBITDA.

The full register (Drivers page) adds a category column, category filter chips, a search box, and a
per-row edit affordance that opens the drawer. Editing any cell — on any page — recomputes the model.

---

## 11. Motion

Restrained and functional. Overlays fade/scale in ~200ms; the drawer and mobile nav slide; toasts
rise and auto-dismiss. **Charts do not animate** (`animation:false`) — a data-first worksheet draws
instantly, which also removes any first-frame render race and lets a driver edit recompute a chart
without a distracting sweep. Hover/active transitions are 120ms. `prefers-reduced-motion` disables
all transitions and animations.

---

## 12. Accessibility

- WCAG 2.1 AA contrast on real surfaces in both editions, including tinted chip backgrounds.
- Direction never by color alone — sign, arrow icon, and label reinforce every positive/negative.
- Visible focus ring (`--accent`, 2px, offset) on every interactive element; driver cells show a ring
  on `:focus-within`.
- Esc closes the modal, edit drawer, and mobile nav (`@keydown.escape.window="closeAll()"`).
- Toggles expose `role="switch"` / `aria-checked`; icon-only buttons and cell steppers carry
  `aria-label`.
- Touch targets ≥ 44px; tabular figures avoid layout shift for screen-magnification users.

---

## 13. Tokens in Practice

```css
/* the graph-paper worksheet canvas */
.graph { background-image:
  linear-gradient(var(--grid) 1px, transparent 1px),
  linear-gradient(90deg, var(--grid) 1px, transparent 1px); background-size: 22px 22px; }
/* an editable driver cell */
.cell:focus-within { border-color: var(--accent); box-shadow: 0 0 0 3px var(--accent-soft); }
/* the indigo primary action / formula operator */
.btn-primary { background: var(--accent); color: var(--on-accent); }
.formula .op { color: var(--accent-ink); }
```

Because the grid, positive/negative, chrome, indigo, and surfaces are all tokens, a driver cell, a
chart bar, a sensitivity mini-bar, a KPI delta, and the formula bar all read from the same source —
and the Terminal edition is a single `body.dark`.

---

## 14. Anti-Patterns Pro Forma Forbids

- **A hard-typed output.** Never show revenue or EBITDA that isn't derived from the drivers.
- **A stale surface.** Never let a KPI, chart, or table lag the driver grid after an edit.
- **Color-only meaning.** Never rely on green/red without a sign, arrow, or label.
- **Proportional-font figures.** Never set a driver value or figure in the UI sans; cells are mono.
- **A phone mock on a desktop.** Pro Forma is a full modeling console on a monitor and an app on a phone.
- **Decorative dark mode.** Terminal is a real token swap, not a dimmed screenshot.
- **Gratuitous chart motion.** No sweeping animations between recomputes.
- **A "coming soon" nav item.** Every sidebar item is a real, populated page.

---

## 15. Pre-Ship Checklist

- [x] Four non-negotiables: distinct POV, responsive (not mobile-only), polished, token-driven & AA.
- [x] Full-fledged demo: BI dashboard (KPIs + line/area, bar, doughnut charts + data table); data
      tables with inline-editable cells; full input range (text, search, select, textarea, toggle,
      segmented, stepper, filter chips, numeric/inline); centered modal (scrim + Esc + create);
      right-hand edit drawer + left mobile nav drawer; ≥2 inline edits (driver cells + click-to-edit
      model name); toasts + status chips; persistent shell where **every** nav item routes to a real,
      populated page; light + dark editions.
- [x] The model recomputes live on every driver edit; sensitivity and scenarios derive from the same
      `calc`; the formula bar reflects the live output.
- [x] WCAG AA verified on both editions, tinted surfaces included.
- [x] Charts render on tab activation and re-render on edition swap and on every recompute; unique
      canvas ids per page; hidden canvases guarded (`offsetParent===null`); `animation:false`; no
      unbounded chart growth; **zero console/page errors** (verified headless Chromium).
- [x] Wired into the gallery (root README table + landing card, count bumped — handled centrally).

<div align="center">
<sub>Pro Forma · Version 1.0 · The FP&A, driver-model, "the model is the product" member of the gallery.</sub>
</div>
