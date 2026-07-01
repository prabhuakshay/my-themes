# Confluence — Theme Design Specification

**Many books, one truth.** Confluence is a consolidation design system for the **group controller** —
the person who takes fourteen local ledgers in nine currencies and rolls them into one set of group
accounts that *ties out*. It is built for group finance, consolidation accountants, and the corporate
controller: people for whom the organizing act is not a single statement but a **confluence** — many
entities' books flowing into one consolidated truth, translated through FX, netted of intercompany,
and closed on a schedule.

- **Metaphor:** rivers joining — a *confluence*. Many entity ledgers converge into one group ledger.
- **Editions:** **Light** (hero — the reporting canvas) and **Dark** (after-hours close work). One
  class swap on `<body>`.
- **Type:** Albert Sans (UI) + Fira Mono (every figure, tabular).
- **Signature:** the **entity rollup that ties out** (Local → FX-translated → Consolidated) and the
  **clickable close heatmap** (entities × tasks) that drives a live group-close %; a cool
  institutional blue-gray canvas inside a deep steel-indigo chrome.

---

## Table of Contents

1. Design Principles
2. Confluence vs. the others
3. Brand & Voice
4. Color System
5. The Consolidation System (signature)
6. Typography
7. Responsive Layout
8. Elevation, Radius & Surfaces
9. Components & Patterns
10. The Rollup & the Heatmap
11. Motion
12. Accessibility
13. Tokens in Practice
14. Anti-Patterns Confluence Forbids
15. Pre-Ship Checklist

---

## 1. Design Principles

### P1 — Consolidation is the interface
The centerpiece is the **rollup**: local-currency figures translated at closing FX into a common
presentation currency, subtotaled by region, netted of intercompany eliminations and NCI, down to one
consolidated group total. Not a dashboard *about* consolidation — the worksheet a group controller
would recognize on sight.

### P2 — It always ties out
Region subtotals sum to translated gross; gross less eliminations less NCI equals the consolidated
group. A **"Ties out" / "Balanced"** badge is a promise, not decoration. Editing an FX rate, an
ownership %, or a local figure re-derives every dependent total live — and the total still ties.

### P3 — Many books, one truth
Every number carries its provenance: which **entity**, which **currency**, at which **FX rate**, under
which **consolidation method**, at what **ownership %**. The group figure is only as trustworthy as the
entities feeding it, so the entity is a first-class object with its own registry, close status, and
edit drawer.

### P4 — The close is a grid, not a checklist
Group close is inherently two-dimensional: **entities × tasks** (Trial balance, Intercompany, FX,
Eliminations, Review). Confluence renders it as a **heatmap** you can click — each cell advances
Open → In progress → In review → Closed — and the whole grid drives a single group-close %.

### P5 — Tabular, never jittery
Figures are monospaced and tabular-lined so columns never shift as values change. Money reads down a
column like a ledger. Negative and eliminated amounts use a true minus (−), never a hyphen.

### P6 — The chrome frames the confluence
A deep steel-indigo chrome (sidebar + top bar) holds the light ledgers like the banks of a river —
present in both editions, a touch of accent on the active tab and the confluence mark. Structure you
can feel.

### P7 — Responsive, never mobile-only
The same tokens power a full consolidation console on a monitor and a glanceable app on a phone:
worksheets scroll horizontally, KPI tiles reflow, the heatmap keeps its grid, and navigation collapses
to a drawer.

---

## 2. Confluence vs. the others

The gallery already holds an *instrument panel* (Meridian), a *financial front page* (Broadsheet), a
*field operations app* (Frontline), and an *office-of-the-CFO statement binder* (Sterling). Confluence
is the **group-consolidation** pole — not one company's books but *many* books rolled into one.

| | Meridian | Broadsheet | Frontline | Sterling | **Confluence** |
| --- | --- | --- | --- | --- | --- |
| Domain | Platform ops | Editorial data | Field ops | Corporate finance | **Group consolidation** |
| Metaphor | Instrument panel | Front page | Field app | The ledger | **Rivers joining** |
| Organizing system | Signals | Columns/rules | Work orders | Variance to plan | **Rollup + close grid** |
| Hero element | Boxed grid | Broadsheet | Rounded cards | Statement | **Entity rollup + heatmap** |
| Palette | Cool gray | Newsprint | Hi-vis concrete | Ink-navy + gilt | **Blue-gray + steel-indigo** |
| Type | IBM Plex | Fraunces/Archivo | Saira | Hanken Grotesk | **Albert Sans / Fira Mono** |

