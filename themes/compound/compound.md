# Compound — Theme Design Specification

**Capital compounds when it's allocated well.** Compound is a capital-allocation design system for
**capex and project finance** — the investment committee's cockpit, not the trading desk. It is built
for the people who decide where a finite pool of money goes: heads of corporate development, capital
planning, and the IC members who must rank a shelf of competing bets against a single, honest
threshold — the **hurdle rate** — and answer one question per project: **fund, hold, or reject.**

- **Metaphor:** the capital-allocation ledger — a portfolio of competing bets ranked against the
  hurdle rate.
- **Editions:** **Deployed** (light, hero — allocation work happens in a bright office) and
  **Reserve** (dark, after-hours). One class swap on `<body>`.
- **Type:** Libre Franklin (UI) + Roboto Mono (every figure, tabular).
- **Signature:** the hurdle-rate ranking with **live IRR / deployed recompute**; a decision semantic
  of invest-green / hold-gold / reject-clay; a warm-granite + bronze-gold palette on a deep chrome.

---

## Table of Contents

1. Design Principles
2. Compound vs. the others
3. Brand & Voice
4. Color System
5. The Decision System (signature)
6. The Hurdle Rate & Live Recompute (signature)
7. Typography
8. Responsive Layout
9. Elevation, Radius & Surfaces
10. Components & Patterns
11. The Ranking Table
12. Motion
13. Accessibility
14. Tokens in Practice
15. Anti-Patterns Compound Forbids
16. Pre-Ship Checklist

---

## 1. Design Principles

### P1 — A dashboard is a portfolio of competing bets
Compound never shows a metric in a vacuum. Every project sits in a **ranked book** against its peers,
and the organizing gesture is comparison: this bet vs. that one, both vs. the hurdle. The hero surface
is a ranking table, not a hero number.

### P2 — The hurdle rate is the single source of truth
There is one threshold — the minimum IRR a project must clear to be worth funding — and everything is
colored, sorted, and totalled against it. Change the hurdle in Settings and the whole book re-reads:
which bets clear, which don't, what the portfolio IRR becomes.

### P3 — Every decision has a consequence, computed live
Set a row to **Fund** and capital deployed, available headroom, funded NPV, the doughnut mix, and the
weighted **portfolio IRR** all recompute in the same tick. Allocation is not a static report; it is a
running total you are responsible for.

### P4 — Value, not just cost
Capex UIs love to count spend. Compound leads with **NPV** (value created) and **IRR** (efficiency of
that value), with spend and payback as supporting columns. The question is never "how much" — it's
"how much is it worth, per dollar, versus the alternative."

### P5 — Deployed-first, but dark-capable
Allocation decisions are made in a bright committee room. **Deployed (light)** is the hero — warm
granite on stone. **Reserve (dark)** is a first-class after-hours copy, a full token swap, never a
dimmed screenshot.

### P6 — Tabular, never jittery
Every figure is monospaced and tabular-lined so columns never shift as decisions change the totals.
Money reads down a column. Negatives use a true minus (−), currency is always `$…M`.

### P7 — Responsive, never mobile-only
The same tokens power a full IC console on a monitor and a glanceable app on a phone: the ranking book
scrolls horizontally, KPI tiles reflow, and navigation collapses to a drawer.

---

## 2. Compound vs. the others

The gallery already holds an *instrument panel* (**meridian-enterprise**), a *financial front page*
(**broadsheet**), a *field operations app* (**frontline**), and a statement-led *office of the CFO*
(**sterling**). Compound is the **capital-allocation / investment-committee** pole — money going *out*
as capex bets, ranked and decided, not money being *reported*.

| | Sterling | Broadsheet | Frontline | **Compound** |
| --- | --- | --- | --- | --- |
| Domain | Corporate finance / CFO | Enterprise data / editorial | Field operations | **Capital allocation / capex** |
| Metaphor | The ledger / statement | The front page | The field app | **Portfolio of competing bets** |
| Organizing system | Variance to plan | Story hierarchy | Task / status | **Rank vs. the hurdle rate** |
| Hero element | Financial statement | The headline | The work order | **The ranking table** |
| Decision | favorable / unfavorable | — | done / blocked | **Fund / Hold / Reject** |
| Palette | Ink-navy binder + gilt | Tinted newsprint + claret | Hi-vis concrete + orange | **Warm granite + bronze-gold** |
| Type | Hanken Grotesk / JetBrains | Fraunces / Archivo | Saira / Martian | **Libre Franklin / Roboto Mono** |

