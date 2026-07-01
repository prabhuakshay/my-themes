# Sterling — Theme Design Specification

**The books balance.** Sterling is a statement-grade design system for **corporate finance and the
office of the CFO** — the finance function *inside* a company, not the markets outside it. It is
built for controllers, FP&A, treasury, and the CFO: people for whom a number is never loose, it
**ties out**; where the organizing truth is not price but **variance to plan**, favorable or
unfavorable; and where the hero surface is a **financial statement**, not a chart.

- **Metaphor:** the ledger / the financial statement — a gilt-edged reporting binder.
- **Editions:** **Statement** (light, hero — finance is paper- and report-first) and **Ledger**
  (dark, after-hours). One class swap.
- **Type:** Hanken Grotesk (UI) + JetBrains Mono (every figure, tabular).
- **Signature:** favorable / unfavorable variance as the semantic core; a deep ink-navy "binder"
  chrome in both editions; a single gilt (brass) brand accent.

---

## Table of Contents

1. Design Principles
2. Sterling vs. the others
3. Brand & Voice
4. Color System
5. The Variance System (signature)
6. Typography
7. Responsive Layout
8. Elevation, Radius & Surfaces
9. Components & Patterns
10. The Statement Table
11. Motion
12. Accessibility
13. Tokens in Practice
14. Anti-Patterns Sterling Forbids
15. Pre-Ship Checklist

---

## 1. Design Principles

### P1 — The statement is the interface
The centerpiece is a **financial statement**: line items, indentation, subtotals with a rule above,
a grand total with a heavy rule. Not a card wall pretending to be finance — a real P&L, balance
sheet, and cash-flow statement that a controller would recognize on sight.

### P2 — Every figure ties out
Subtotals equal the sum of their components; the balance sheet balances; ending cash rolls forward.
A **"Ties out"** badge is not decoration — it is a promise the numbers keep. Nothing in Sterling
displays a total that doesn't reconcile.

### P3 — Variance is the system
The organizing signal is **actual vs. plan**. Favorable is green, unfavorable is red — and crucially,
*favorable is context-aware*: for revenue and profit, over plan is good; for expenses, **under** plan
is good. One rule, applied honestly, colors every variance cell and every chart bar.

### P4 — Paper-first, but dark-capable
Corporate finance lives on printed statements and board decks. **Statement (light)** is the hero.
**Ledger (dark)** is a first-class alternate for late-night close work — a full token swap, never a
dimmed afterthought.

### P5 — Tabular, never jittery
Figures are monospaced and tabular-lined so columns never shift as values change. Money reads down a
column like a real ledger. Negative numbers use a true minus (−), not a hyphen; zero is an em dash.

### P6 — The binder frames the work
A deep ink-navy chrome (sidebar + top bar) holds the light statements like the cover of a reporting
binder — present in both editions, a touch of gilt on the active tab. Structure you can feel.

### P7 — Responsive, never mobile-only
The same tokens power a full CFO console on a monitor and a glanceable app on a phone: statement
tables scroll horizontally, KPI tiles reflow, and navigation collapses to a drawer.

---

## 2. Sterling vs. the others

The gallery already holds a *revenue desk* (Cardinal) and a *records pipeline* (Vellum). Sterling is
the **corporate-finance / office-of-the-CFO** pole — the internal finance function, statement-led.

| | Cardinal | Vellum | Dossier | **Sterling** |
| --- | --- | --- | --- | --- |
| Domain | Sales / revenue | BI data entry | Legal / contracts | **Corporate finance / CFO** |
| Metaphor | Revenue desk | The record | The case file | **The ledger / statement** |
| Organizing system | Pipeline stages | The record pipeline | Obligations | **Variance to plan** |
| Hero element | Deal board | Entry sheet | Case file | **Financial statement** |
| Default edition | Light (warm) | Light only | Light (serif) | **Statement (light, cool)** |
| Palette | Warm paper + red/teal | Porcelain + iris | Porcelain + burgundy | **Ink-navy binder + gilt** |
| Type | Sora | (serif-led) | Spectral (serif) | **Hanken Grotesk / JetBrains Mono** |

Sterling is cool where Cardinal/Vellum/Dossier are warm, sans where Dossier is serif, and
statement-led where the others are board/record/file-led.

---

## 3. Brand & Voice

