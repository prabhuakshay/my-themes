# Quorum — Theme Design Specification

**The board's view, told as a story.** Quorum is a premium, narrative design system for **board
reporting and investor relations** — the quarterly board pack, not the operational dashboard. It is
built for the people who assemble the read that goes into the room: the CFO, IR, and FP&A. Where an
analytics tool piles up tiles, Quorum composes a **document** — a cover, a one-line takeaway, headline
results, guidance measured against the range you gave the Street, the segment mix, an operating
scorecard, the board talking points, and the distribution list. It reads like something printed on
heavy stock and handed across a table.

- **Metaphor:** the board pack / the investor letter — a leather-bound quarterly, told as a story.
- **Editions:** **Boardroom** (dark, hero — the in-room read on a screen) and **Ivory** (light, the
  printed hand-out copy). One class swap on `<body>`.
- **Type:** DM Serif Display (the editorial voice) + DM Sans (UI) + DM Mono (every figure, tabular).
- **Signature:** the board-pack **cover** with a click-to-edit one-line takeaway; **guidance-vs-actual
  bullet charts** as the semantic core; a constant deep-charcoal "binder" chrome in both editions; a
  single champagne brand accent; ahead / behind vs. guidance as the meaning system.

---

## Table of Contents

1. Design Principles
2. Quorum vs. the others
3. Brand & Voice
4. Color System
5. The Guidance System (signature)
6. Typography
7. Responsive Layout
8. Elevation, Radius & Surfaces
9. Components & Patterns
10. The Cover & the Bullet Chart
11. Motion
12. Accessibility
13. Tokens in Practice
14. Anti-Patterns Quorum Forbids
15. Pre-Ship Checklist

---

## 1. Design Principles

### P1 — A board pack is a story, not a dashboard
The interface is a **document with a narrative arc**: it opens on a cover with a single headline, then
walks the reader through results, guidance, mix, efficiency, and commentary. Every page is a spread you
could print. Quorum never dumps forty tiles and calls it reporting — it *composes*.

### P2 — Say the one thing first
The most valuable object on the cover is the **one-line takeaway** — the sentence the Chair repeats.
It is large, serif, and editable in place, because the story is the product. Numbers support it; they
do not replace it.

### P3 — Measure against the promise
The organizing signal is **actual vs. the guidance range you gave the market** — not raw magnitude.
Above the range is a beat; inside is in line; below is a miss. A **bullet chart** shows the range as a
band and the actual as a mark, so a director sees "did we keep our word" at a glance.

### P4 — Boardroom-first, but print-ready
The pack is read on a screen in a dim room, so **Boardroom (dark)** is the hero. **Ivory (light)** is
the printed hand-out — a first-class full token swap, warm off-white like good paper, never a dimmed
afterthought.

### P5 — Premium restraint, generous whitespace
This is an executive **output**, not a dense ops console. Type is the ornament; space is the luxury.
One champagne accent, quiet surfaces, hairline rules. Boldness is spent on the serif and the cover —
everything else stays disciplined.

### P6 — The binder holds the pages
A constant deep-charcoal chrome (sidebar + top bar) frames the pages in **both** editions, like the
cover of a leather quarterly — a touch of champagne on the active tab. Structure you can feel.

### P7 — Responsive, never mobile-only
The same tokens power a full board-review console on a monitor and a glanceable app on a phone: the
cover reflows, tiles stack, tables scroll horizontally, and navigation collapses to a drawer.

---

## 2. Quorum vs. the others

The gallery already holds an *instrument panel* (Meridian), a *financial front page* (Broadsheet), a
*field ops app* (Frontline), and an *office-of-the-CFO ledger* (Sterling). Quorum is the
**board-reporting / investor-relations** pole — the audience is the Board and the Street, and the hero
is the **pack**, not the ledger behind it.