Compound is warm where Sterling is cool, forward-looking (what to fund next) where the others are
reporting (what happened), and decision-led where the others are statement-, story-, or task-led.

---

## 3. Brand & Voice

- **Name:** *Compound* — capital compounds when it's allocated well; the discipline is choosing which
  compounding to buy.
- **Voice:** measured, comparative, committee-grade. Labels are plain capital-planning English (NPV,
  IRR, payback, hurdle rate, deployed, headroom). No hype, no emoji.
- **Tagline:** *Capital compounds when it's allocated well.*
- **Logo:** a rising bar-chart with a trend line in bronze-gold on deep granite — a portfolio growing.

---

## 4. Color System

Every value is a CSS custom property. The edition class lives on `<body>` (bare `:root,.light` /
`.dark`), so the tokens cascade to the whole subtree — including overlays like the modal and drawer.
JS reads live values via `getComputedStyle(document.body)` so charts always match the active edition.

### Deployed edition (light) — default
```css
--canvas:#F3F1EA;  --surface:#FFFFFF;  --surface-2:#F1EEE4;   /* warm granite on stone */
--line:#E3DECF;    --line-2:#CFC7B2;
--ink:#221E17;     --ink-2:#5C5445;    --ink-3:#8A8172;
--chrome:#2A241A;  --chrome-2:#3A3324; --chrome-line:#4A412E; /* the granite frame */
--accent:#9A7B1F;  --accent-2:#846914; --accent-ink:#7A6013;  /* bronze-gold */
--fav:#2F6D46;     --hold:#6E6858;     --unfav:#B0483B;        /* fund / hold / reject */
```

### Reserve edition (dark) — alternate
```css
--canvas:#191510;  --surface:#221D16;  --surface-2:#2B2519;
--line:#352E20;    --line-2:#473E2C;
--ink:#EFE9DC;     --ink-2:#B7AD98;    --ink-3:#847B69;
--chrome:#120F0A;  --chrome-2:#221D15; --chrome-line:#332C1C;
--accent:#C9A544;  --accent-2:#D9B75C; --accent-ink:#D0AB4A;
--fav:#4FA972;     --hold:#A79C86;     --unfav:#D2685A;
```

**Contrast (WCAG 2.1 AA).** Body ink on both warm canvases clears 4.5:1. Bronze-gold fills use dark
ink text (`--on-accent`) for AA; gold *text* uses the darker `--accent-ink` on light surfaces. Fund /
hold / reject are validated on their own soft-tinted chip backgrounds in both editions, and never
carry meaning by hue alone — a rank number, a row edge-mark, an IRR sign, and a label all reinforce it.

---

## 5. The Decision System (signature)

Compound's semantic core is a single per-project verdict, not a magnitude.

| Token | Decision | Meaning | Used for |
| --- | --- | --- | --- |
| `--fav`  | **Fund** | Deploy capital to this bet | funded rows, deployed total, the doughnut, NPV bars |
| `--hold` | **Hold** | Defer — worth watching, not yet | held rows, gold accent chips |
| `--unfav`| **Reject** | Below the bar — don't fund | rejected rows, negative NPV |

The same three tokens drive: the in-row decision `<select>` (which recolors its own pill and the row's
left edge-mark), the NPV-by-project bar colors, the funded-only doughnut, and the fund/hold/reject
count chips. One decision, read everywhere, from one token set.

---

## 6. The Hurdle Rate & Live Recompute (signature)

The **hurdle rate** (default 12.0%) is the minimum IRR a project must clear. It is surfaced in the top
bar, drives the green/clay coloring of every IRR cell (`irr >= hurdle`), and is editable via a
**stepper** in Settings — where lowering or raising it re-reads the whole book instantly.

Funding is a live computation. The funded set and its rollups are pure getters:

```js
get funded()       { return this.projects.filter(p => p.decision === 'Fund'); }
get deployed()     { return this.funded.reduce((s,p)=>s+p.spend, 0); }
get available()    { return this.budget - this.deployed; }
get portfolioIrr() { const f=this.funded, sp=f.reduce((s,p)=>s+p.spend,0);
                     return f.reduce((s,p)=>s+p.irr*p.spend,0) / sp; }   // capital-weighted
```

