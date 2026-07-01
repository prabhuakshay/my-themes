# Zero — Theme Design Specification

**Every dollar justified from zero.** Zero is a design system for **zero-based budgeting and spend
management** — the discipline where no line item is inherited and no budget is renewed by default.
Nothing carries forward. Every cost package starts at **zero** and must be *defended* on its own
justification before a dollar is granted. It is built for FP&A, cost owners, and the budget
committee: people who don't ask "how much more than last year?" but "why does this dollar exist at
all?"

- **Metaphor:** the cost meter / the thermostat — nothing is a given; every package is set, not
  inherited. The organizing act is a **decision**: Approve, Challenge, or Cut.
- **Editions:** **Concrete** (light, hero — austere and utilitarian) and **Graphite** (dark,
  after-hours). One class swap on `<body>`.
- **Type:** Instrument Sans (UI) + Anonymous Pro (every figure, tabular).
- **Signature:** the three-way **decision** as the semantic core — approve-green, challenge-amber,
  cut-red — driving a live recompute of every KPI, chart, and total the moment a decision changes.

---

## Table of Contents

1. Design Principles
2. Zero vs. the others
3. Brand & Voice
4. Color System
5. The Decision System (signature)
6. Typography
7. Responsive Layout
8. Elevation, Radius & Surfaces
9. Components & Patterns
10. The Cost-Package Register
11. Live Recompute
12. Motion
13. Accessibility
14. Tokens in Practice
15. Anti-Patterns Zero Forbids
16. Pre-Ship Checklist

---

## 1. Design Principles

### P1 — Nothing is a given
The interface never presents a number as inherited. Every cost package is shown next to its **prior
base** and its **proposed** amount, and the delta is always visible. The chrome even says it out
loud: *"Nothing is a given."* A budget is not last year plus X — it is a stack of packages, each one
defended from zero.

### P2 — The decision is the interface
The atomic act is a **decision**: Approve, Challenge, or Cut. It lives everywhere — an inline
`<select>` in the register, a pair of action buttons in the queue, a field in the edit drawer — and
it always looks the same, colors the same, and recomputes the same. One verb set, one color set.

### P3 — Justify or cut
Every package carries a **justification** — a sentence that defends the spend. A package with no
defense is a candidate for the axe. The demo treats the justification as a first-class field: in the
table, the drawer, the modal, and the reports.

### P4 — Concrete-first, but dark-capable
Zero-based work is austere, high-stakes, spreadsheet-adjacent. **Concrete (light)** is the hero — a
utilitarian, high-contrast, boxy surface. **Graphite (dark)** is a first-class alternate for the
late-night committee session, a full token swap, never a dimmed screenshot.

### P5 — Tabular, never jittery
Figures are monospaced and tabular-lined so columns never shift as decisions flip values. Money
reads down a column like a meter. Negative deltas use a true minus (−); a zero delta is `±$0`.

### P6 — The meter frames the work
A stark near-black chrome (sidebar + top bar) holds the concrete surfaces like the bezel of an
instrument — present in both editions, a stripe of approve-green on the active tab. Structure you can
feel; boxy 4px radii throughout.

### P7 — Responsive, never mobile-only
The same tokens power a full committee console on a monitor and a glanceable app on a phone: the
register scrolls horizontally, KPI tiles reflow, and navigation collapses to a drawer.

---

## 2. Zero vs. the others

The gallery already holds an *instrument panel* (Meridian), a *financial front page* (Broadsheet),
and a *field / operations app* (Frontline). Zero is the **zero-based-budgeting / spend-management**
pole — decision-led, not statement- or record-led.

| | Meridian | Broadsheet | Frontline | **Zero** |
| --- | --- | --- | --- | --- |
| Domain | Enterprise ops | Editorial data | Field operations | **Zero-based budgeting** |
| Metaphor | Instrument panel | Financial front page | Ops app | **The cost meter** |
| Organizing system | Status | Columns & rules | Task state | **The decision (Approve/Challenge/Cut)** |
| Hero element | Panel grid | Front page | Work cards | **The cost-package register** |
| Palette | Cool gray + Carbon blue | Tinted newsprint + claret | Hi-vis concrete + orange | **Concrete + graphite chrome + green/amber/red** |
| Type | IBM Plex Sans/Mono | Fraunces + Archivo | Saira + Martian Mono | **Instrument Sans / Anonymous Pro** |