Confluence is cool and institutional like Meridian/Sterling, but its organizing act is **many-to-one
consolidation** — the entity registry, the FX-translated rollup, the intercompany elimination matrix,
and the entities × tasks close heatmap — a pole none of the others occupy.

---

## 3. Brand & Voice

- **Name:** *Confluence* — the point where rivers meet; many flows becoming one. The consolidation act
  in a single word.
- **Voice:** precise, institutional, audit-grade. Labels are plain group-accounting English (Entity
  Rollup, Translated USD, Eliminations, NCI, Close status). No hype, no emoji.
- **Tagline:** *Many books, one truth.*
- **Logo:** a confluence mark — two strokes joining into one — in white/accent on steel-indigo; the
  many-into-one metaphor, drawn.

---

## 4. Color System

Every value is a CSS custom property. The edition class lives on `<body>` (bare `.light` / `.dark`),
so tokens cascade to the whole subtree — including overlays like the modal and drawer.

### Light edition (default)
```css
--canvas:#EEF2F6;  --surface:#FFFFFF;  --surface-2:#E7ECF2;
--line:#DEE5EC;    --line-2:#C6D0DB;
--ink:#17222E;     --ink-2:#4E5D6E;    --ink-3:#8391A0;
--chrome:#20294A;  --chrome-2:#2C3860; --chrome-line:#3A4770;   /* steel-indigo */
--accent:#445A9C;  --accent-2:#3A4E88; --accent-ink:#3B4E8C;    /* confluence brand */
--link:#3D5AAE;
--pos:#1E8E5A;     --neg:#C34733;      --warn:#B5871E;  --neutral:#5D6B7C;
```

### Dark edition
```css
--canvas:#0E1420;  --surface:#151D2C;  --surface-2:#1D2738;
--line:#273347;    --line-2:#3A485E;
--ink:#E6ECF3;     --ink-2:#A0AEC0;    --ink-3:#6B7A8D;
--chrome:#0A0F1B;  --chrome-2:#151D2E; --chrome-line:#212C40;
--accent:#7E93D6;  --accent-2:#93A5DE; --accent-ink:#93A5DE;
--link:#8EA0DB;
--pos:#35C08A;     --neg:#E06A54;      --warn:#E0B24E;  --neutral:#94A0AF;
```

**Contrast (WCAG 2.1 AA).** Body ink on both canvases clears 4.5:1. The accent fill uses white text
(`--on-accent`) on light and a dark ink on dark for AA; accent *text* uses the tuned `--accent-ink` on
light surfaces. Semantic states (pos/neg/warn/link) are validated on their own soft-tinted chip and
heatmap backgrounds in both editions, and never carry meaning by hue alone — an icon and a sign
accompany the color.

---

## 5. The Consolidation System (signature)

Confluence's semantic core is **provenance and roll-up**, not raw magnitude. One computed chain drives
every surface:

```
usd(entity)      = round(local × fx)                       // translate each entity
regionTotal      = Σ usd(entity in region)                 // subtotal by region
groupTotal       = Σ usd(entity)                            // translated gross
consolidated     = groupTotal − eliminations − NCI         // the group truth
groupClosePct    = doneCells / totalCells × 100            // the close heatmap
```

| Token | Meaning | Used for |
| --- | --- | --- |
| `--pos`  | Closed / matched / favorable | closed entities, matched IC balances, positive FX |
| `--neg`  | Eliminated / unmatched | intercompany eliminations, negative FX, unmatched pairs |
| `--warn` | Watch | in-progress close tasks, NCI, reduced ownership |
| `--link` | In review | in-review close cells and entities |
| `--neutral` | Neutral / info | on-plan, non-directional figures |

Because FX rates, ownership %, and local figures are all editable and feed the same chain, an inline
edit on the **FX page** flows straight into the **rollup**, the **consolidation worksheet**, and the
**FX-impact chart** — and the group still ties out.

---

## 6. Typography

- **UI / display:** Albert Sans (400–800). A humanist, cool-neutral grotesk with excellent numerals
  and a calm institutional voice — distinct from the gallery's serif (Broadsheet) and display
  (Frontline) themes.