So every Fund/Hold/Reject change — from the ranking table, the edit drawer, the **Fund above hurdle**
action, or a new proposal — recomputes deployed capital, available headroom, funded NPV, the
capital-weighted portfolio IRR, and every chart, in the same tick. Portfolio IRR is **weighted by
spend**, not a naïve average, because a big bet moves the portfolio more than a small one.

---

## 7. Typography

- **UI / display:** Libre Franklin (400–800). A precise, slightly warm grotesque with excellent
  numerals — sets Compound apart from the gallery's serif (Broadsheet) and geometric (Frontline) voices.
- **Figures / mono:** Roboto Mono, `font-variant-numeric: tabular-nums`, slight negative tracking.
  Every currency figure, IRR, payback, ratio, and axis tick is mono so columns line up.
- **Labels:** mono, 10px, uppercase, `.12em` tracking — the small-caps of a capital schedule.
- **Ranking scale:** project name 13px/600; NPV bold; the rank chip mono; totals footer mono.

---

## 8. Responsive Layout

- **≥1280px:** granite sidebar (240px) + top bar; ranking + doughnut in a 3-col grid; KPI tiles in a
  5-up strip; charts in 2/3 + 1/3 splits.
- **768–1279px:** sidebar persists; grids fold to 1–2 columns; tiles 3-up.
- **<768px:** sidebar → **mobile nav drawer** (hamburger); tiles 2-up; every table gets a horizontal
  scroll container so columns never crush; the edit drawer and modal go full-width.
- Shell is `h-screen` with an internally-scrolling `<main>`, so the granite chrome stays pinned and no
  panel grows unbounded. Touch targets ≥ 44px.

---

## 9. Elevation, Radius & Surfaces

- **Radius:** `--r: 9px` (cards, panels), `--r-sm: 6px` (controls, chips). Calm, considered.
- **Surfaces:** `--canvas` (page) → `--surface` (cards/tables) → `--surface-2` (insets, fields, zebra).
  Hairlines use `--line`; structural rules (table heads, chrome seams) use the stronger `--line-2` /
  `--chrome-line`.
- **Shadow:** low and warm on light; deeper on dark. Overlays (modal, drawer) use `--shadow-lg`.

---

## 10. Components & Patterns

- **App shell** — pinned granite sidebar + top bar with the capex-cycle chip, a live **hurdle /
  funded** pill, a global **New proposal** button, the edition toggle, and an available-to-allocate
  meter. Every one of the 7 nav items routes to a distinct, populated page.
- **KPI tiles** — value, a decision-toned chip (funded, vs hurdle, headroom), and a trend sparkline.
- **Ranking table** — the signature (see §11), with an inline decision `<select>` per row.
- **Data tables** — the full Projects ranking book (search, category chips, sortable-looking headers,
  zebra, hover, risk cells, responsive scroll, inline decision select, click-to-edit-drawer) and the
  Pipeline proposals table (inline **stage** select).
- **Inputs** — text, **search**, `<select>`, textarea, **toggle switch**, **segmented control**,
  **+/− stepper** (proposal capex, hurdle rate, total budget), **filter chips** (category, proposal
  tags), and numeric / inline-editable fields. All keyboard-usable with a visible gold focus ring.
- **Modal** — a centered **New Project Proposal** dialog: scrim, Esc-to-close, name, category, a
  stepper capex, expected IRR, payback, a description textarea, tag chips, a **fast-track** toggle, and
  a working **Add proposal** → pushes a new ranked project (with a derived NPV) + toast.
- **Edit drawer** — a right-hand **Edit project** drawer opened by clicking a Projects row: editable
  name, category, capex / NPV / IRR / payback numeric fields, decision select, a live IRR-vs-hurdle
  readout, a committee-note textarea, and a **high-risk** toggle; Save writes back and recomputes the
  portfolio.
- **Inline edits** — the inline decision `<select>` in the ranking tables, plus a **click-to-edit
  portfolio name** in Settings that becomes an input with Save/Cancel.
- **Feedback** — decision-toned toasts for every action; fund/hold/reject/gold **chips** from one token
  set; committed-vs-budget tracks.

The seven pages: **Overview** (portfolio BI dashboard), **Projects** (the full ranking book),
**Pipeline** (intake → committee → approved funnel + proposals), **Capital** (allocation vs. budget by
category), **Analysis** (per-project NPV/IRR/payback, cumulative cash flow, IRR sensitivity),
**Reports** (library + custom generation form), and **Settings** (edition, hurdle-rate stepper, budget
stepper, click-to-edit name).