Zero is decision-led where the others are status-, column-, and task-led; its palette is a stark
near-black meter, and its semantic core is a three-way budget verdict rather than a status or a
variance.

---

## 3. Brand & Voice

- **Name:** *Zero* — the baseline every package is measured from. Zero-based budgeting in one word.
- **Voice:** austere, direct, accountable. Labels are plain budgeting English (Prior base, Proposed,
  Δ vs base, Justified spend). No hype, no emoji, no exclamation.
- **Tagline:** *Every dollar justified from zero.*
- **Logo:** a gauge / meter glyph — the dial that reads nothing until a value is set.

---

## 4. Color System

Every value is a CSS custom property. The edition class lives on `<body>` (bare `.light` / `.dark`),
so the tokens cascade to the whole subtree — including overlays like the modal and drawer.

### Concrete edition (light) — default
```css
--canvas:#F0F0ED;  --surface:#FFFFFF;  --surface-2:#F4F4F1;
--line:#E2E2DD;    --line-2:#CFCFC8;
--ink:#141414;     --ink-2:#565650;    --ink-3:#8A8A82;
--chrome:#141414;  --chrome-2:#1F1F1E; --chrome-line:#2E2E2C;   /* the meter bezel */
--accent:#1A1A1A;  --accent-2:#000000; --on-accent:#FFFFFF;     /* graphite brand */
--link:#1D4ED8;
--fav:#15803D;     --warn:#B45309;     --unfav:#DC2626;  --flat:#6B7280;
--r:4px;           --r-sm:3px;
```

### Graphite edition (dark) — alternate
```css
--canvas:#121211;  --surface:#1B1B19;  --surface-2:#232320;
--line:#2E2E2A;    --line-2:#3D3D38;
--ink:#F0F0EA;     --ink-2:#A8A89F;    --ink-3:#75756C;
--chrome:#0C0C0B;  --chrome-2:#1A1A18; --chrome-line:#2A2A27;
--accent:#EDEDE6;  --accent-2:#FFFFFF; --on-accent:#141414;
--link:#6C9BEE;
--fav:#3FB56B;     --warn:#D98A2B;     --unfav:#F06767;  --flat:#9A9A90;
```

**Contrast (WCAG 2.1 AA).** Body ink on both canvases clears 4.5:1. The graphite accent uses a light
`--on-accent` for filled buttons (near-white ink on near-black in Concrete, dark ink on near-white in
Graphite). Approve / challenge / cut are validated on their own soft-tinted chip backgrounds in both
editions, and never carry meaning by hue alone — an icon (check / triangle / scissors) and the verb
label always accompany the color.

---

## 5. The Decision System (signature)

Zero's semantic core is the **decision**, not raw magnitude.

| Token | Decision | Meaning | Used for |
| --- | --- | --- | --- |
| `--fav`   | **Approve**   | The dollar is justified — granted in full | approved packages, savings on target, under-base status |
| `--warn`  | **Challenge** | Contested — sent to the queue for defense | challenged packages, the approvals queue, short-of-target |
| `--unfav` | **Cut**       | Eliminated — struck from the budget | cut packages (struck-through, dimmed), over-base status |
| `--flat`  | Neutral       | Baseline / non-directional | prior base, category chips |

Every decision surface reads from the same three functions so a `<select>`, a chip, a chart slice,
and a KPI delta are never out of step:

```js
decisionColor(d) { return { Approve:'var(--fav)', Challenge:'var(--warn)', Cut:'var(--unfav)' }[d]; }
decisionSoft(d)  { return { Approve:'var(--fav-soft)', Challenge:'var(--warn-soft)', Cut:'var(--unfav-soft)' }[d]; }
decisionChip(d)  { return { Approve:'chip-fav', Challenge:'chip-warn', Cut:'chip-unfav' }[d]; }
```

A **Cut** package is treated honestly: struck through, dimmed, and removed from proposed spend (its
dollars flow into savings). A **Challenge** lands in the Approvals queue awaiting a committee verdict.

---

## 6. Typography

- **UI / display:** Instrument Sans (400–700). A clean, slightly condensed grotesk with an
  engineered feel — utilitarian without being generic, and distinct from the gallery's serif and
  humanist-sans themes.
- **Figures / mono:** Anonymous Pro, `font-variant-numeric: tabular-nums`, slight negative tracking.
  Every currency figure, percentage, delta, and axis tick is mono so columns line up like a meter.