- **Name:** *Sterling* — the standard of value; the trusted measure. A byword for quality ("sterling
  work") and for money (pound sterling, sterling silver).
- **Voice:** precise, understated, audit-grade. Labels are plain accounting English (Gross Profit,
  EBITDA, DSO, Net Working Capital). No hype, no emoji, no exclamation.
- **Tagline:** *The books balance.*
- **Logo:** a balance/scale glyph in gilt on ink navy — the balance sheet and the standard, in one.

---

## 4. Color System

Every value is a CSS custom property. The edition class lives on `<body>` (bare `.light` / `.dark`),
so the tokens cascade to the whole subtree — including overlays like the modal and drawer.

### Statement edition (light) — default
```css
--canvas:#F4F6F9;  --surface:#FFFFFF;  --surface-2:#EDF1F5;
--line:#E4E9EF;    --line-2:#CBD5E0;
--ink:#17212E;     --ink-2:#52607A;    --ink-3:#8794A6;
--chrome:#172436;  --chrome-2:#21344B; --chrome-line:#2C4058;   /* the binder */
--accent:#B4893B;  --accent-2:#9C7530; --accent-ink:#86611F;    /* gilt */
--link:#2D6CB5;
--fav:#1E8E5A;     --unfav:#C34733;    --flat:#6B7789;  --warn:#B5871E;
```

### Ledger edition (dark) — alternate
```css
--canvas:#10151C;  --surface:#161C25;  --surface-2:#1E2733;
--line:#28323F;    --line-2:#3A4757;
--ink:#E8EDF3;     --ink-2:#9DA9B8;    --ink-3:#66717F;
--chrome:#0C1119;  --chrome-2:#17202B; --chrome-line:#212C39;
--accent:#D8B15A;  --accent-2:#E6C577; --accent-ink:#D8B15A;
--link:#5AA0E6;
--fav:#35C08A;     --unfav:#E06A54;    --flat:#94A0AF;  --warn:#E0B24E;
```

**Contrast (WCAG 2.1 AA).** Body ink on both canvases clears 4.5:1. Gilt fills use dark ink text
(`--on-accent`) for AA; gilt *text* uses the darker `--accent-ink` on light surfaces. Favorable and
unfavorable are validated on their own soft-tinted chip backgrounds in both editions, and never carry
meaning by hue alone — a sign (+/−) and often an arrow icon accompany the color.

---

## 5. The Variance System (signature)

Sterling's semantic core is **variance to plan**, not raw magnitude.

| Token | Meaning | Used for |
| --- | --- | --- |
| `--fav`   | **Favorable** to plan | revenue/profit over budget, expenses under budget, positive cash flow, on-track collections |
| `--unfav` | **Unfavorable** to plan | revenue/profit under budget, expenses over budget, cash outflows, overdue/disputed |
| `--flat`  | On plan / neutral | zero variance, non-directional balance-sheet movement |
| `--warn`  | Watch | 31–60 day aging, in-progress close tasks |

The favorability rule is **context-aware** and computed once:

```js
varFav(row) { const d = row.actual - row.budget; return row.expense ? d <= 0 : d >= 0; }
```

So a Sales line $40K **under** budget reads green (favorable), while an R&D line $20K **over** reads
red — the same signed number, opposite meaning, because one is an expense. This single function drives
the P&L variance columns, the department table, and the budget-variance tornado chart.

---

## 6. Typography

- **UI / display:** Hanken Grotesk (400–800). A professional, cool-neutral grotesk with excellent
  numerals — sets Sterling apart from the gallery's serif themes (Dossier, Broadsheet).
- **Figures / mono:** JetBrains Mono, `font-variant-numeric: tabular-nums`, slight negative tracking.
  Every currency figure, ratio, percentage, and axis tick is mono so columns line up.
- **Labels:** mono, 10px, uppercase, `.13em` tracking — the small-caps of an accounting schedule.
- **Statement scale:** line items 13.5px; subtotals 700; grand total 800 / 14px with a heavy top rule.

---

## 7. Responsive Layout

- **≥1280px:** ink-navy sidebar (240px) + top bar; statement + side charts in a 3-col grid; KPI tiles
  in a 6-up strip.
- **768–1279px:** sidebar persists; grids fold to 1–2 columns; tiles 3-up.
- **<768px:** sidebar → **mobile nav drawer** (hamburger); tiles 2-up; every statement/table gets a
  horizontal scroll container so columns never crush; the edit drawer and modal go full-width.
- Shell is `h-screen` with an internally-scrolling `<main>`, so the binder chrome stays pinned and no
  panel grows unbounded. Touch targets ≥ 44px.

---

## 8. Elevation, Radius & Surfaces

- **Radius:** `--r: 8px` (cards, panels), `--r-sm: 5px` (controls, chips). Calm, not playful.
- **Surfaces:** `--canvas` (page) → `--surface` (cards/statements) → `--surface-2` (insets, fields,
  subtotal rows, zebra). Hairlines use `--line`; structural rules and subtotal borders use the
  stronger `--line-2`; the grand-total rule uses `--ink`.
- **Shadow:** low and cool on light; deeper on dark. Overlays (modal, drawer) use `--shadow-lg`.

---

## 9. Components & Patterns

- **App shell** — pinned ink-navy sidebar + top bar with a period segmented control (MTD/QTD/YTD),
  fiscal-period chip, close-status pill, global **New entry** button, edition toggle, and entity
  selector. Every one of the 8 nav items routes to a distinct, populated page.
- **KPI tiles** — value, a favorable/unfavorable variance chip (vs plan), and a vs-plan sparkline.
- **Statement tables** — P&L, balance sheet, cash flow (see §10).
- **Data tables** — department budget variance and AR/AP aging: mono figures, status cells, hover,
  responsive scroll, and an **inline-editable status `<select>`**.
- **Inputs** — text, search, `<select>`, textarea, **toggle switch**, **segmented control**,
  **+/− stepper** (reforecast %, journal amount), **filter chips** (department group, JE tags), and
  numeric/inline-editable fields. All keyboard-usable with a visible cyan-blue focus ring.
- **Modal** — a centered **New Journal Entry** dialog: scrim, Esc-to-close, entity/date/type/account,
  a stepper amount, memo, tag chips, a recurring toggle, and a working **Post entry** → toast.
- **Edit drawer** — a right-hand **Edit account** drawer opened by clicking an AR/AP row: editable
  name, type, status, aging buckets (live total), a collections-note textarea, an escalate toggle, and
  Save/Cancel that writes back to the row.
- **Inline edits** — the inline status `<select>` in tables, plus a **click-to-edit "Prepared by"**
  name that becomes an input with Save/Cancel.
- **Feedback** — toasts for every action; favorable/unfavorable/warn/neutral **chips** from one token
  set; a close-progress track.

---

## 10. The Statement Table

The hero pattern. Three row kinds, one grammar:

- **Line item** — indented (`.indent-1`), secondary ink, the components.
- **Subtotal** (`.row-sub`) — 700 weight, a `--line-2` rule above and below, a `--surface-2` band
  (Total Revenue, Gross Profit, EBITDA, Cash from Operations, Total Assets sections).
- **Grand total** (`.row-total`) — 800 weight, a heavy `--ink` rule above (Net Income, Total Assets,
  Total Liab. & Equity, Ending Cash).

Variance columns (Actual / Budget / Var $ / Var %) are colored by the context-aware `varFav` rule;
the P&L adds a **% of revenue** column. The balance sheet carries prior-period and change columns; the
cash-flow statement colors inflows green and outflows red, with beginning/ending cash left neutral.
All subtotals are pre-reconciled so the statement always ties.

---

## 11. Motion

Restrained and functional. Overlays fade/scale in ~200ms; the drawer and mobile nav slide; toasts
rise and auto-dismiss. **Charts do not animate** — a data-first terminal draws instantly (this also
removes any first-frame render race). Hover/active transitions are 120ms. Respect for `prefers-
reduced-motion` is inherited from the minimal motion budget.

---

## 12. Accessibility

- WCAG 2.1 AA contrast on real surfaces in both editions, including tinted chip backgrounds.
- Favorability never by color alone — sign, arrow icon, and label reinforce it.
- Visible focus ring (`--link`, 2px, offset) on every interactive element.
- Esc closes the modal, edit drawer, and mobile nav (`@keydown.escape.window`).
- Toggles expose `role="switch"` / `aria-checked`; icon-only buttons carry `aria-label`.
- Touch targets ≥ 44px; tabular figures avoid layout shift for screen magnification users.

---

## 13. Tokens in Practice

```css
/* a favorable variance cell */
.var-fav { color: var(--fav); }
/* a subtotal band in the statement */
.stmt .row-sub td { background: var(--surface-2); border-block: 1px solid var(--line-2); }
/* the gilt primary action */
.btn-primary { background: var(--accent); color: var(--on-accent); }
```

Because favorable/unfavorable, chrome, gilt, and surfaces are all tokens, a variance chip, a chart
bar, a status pill, and a KPI delta all read from the same source — and the Ledger edition is a single
`body.dark`.

---

## 14. Anti-Patterns Sterling Forbids

- **A total that doesn't tie.** Never show a subtotal that isn't the sum of its parts.
- **Color-only meaning.** Never rely on green/red without a sign or label.
- **Naïve variance.** Never color an expense overrun green just because the number is positive.
- **Proportional-font figures.** Never set money in the UI sans; columns must be tabular mono.
- **A phone mock on a desktop.** Sterling is a full console on a monitor and an app on a phone.
- **Decorative dark mode.** Ledger is a real token swap, not a dimmed screenshot.
- **Gratuitous chart motion.** No sweeping animations on financial data.

---

## 15. Pre-Ship Checklist

- [x] Four non-negotiables: distinct POV, responsive (not mobile-only), polished, token-driven & AA.
- [x] Full-fledged demo: BI dashboard (KPIs + line/area, bar, doughnut charts + statement table);
      data tables with inline-editable cells; full input range (text, search, select, textarea,
      toggle, segmented, stepper, filter chips, numeric/inline); centered modal (scrim + Esc + create);
      right-hand edit drawer + left mobile nav drawer; ≥2 inline edits; toasts + status chips;
      persistent shell where **every** nav item routes to a real, populated page; light + dark.
- [x] Every statement ties out; variance favorability is context-aware.
- [x] WCAG AA verified on both editions, tinted surfaces included.
- [x] Charts render on tab activation and re-render on edition swap; hidden canvases guarded; no
      unbounded chart growth; no console errors.
- [x] Wired into the gallery (root README table + landing card, count bumped).

<div align="center">
<sub>Sterling · Version 1.0 · The corporate-finance, statement-led, office-of-the-CFO member of the gallery.</sub>
</div>