---

## 11. The Ranking Table

The hero pattern. Each row is a competing bet, and the grammar is comparison:

- **Rank chip** — the current standing under the active sort (NPV, IRR, or payback), with a colored
  **left edge-mark** carrying the decision.
- **Project + category** — a dotted category swatch (Growth = bronze, Maintenance = green, Compliance
  = gray).
- **NPV / IRR / Payback / Spend** — mono, tabular; IRR is green when it clears the hurdle, clay when it
  doesn't; negative NPV goes clay.
- **Decision** — an inline `<select>` (Fund / Hold / Reject) that recolors itself and the row edge, and
  triggers the live recompute.

A pinned footer sums the **funded** book: spend, NPV, and capital-weighted IRR. Sorting is by NPV or
IRR (descending — bigger is better) or payback (ascending — sooner is better), so the top of the book
is always "the best bet under the current lens."

---

## 12. Motion

Restrained and functional. Overlays fade/scale in ~200ms; the drawer and mobile nav slide; toasts rise
and auto-dismiss. **Charts do not animate** (`animation:false`) — a decision terminal draws instantly,
which also removes any first-frame render race. Hover/active transitions are ~120ms. `prefers-reduced-
motion` disables transitions entirely.

---

## 13. Accessibility

- WCAG 2.1 AA contrast on real warm surfaces in both editions, including tinted chip backgrounds.
- Decision never by color alone — rank, edge-mark, IRR sign, and label reinforce it.
- Visible focus ring (`--link`, 2px, offset) on every interactive element.
- Esc closes the modal, edit drawer, mobile nav, and the click-to-edit name (`@keydown.escape.window`).
- Toggles expose `role="switch"` / `aria-checked`; icon-only buttons and decision selects carry
  `aria-label`.
- Touch targets ≥ 44px; tabular figures avoid layout shift as decisions change the totals.

---

## 14. Tokens in Practice

```css
/* the inline decision pill recolors from the decision token */
.dsel { color: var(--fav-ink); border-color: var(--fav-ink); background: var(--fav-soft); }
/* the bronze primary action */
.btn-primary { background: var(--accent); color: var(--on-accent); }
/* a funded row's left edge-mark */
.rowmark { border-left: 3px solid var(--fav-ink); }
```

Because fund/hold/reject, chrome, bronze, and surfaces are all tokens, a decision pill, a chart bar, a
doughnut slice, and a KPI chip all read from the same source — and the Reserve edition is a single
`body.dark`.

---

## 15. Anti-Patterns Compound Forbids

- **A total that lies.** Deployed, available, funded NPV, and portfolio IRR must always reflect the
  live decisions — never a stale figure.
- **A naïve portfolio IRR.** Weight by capital; a $88M bet is not one vote next to an $11M bet.
- **Color-only decisions.** Never rely on green/gold/clay without a rank, edge-mark, sign, or label.
- **Cost without value.** Never lead with spend when NPV and IRR are the point.
- **A phone mock on a desktop.** Compound is a full IC console on a monitor and an app on a phone.
- **Decorative dark mode.** Reserve is a real token swap, not a dimmed screenshot.
- **Gratuitous chart motion.** No sweeping animations on decision data.

---

## 16. Pre-Ship Checklist

- [x] Four non-negotiables: distinct POV, responsive (not mobile-only), polished, token-driven & AA.
- [x] Full-fledged demo: BI dashboard (KPIs + sparkline/area, bar, doughnut charts + a data table);
      data tables with inline-editable cells; full input range (text, search, select, textarea,
      toggle, segmented, stepper, filter chips, numeric/inline); centered modal (scrim + Esc + create);
      right-hand edit drawer + left mobile nav drawer; ≥2 inline edits (decision select + click-to-edit
      name); toasts + status chips; persistent shell where **every** nav item routes to a real,
      populated page; light + dark.
- [x] Hurdle-rate ranking with live IRR / deployed / available recompute on every decision.
- [x] WCAG AA verified on both editions, tinted surfaces included.
- [x] Charts render on tab activation and re-render on edition swap; hidden canvases guarded
      (`offsetParent === null`); unique canvas ids per page; no unbounded chart growth; **zero console
      errors** (verified headless).
- [x] Wired into the gallery (root README table + landing card, count bumped).

<div align="center">
<sub>Compound · Version 1.0 · The capital-allocation, hurdle-ranked, investment-committee member of the gallery.</sub>
</div>