- **Figures / mono:** Fira Mono, `font-variant-numeric: tabular-nums`. Every currency figure, FX rate,
  percentage, and axis tick is mono so columns line up down the ledger.
- **Labels:** mono, 10px, uppercase, `.12em` tracking — the small-caps of a consolidation schedule.
- **Statement scale:** line items 13.5px; region subtotals 700; the consolidated grand total 800 /
  14px with a heavy top rule.

---

## 7. Responsive Layout

- **≥1280px:** steel-indigo sidebar (240px) + top bar; worksheet + side charts in a 3-col grid; KPI
  tiles in a 5-up strip.
- **768–1279px:** sidebar persists; grids fold to 1–2 columns; tiles 3-up.
- **<768px:** sidebar → **mobile nav drawer** (hamburger); tiles 2-up; every worksheet/table/heatmap
  gets a horizontal-scroll container so columns never crush; the edit drawer and modal go full-width.
- Shell is `h-screen` with an internally-scrolling `<main>`, so the chrome stays pinned and no panel
  grows unbounded. Touch targets ≥ 44px.

---

## 8. Elevation, Radius & Surfaces

- **Radius:** `--r: 9px` (cards, panels), `--r-sm: 6px` (controls, chips). Calm, institutional.
- **Surfaces:** `--canvas` (page) → `--surface` (cards/ledgers) → `--surface-2` (insets, fields,
  subtotal/region rows, zebra). Hairlines use `--line`; structural rules, region bands and subtotal
  borders use the stronger `--line-2`; the consolidated grand-total rule uses `--ink`.
- **Shadow:** low and cool on light; deeper on dark. Overlays (modal, drawer) use `--shadow-lg`.

---

## 9. Components & Patterns

- **App shell** — pinned steel-indigo sidebar + top bar with a period segmented control (MTD/QTD/YTD),
  fiscal chip, reporting-count pill, global **Add entity** button, edition toggle, and a reporting-
  currency selector. Every one of the **8 nav items** routes to a distinct, populated page.
- **KPI tiles** — value, a semantic chip, a helper note, and a sparkline; consolidated revenue,
  entities reporting, eliminations, FX impact, and group close.
- **Entity rollup** (signature) — Local → FX rate → Translated USD → % Group, region-banded and
  subtotaled, with an inline **close-status `<select>`** per entity, an eliminations line, and a
  consolidated total that ties.
- **Consolidation worksheet** — a statement-style table down to consolidated group revenue, with a
  bridge chart and a Gross → Elim → NCI → Consolidated reconciliation.
- **Elimination matrix** — seller → buyer intercompany balances with an inline **match-status select**,
  a by-type bar, and a mix doughnut; filterable by type.
- **Close heatmap** (signature) — entities × tasks, each cell clickable to advance, driving a live
  group-close %; paired with a by-status doughnut.
- **FX translation** — a rates table with an **inline-editable rate cell** (click a rate → input →
  Save) that propagates into every entity's translation, plus per-currency exposure and FX impact.
- **Data tables** — the entity registry (searchable, region-filtered, clickable rows) and every
  worksheet: mono figures, status cells, hover/zebra, responsive scroll, inline-editable cells.
- **Inputs** — text, **search**, `<select>`, textarea, **toggle switch**, **segmented control**,
  **+/− stepper** (ownership %), **filter chips** (region, elimination type), and numeric/inline-
  editable fields. All keyboard-usable with a visible focus ring.
- **Modal** — a centered **Add entity** dialog: name, parent, region, currency, method, an ownership
  **stepper**, an opening-note textarea, an **eliminate-intercompany toggle**, and a working create →
  appends to the registry and toasts.
- **Edit drawer** — a right-hand **Edit entity** drawer opened by clicking a registry row: name,
  functional currency, ownership %, close status, FX rate, local revenue, method, a live translated-
  USD total, a controller note, a **sub-consolidated toggle**, and Save/Cancel that writes back and
  re-derives the rollup.
- **Inline edits** — the inline status/match `<select>`s and editable rate cell, plus a **click-to-edit
  group name** on Settings that becomes an input with Save/Cancel.
- **Feedback** — toasts for every action; pos/neg/warn/link/neutral **chips** from one token set; the
  group-close progress track.

---

## 10. The Rollup & the Heatmap

The two hero patterns.