| | Broadsheet | Frontline | Sterling | **Quorum** |
| --- | --- | --- | --- | --- |
| Domain | Enterprise data (editorial) | Field / operations | Corporate finance / CFO | **Board reporting / IR** |
| Metaphor | Financial front page | Field app | The ledger / statement | **The board pack / letter** |
| Organizing system | Story hierarchy | Job status | Variance to plan | **Actual vs. guidance range** |
| Hero element | The front page | Work order | Financial statement | **The cover + bullet chart** |
| Default edition | Light (newsprint) | Hi-vis light | Statement (light) | **Boardroom (dark)** |
| Palette | Tinted newsprint + claret | Concrete + safety orange | Ink-navy + gilt | **Charcoal + champagne** |
| Type | Fraunces / Archivo | Saira / Martian | Hanken / JetBrains | **DM Serif / DM Sans / DM Mono** |

Quorum is dark-first where most are light, narrative where the others are operational, and
guidance-led where Sterling is variance-led — the outward-facing board story, not the internal books.

---

## 3. Brand & Voice

- **Name:** *Quorum* — the minimum needed for the board to decide; the moment the meeting is real.
- **Voice:** measured, confident, editorial. Full sentences, not fragments. Plain board English
  (guidance, net revenue retention, Rule of 40, free cash flow). No hype, no emoji, no exclamation.
- **Tagline:** *The board's view, told as a story.*
- **Logo:** a champagne "Q" set in the serif on charcoal — the quarterly, monogrammed.

---

## 4. Color System

Every value is a CSS custom property. The edition class lives on `<body>` (bare `.light` / `.dark`),
so the tokens cascade to the whole subtree — including overlays like the modal and the edit drawer —
and JS reads them via `getComputedStyle(document.body)`.

### Boardroom edition (dark) — default
```css
--canvas:#14161C;  --surface:#1B1E26;  --surface-2:#232732;
--line:#2A2F3A;    --line-2:#3B4250;
--ink:#E9ECF2;     --ink-2:#AEB6C4;    --ink-3:#868EA0;
--chrome:#101218;  --chrome-2:#1A1D25; --chrome-line:#262B35;   /* the binder */
--accent:#CBB681;  --accent-2:#DBC896; --accent-ink:#CBB681;    /* champagne */
--link:#7FA8DA;
--pos:#4FB783;     --neg:#E07A6A;      --flat:#9BA3B2;  --warn:#D9B45C;
```

### Ivory edition (light) — the printed hand-out
```css
--canvas:#EFEBE1;  --surface:#FBF9F4;  --surface-2:#F1EDE2;   /* warm paper */
--line:#E4DECF;    --line-2:#CFC6B2;
--ink:#22242C;     --ink-2:#575D68;    --ink-3:#6E6A61;
--chrome:#161821;  --chrome-2:#22252F; --chrome-line:#313641; /* charcoal, still */
--accent:#B79A55;  --accent-2:#A5883F; --accent-ink:#7E6526;  /* deeper champagne for AA text */
--link:#3B6CA8;
--pos:#14713F;     --neg:#B0442F;      --flat:#6E6A61;  --warn:#8A6A1E;
```

**Contrast (WCAG 2.1 AA).** Body ink on both canvases clears 4.5:1. Champagne *fills* use dark ink
text (`--on-accent`); champagne *text* uses the darker `--accent-ink` on light surfaces. Positive and
negative are validated on their own soft-tinted chip backgrounds in both editions and never carry
meaning by hue alone — a sign (+/−), an arrow, and often a word ("Above range") accompany the color.
The **chrome stays charcoal in both editions**, so its light text is designed once and always passes.

---

## 5. The Guidance System (signature)

Quorum's semantic core is **actual vs. the guidance range**, not magnitude.

| Token | Meaning | Used for |
| --- | --- | --- |
| `--pos`   | **Above the range** / beat | actual above guidance high, favorable deltas, positive momentum |
| `--neg`   | **Below the range** / miss | actual below guidance low, unfavorable deltas |
| `--accent`| **In the range** / on promise | actual within guidance, board highlights |
| `--warn`  | Watch | metrics flagged for the board to monitor |

The status is computed once from the range and drives the bullet chart, the status chip, the scorecard
`<select>`, and the edit drawer:

```js
statusLabel(g) { return g.act > g.high ? 'Above range' : (g.act >= g.low ? 'In range' : 'Below range'); }
pos(g, v)      { return Math.max(0, Math.min(100, (v - g.dmin) / (g.dmax - g.dmin) * 100)); }
```