- **Labels:** mono, 10px, uppercase, `.14em` tracking — the small-caps of a control panel.
- **Register scale:** package names 13.5px/600; the justification sub-line 12px/`--ink-2`; totals in
  the footer bar 700.

---

## 7. Responsive Layout

- **≥1280px:** near-black sidebar (240px) + top bar; the register full-width; charts in a 3-col grid;
  KPI tiles in a 5-up strip.
- **768–1279px:** sidebar persists; grids fold to 1–2 columns; tiles 3-up.
- **<768px:** sidebar → **mobile nav drawer** (hamburger); tiles 2-up; every table gets a horizontal
  scroll container so columns never crush; the edit drawer and modal go full-width.
- Shell is `h-screen` with an internally-scrolling `<main>`, so the meter chrome stays pinned and no
  panel grows unbounded. Touch targets ≥ 44px.

---

## 8. Elevation, Radius & Surfaces

- **Radius:** `--r: 4px` (cards, panels), `--r-sm: 3px` (controls, chips). Boxy and utilitarian — the
  signature restraint. Even the toggle switch is squared to match.
- **Surfaces:** `--canvas` (page) → `--surface` (cards) → `--surface-2` (insets, fields, zebra rows).
  Hairlines use `--line`; structural rules and table-head borders use the stronger `--line-2`; the
  chrome seam uses `--chrome-line` so the bezel reads clearly against the panels.
- **Shadow:** low and neutral on Concrete; deeper on Graphite. Overlays (modal, drawer) use
  `--shadow-lg`.

---

## 9. Components & Patterns

- **App shell** — pinned near-black sidebar + top bar with a cycle segmented control (FY26/27/28), a
  fiscal-year chip, a pending-count pill, a global **New package** button, edition toggle, and a
  cost-center selector. Every one of the 7 nav items routes to a distinct, populated page.
- **KPI tiles** — value, a decision-colored chip, and a trend sparkline (Overview).
- **The cost-package register** — the hero table (see §10).
- **Data tables** — the register and the category / savings tables: mono figures, sortable-look
  headers (click to sort by name, base, proposed, or delta), zebra rows, hover, status cells,
  responsive scroll, an **inline-editable decision `<select>`**, and an empty-state with a reset.
- **Inputs** — text, search, `<select>`, textarea, **toggle switch** (recurring, escalate,
  preferences), **segmented control** (cycle, decision filter, report period, edition), **+/−
  stepper** (target-savings percent, proposed amount), **filter chips** (category, JE tags), and
  numeric / inline-editable fields. All keyboard-usable with a visible blue focus ring.
- **Modal** — a centered **New Cost Package** dialog: scrim, Esc-to-close, name, category, owner,
  prior base, a stepper proposed amount, a live Δ-vs-base readout, justification, tag chips, a
  recurring toggle, and a working **Add package** → toast (defaults the new package to *Challenge*).
- **Edit drawer** — a right-hand **Edit package** drawer opened by clicking a register row: editable
  name, category, owner, prior/proposed amounts (live Δ), decision, justification, an escalate
  toggle, and Save/Cancel that writes back and recomputes.
- **Approvals queue** — challenged packages as cards with Approve / Review / Cut actions; deciding a
  card removes it from the queue and updates the KPIs, doughnut, and progress meter live.
- **Inline edits** — the inline decision `<select>` in the register, plus a **click-to-edit budget
  owner** in Settings that becomes an input with Save/Cancel (Enter/Esc).
- **Feedback** — decision-colored toasts for every action; approve/challenge/cut/neutral **chips**
  from one token set; a decision-progress meter.

---

## 10. The Cost-Package Register

The hero pattern. Each row is a package defended from zero:

- **Identity** — an owner monogram, the package name (struck through when Cut), the one-line
  justification, and the owner.
- **The numbers** — Prior base (neutral) and Proposed (bold), with **Δ vs base** colored green when
  at or under base and red when over.
- **The verdict** — an inline decision `<select>` whose border, text, and fill all take the decision
  color, so the row *is* its decision at a glance. A left border stripe reinforces it.
- **The footer** — live counts (approved / challenged / cut) and justified-spend-of-baseline.

Filters (category chips + a decision segmented control + a search box) and click-to-sort headers make
the register a real working surface, not a static list. Clicking anywhere on a row (except the
decision cell) opens the edit drawer.