**The rollup** has three row kinds, one grammar: a **region band** (`.row-region`, a `--line-2`-ruled
`--surface-2` header naming the region), **entity lines** (indented, secondary ink, the components),
a **region subtotal** (`.row-sub`, 700, banded), then the **eliminations** and **NCI** lines and the
**consolidated total** (`.row-total`, 800, a heavy `--ink` rule). All subtotals are pre-reconciled so
the sheet always ties.

**The heatmap** is a matrix: entities down the side, close tasks across the top, each cell a colored
button carrying an icon (check / eye / loader / minus) and a soft-tinted state background. Clicking a
cell advances its state and re-derives the single group-close % shown in the footer track — the close
made spatial.

---

## 11. Motion

Restrained and functional. Overlays fade/scale in ~200ms; the drawer and mobile nav slide; toasts rise
and auto-dismiss. **Charts do not animate** (`animation:false`) — a data-first console draws instantly,
which also removes any first-frame render race. Hover/active transitions are ~120ms; heatmap cells lift
1px on hover. `prefers-reduced-motion` disables transitions and animations globally.

---

## 12. Accessibility

- WCAG 2.1 AA contrast on real surfaces in both editions, including tinted chip and heatmap backgrounds.
- State never by color alone — icon, sign, and label reinforce every chip and heatmap cell.
- Visible focus ring (`--link`, 2px, offset) on every interactive element.
- Esc closes the modal, edit drawer, mobile nav, the click-to-edit name, and the inline rate editor
  (`@keydown.escape.window="closeAll()"`).
- Toggles expose `role="switch"` / `aria-checked`; icon-only and heatmap buttons carry `aria-label`.
- Touch targets ≥ 44px; tabular figures avoid layout shift for screen-magnification users.

---

## 13. Tokens in Practice

```css
/* a region band in the rollup */
.tbl .row-region td { background: var(--surface-2); border-block: 1px solid var(--line-2); }
/* the consolidated grand total */
.tbl .row-total td { border-top: 2px solid var(--ink); font-weight: 800; }
/* a heatmap cell (closed) */
.hmcell.done { background: var(--pos-soft); color: var(--pos); }
/* the accent primary action */
.btn-primary { background: var(--accent); color: var(--on-accent); }
```

Because chrome, accent, semantic states and surfaces are all tokens, a rollup cell, a heatmap tile, a
status chip, a chart bar, and a KPI delta all read from the same source — and the Dark edition is a
single `body.dark`.

---

## 14. Anti-Patterns Confluence Forbids

- **A group total that doesn't tie.** Never show a consolidated figure that isn't gross less
  eliminations less NCI.
- **Figures without provenance.** Never show a translated amount without its entity, currency, and FX
  rate.
- **A stale rollup.** Editing an FX rate or ownership % must re-derive every dependent total.
- **Color-only meaning.** Never rely on green/red without an icon or label.
- **Proportional-font figures.** Money and rates are tabular mono, always.
- **A phone mock on a desktop.** Confluence is a full console on a monitor and an app on a phone.
- **Decorative dark mode.** Dark is a real token swap, not a dimmed screenshot.
- **Gratuitous chart motion.** No sweeping animations on consolidation data.

---

## 15. Pre-Ship Checklist

- [x] Four non-negotiables: distinct POV, responsive (not mobile-only), polished, token-driven & AA.
- [x] Full-fledged demo: BI dashboard (KPIs + line/area, bar, doughnut charts + rollup table); data
      tables with inline-editable cells; full input range (text, search, select, textarea, toggle,
      segmented, stepper, filter chips, numeric/inline); centered modal (scrim + Esc + create);
      right-hand edit drawer + left mobile nav drawer; ≥2 inline edits; toasts + status chips;
      persistent shell where **every** nav item routes to a real, populated page; light + dark.
- [x] The rollup and consolidation worksheet tie out; the heatmap drives a live group-close %.
- [x] WCAG AA verified on both editions, tinted surfaces included.
- [x] Charts render on tab activation and re-render on edition swap; hidden canvases guarded
      (`offsetParent`); unique canvas ids per page; no unbounded chart growth; no console errors.
- [x] Wired into the gallery (root README table + landing card, count bumped).

<div align="center">
<sub>Confluence · Version 1.0 · The group-consolidation, many-books-one-truth member of the gallery.</sub>
</div>