So a revenue line landing at $642M against a $615–635M range reads as a beat (mark past the band),
while a metric inside its range reads champagne "in line" — same grammar, every metric.

---

## 6. Typography

- **Editorial / display:** DM Serif Display — the cover headline, the takeaway, page titles, and the
  big figures. This is the voice that makes the pack read like a letter, not a report.
- **UI / body:** DM Sans (400–700) — labels, controls, table cells, prose.
- **Figures / mono:** DM Mono, `font-variant-numeric: tabular-nums`, slight negative tracking. Every
  currency figure, percentage, ratio, and axis tick is mono so columns line up down a schedule.
- **Labels:** mono, 10px, uppercase, `.16em` tracking — the small-caps of a printed pack.

---

## 7. Responsive Layout

- **≥1280px:** charcoal sidebar (256px) + top bar; cover as a full spread; content in a centered
  1180px measure; KPI tiles 4-up; charts in a 2:1 grid.
- **768–1279px:** sidebar persists; grids fold to 1–2 columns; tiles 2-up.
- **<768px:** sidebar → **mobile nav drawer** (hamburger); tiles stack; every table gets a horizontal
  scroll container so columns never crush; the edit drawer and modal go full-width.
- Shell is `h-screen` with an internally-scrolling `<main>`, so the binder chrome stays pinned and no
  panel grows unbounded. Touch targets ≥ 44px.

---

## 8. Elevation, Radius & Surfaces

- **Radius:** `--r: 12px` (cards, panels) and `--r-sm: 8px` (controls, chips) — soft and premium, not
  playful.
- **Surfaces:** `--canvas` (page) → `--surface` (cards) → `--surface-2` (insets, fields, zebra).
  Hairlines use `--line`; structural rules and the cover edge use the stronger `--line-2`.
- **Shadow:** low and warm on Ivory; deeper on Boardroom. Overlays (modal, drawer) use `--shadow-lg`.

---

## 9. Components & Patterns

- **App shell** — pinned charcoal sidebar + top bar with a period chip, a view segmented control
  (Quarter / Full year / vs Guidance), a global **New board pack** button, the edition toggle, and a
  confidential footer. **Every one of the 7 nav items routes to a distinct, populated page.**
- **The cover** — the board-pack front page: period, a beat/miss chip, and the click-to-edit one-line
  takeaway (see §10).
- **KPI tiles** — headline value, an above/below chip vs guidance, and a vs-guidance sparkline.
- **Bullet charts** — guidance-vs-actual, the signature (see §10), each with an editable talking point.
- **Data tables** — headline scorecard, guidance scorecard, segment detail, operating metrics, and the
  distribution list: mono figures, sortable-look headers, zebra + hover, responsive scroll, an
  **inline-editable status `<select>`**, and a per-recipient **deliver toggle**.
- **Inputs** — text, search, `<select>`, textarea, **toggle switch**, **segmented control**,
  **+/− stepper** (board copies, rounding), **filter chips** (talking-point status, pack tags), and
  numeric/inline-editable fields. All keyboard-usable with a visible focus ring.
- **Modal** — a centered **New board pack** dialog: scrim, Esc-to-close, title, period/audience selects,
  a key-message textarea, a copies stepper, tag chips, a confidential toggle, and a working **Create
  pack** → toast.
- **Edit drawer** — a right-hand **Edit guidance line** drawer opened from any scorecard row or the
  bullet-chart pencil: metric name, actual, guidance low/high, a live result chip, board status, a
  highlight-for-board toggle, and commentary — Save writes back and updates the bullets and scorecard.
- **Inline edits** — the inline status `<select>` in tables, plus **three** click-to-edit surfaces: the
  cover takeaway, each guidance talking point, each board narrative point, and the settings company name.
- **Feedback** — toasts for every action; above/below/in-line/watch **chips** from one token set.

---

## 10. The Cover & the Bullet Chart

Two signature objects carry the theme.