---

## 11. Live Recompute

The entire system is derived from the packages array through Alpine getters — `baseline`, `spend`,
`justified`, `cut`, `savings`, `approvedPct` — so changing one decision cascades everywhere at once:

```js
get spend()   { return this.packages.reduce((s,p)=>s + (p.decision==='Cut' ? 0 : p.amount), 0); }
get savings() { return this.baseline - this.spend; }
```

When a decision changes — via the register `<select>`, a queue button, or a drawer Save — the KPI
tiles, the decision-mix doughnut, the category bars, the savings tracker, the progress meter, and the
nav badges all recompute in the same frame. Charts on the *current* page are rebuilt via
`renderFor(page)` (hidden canvases are guarded by `offsetParent === null`).

---

## 12. Motion

Restrained and functional. Overlays fade/scale in ~200ms; the drawer and mobile nav slide; toasts
rise and auto-dismiss at 2.6s. **Charts do not animate** (`animation:false`) — a data-first meter
draws instantly, which also removes any first-frame render race. Hover/active transitions are 120ms.
`prefers-reduced-motion` collapses all transitions to near-zero.

---

## 13. Accessibility

- WCAG 2.1 AA contrast on real surfaces in both editions, including tinted chip backgrounds.
- Decisions never by color alone — icon (check / triangle / scissors) and the verb label reinforce
  every use.
- Visible focus ring (`--link`, 2px, offset) on every interactive element.
- Esc closes the modal, edit drawer, mobile nav, and the inline owner editor (`@keydown.escape.window
  → closeAll()`).
- Toggles expose `role="switch"` / `aria-checked`; icon-only buttons carry `aria-label`; the toast
  region is `aria-live="polite"`.
- Touch targets ≥ 44px; tabular figures avoid layout shift under zoom / magnification.

---

## 14. Tokens in Practice

```css
/* an approve decision cell */
select { border-color: var(--fav); color: var(--fav); background: var(--fav-soft); }
/* a cut package row */
tr { border-left: 3px solid var(--unfav); opacity: .72; }
/* the graphite primary action */
.btn-primary { background: var(--accent); color: var(--on-accent); }
```

Because approve/challenge/cut, chrome, accent, and surfaces are all tokens, a decision `<select>`, a
chart slice, a status chip, and a KPI delta all read from the same source — and the Graphite edition
is a single `body.dark`.

---

## 15. Anti-Patterns Zero Forbids

- **An inherited number.** Never present a budget without its zero-base and its delta.
- **Color-only meaning.** Never rely on green/amber/red without an icon or the verb.
- **A silent cut.** A Cut package must read as cut — struck through, dimmed, out of spend.
- **Proportional-font figures.** Never set money in the UI sans; columns must be tabular mono.
- **A phone mock on a desktop.** Zero is a full console on a monitor and an app on a phone.
- **Decorative dark mode.** Graphite is a real token swap, not a dimmed screenshot.
- **Rounded, playful chrome.** Zero is boxy (4px) and austere on purpose; no soft SaaS pill look.
- **Gratuitous chart motion.** No sweeping animations on budget data.

---

## 16. Pre-Ship Checklist

- [x] Four non-negotiables: distinct POV, responsive (not mobile-only), polished, token-driven & AA.
- [x] Full-fledged demo: BI overview (KPIs + line/area, bar, doughnut charts + data table); data
      tables with an inline-editable decision cell and sortable-look headers; full input range (text,
      search, select, textarea, toggle, segmented, stepper, filter chips, numeric/inline); centered
      modal (scrim + Esc + create + toast); right-hand edit drawer + left mobile nav drawer; ≥2
      inline edits (decision cell + click-to-edit owner); toasts + status chips; persistent shell
      where **every** nav item routes to a real, populated page; Concrete + Graphite.
- [x] Live recompute: every decision cascades to KPIs, doughnut, bars, savings, and badges.
- [x] WCAG AA verified on both editions, tinted surfaces included.
- [x] Charts render on tab activation and re-render on edition swap; unique canvas ids per page;
      hidden canvases guarded; no unbounded growth; **zero console/page errors** (verified headless).
- [x] Wired into the gallery (root README table + landing card, count bumped).

<div align="center">
<sub>Zero · Version 1.0 · The zero-based-budgeting, decision-led, spend-management member of the gallery.</sub>
</div>