**The cover** is the front page of the pack: an editorial spread with the period set large in DM Serif,
a beat/miss chip, and the **one-line takeaway** — a serif sentence that becomes a textarea on click,
with Save/Cancel. It is the highest-value editable object in the product, because the board reads the
sentence before the numbers.

**The bullet chart** measures a metric against its guidance range: a `--surface-2` track, an
`--accent-soft` **band** (the guidance low→high range), a champagne **fill** to the actual, and an ink
**mark** at the actual value. Above the band is a beat, inside is in line, below is a miss — the status
chip and the scorecard `<select>` read the same computed result. Each bullet carries a click-to-edit
talking point, so the chart and its story travel together.

---

## 11. Motion

Restrained and functional. Overlays fade/scale in ~200ms; the drawer and mobile nav slide; toasts rise
and auto-dismiss. **Charts do not animate** (`animation:false`) — an executive read draws instantly,
which also removes any first-frame render race. Hover/active transitions are 120ms. `prefers-reduced-
motion` disables transitions and animations entirely.

---

## 12. Accessibility

- WCAG 2.1 AA contrast on real surfaces in both editions, including tinted chip backgrounds.
- Status never by color alone — sign, arrow icon, and a word ("Above range") reinforce it.
- Visible focus ring (`--link`, 2px, offset) on every interactive element.
- Esc closes the modal, edit drawer, mobile nav, and every inline editor (`@keydown.escape.window`).
- Toggles expose `role="switch"` / `aria-checked`; icon-only buttons carry `aria-label`.
- Touch targets ≥ 44px; tabular figures avoid layout shift as values change.

---

## 13. Tokens in Practice

```css
/* the guidance band and actual mark */
.bullet-band { background: var(--accent-soft); border-inline: 1px solid var(--accent); }
.bullet-mark { background: var(--ink); box-shadow: 0 0 0 2px var(--surface); }
/* the champagne primary action */
.btn-primary { background: var(--accent); color: var(--on-accent); }
/* an above-range chip */
.chip-pos { color: var(--pos); background: var(--pos-soft); }
```

Because above/below, champagne, chrome, and surfaces are all tokens, a bullet band, a status chip, a
chart series, and a KPI delta all read from the same source — and Ivory is a single `body.light`.

---

## 14. Anti-Patterns Quorum Forbids

- **A tile wall pretending to be a board pack.** Quorum composes a document with a narrative arc.
- **Magnitude without the promise.** Never show an actual without the guidance range it is measured on.
- **Color-only meaning.** Never rely on green/red without a sign, arrow, or word.
- **Proportional-font figures.** Money is tabular DM Mono; columns must line up.
- **A phone mock on a desktop.** Quorum is a full console on a monitor and an app on a phone.
- **Decorative dark mode.** Boardroom is the hero and Ivory a real token swap — neither is a dimmed
  screenshot of the other.
- **Chrome that changes edition.** The charcoal binder is a constant; the pages change, not the cover.

---

## 15. Pre-Ship Checklist

- [x] Four non-negotiables: distinct POV, responsive (not mobile-only), polished, token-driven & AA.
- [x] Full-fledged demo: BI page (KPIs + line/area, bar, doughnut charts + a data table); data tables
      with inline-editable cells; full input range (text, search, select, textarea, toggle, segmented,
      stepper, filter chips, numeric/inline); centered modal (scrim + Esc + create); right-hand edit
      drawer + left mobile nav drawer; ≥2 inline edits; toasts + status chips; persistent shell where
      **every** nav item routes to a real, populated page; Boardroom + Ivory.
- [x] Guidance status computed once from the range; drives bullets, chips, scorecard, and drawer.
- [x] WCAG AA verified on both editions, tinted surfaces included; chrome constant in both.
- [x] Charts render on tab activation and re-render on edition swap; hidden canvases guarded
      (`offsetParent`); prior instances destroyed (`Chart.getChart`); no unbounded growth; no console
      errors (verified headless, 0 errors).
- [x] Wired into the gallery (root README table + landing card).

<div align="center">
<sub>Quorum · Version 1.0 · The board-reporting, investor-relations, story-led member of the gallery.</sub>
</div>
