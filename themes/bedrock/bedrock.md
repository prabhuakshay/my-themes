# Bedrock — Theme Design Specification

**The definitions underneath the numbers.** Bedrock is a certified-metrics catalog, lineage, and
data-governance design system for the **financial metrics semantic layer** — the layer *below* the
dashboard, where a metric is not a chart but a **definition**: an identifier, an owner, a lineage, a
freshness, and a certification. It is built for the analytics-engineering and data-governance function:
people for whom the organizing truth is not the value of a number but whether the number can be
**trusted** — is it *Certified*, in *Review*, or *Deprecated*.

- **Metaphor:** the geological stratum / the spec sheet — bedrock is the certified layer everything
  above rests on.
- **Editions:** **Reference** (light, hero — a catalog reads like a spec sheet) and **Vault**
  (dark, after-hours). One class swap on `<body>`.
- **Type:** Lexend (UI, a legible humanist sans) + Roboto Mono (every identifier, figure, and tick).
- **Signature:** certification status — **Certified / Review / Deprecated** — as the semantic core,
  applied to every metric, source, and node; a deep graphite-teal "bedrock" chrome in both editions;
  a single certified-teal brand accent; and an inline, no-library **source → transform → metric
  lineage graph** drawn from positioned nodes and computed SVG beziers.

---

## Table of Contents

1. Design Principles
2. Bedrock vs. the others
3. Brand & Voice
4. Color System
5. The Certification System (signature)
6. Typography
7. Responsive Layout
8. Elevation, Radius & Surfaces
9. Components & Patterns
10. The Lineage Graph
11. Motion
12. Accessibility
13. Tokens in Practice
14. Anti-Patterns Bedrock Forbids
15. Pre-Ship Checklist

---

## 1. Design Principles

### P1 — The definition is the interface
The centerpiece is not a chart but a **metric definition**: a human name, a machine identifier
(`metric.net_rev`), a one-line unambiguous definition, an owner, a domain, a freshness, and a
certification. The catalog reads like a spec sheet, because in a semantic layer the spec *is* the
product.

### P2 — Trust is a status, not a vibe
Every metric carries an explicit **certification**: *Certified*, in *Review*, or *Deprecated*. This is
the organizing signal — it colors the catalog cell, the lineage metric node, the doughnut, and the
KPI strip. A number you cannot certify is a number you cannot ship.

### P3 — Lineage is legible
Where does a metric come from? Bedrock answers with a **source → transform → metric** graph drawn from
positioned nodes and computed bezier connectors — no external graph library. Pick any metric and its
definition traces back to the raw tables and dbt models that build it.

### P4 — Freshness is first-class
A definition is only as good as its data. Freshness (hours since last refresh) is shown as a
three-band signal — fresh ≤8h (green), aging ≤24h (amber), stale >24h (red) — on every metric, every
source, and every lineage node.

### P5 — Reference-first, but Vault-capable
Governance work happens in a bright office against a spec sheet. **Reference (light)** is the hero.
**Vault (dark)** is a first-class alternate for late reviews — a full token swap, never a dimmed
afterthought.

### P6 — The stratum frames the work
A deep graphite-teal chrome (sidebar + top bar) holds the light catalog like the bedrock layer holds
everything above it — present in both editions, a touch of certified teal on the active tab.

### P7 — Responsive, never mobile-only
The same tokens power a full governance console on a monitor and a glanceable app on a phone: the
catalog and registry tables scroll horizontally, KPI tiles reflow, the lineage graph scrolls, and
navigation collapses to a drawer.

---

## 2. Bedrock vs. the others

The gallery already holds an *instrument panel* (**Meridian**), a *financial front page*
(**Broadsheet**), a *field-operations app* (**Frontline**), and a *statement-led CFO console*
(**Sterling**). Bedrock is the **data-governance / semantic-layer** pole — nobody else owns *the
definitions underneath the numbers*.

| | Meridian | Broadsheet | Sterling | **Bedrock** |
| --- | --- | --- | --- | --- |
| Domain | Enterprise BI | Editorial data | Corporate finance | **Metrics semantic layer / governance** |
| Metaphor | Instrument panel | Financial front page | The ledger / statement | **The certified stratum / spec sheet** |
| Organizing system | Signals | Story hierarchy | Variance to plan | **Certification status** |
| Hero element | Dashboard | Front page | Financial statement | **Metric catalog + lineage graph** |
| Default edition | Light, cool gray | Tinted newsprint | Statement (cool) | **Reference (graphite-teal)** |
| Type | IBM Plex Sans/Mono | Fraunces + Archivo | Hanken / JetBrains Mono | **Lexend / Roboto Mono** |

Bedrock is definitional where the others are presentational: the value on a dashboard is Broadsheet's
concern; *where that value is defined, who owns it, and whether it is certified* is Bedrock's.

---

## 3. Brand & Voice

- **Name:** *Bedrock* — the solid layer beneath the surface; the foundation everything rests on. A
  certified metric is bedrock; an uncertified one is loose fill.
- **Voice:** precise, engineering-plain, audit-grade. Labels are catalog English (identifier,
  definition, owner, domain, freshness, lineage, certification). No hype, no emoji.
- **Tagline:** *The definitions underneath the numbers.*
- **Logo:** stacked strata in certified teal on graphite — the layers of the semantic model, with one
  certified node.

---

## 4. Color System

Every value is a CSS custom property. The edition class lives on `<body>` (bare `.light` / `.dark`),
so the tokens cascade to the whole subtree — including overlays like the modal and drawer, and the
JS reads them via `getComputedStyle(document.body)`.

### Reference edition (light) — default
```css
--canvas:#F5F6F7;  --surface:#FFFFFF;  --surface-2:#EDF1F1;
--line:#E2E6E8;    --line-2:#CBD3D6;
--ink:#1C2126;     --ink-2:#566069;    --ink-3:#89939B;
--chrome:#14201F;  --chrome-2:#1F2F2D; --chrome-line:#2C3E3B;   /* the stratum */
--accent:#0E9488;  --accent-2:#0B7A70; --accent-ink:#0B6E64;    /* certified teal */
--link:#1E77C4;
--cert:#16A34A;    --review:#B5871E;   --stale:#C34733;  --flat:#6B757F;
```

### Vault edition (dark) — alternate
```css
--canvas:#0D1315;  --surface:#141C1E;  --surface-2:#1C2629;
--line:#253032;    --line-2:#374547;
--ink:#E7EDEC;     --ink-2:#9AA7A6;    --ink-3:#66716F;
--chrome:#0A1211;  --chrome-2:#152321; --chrome-line:#213230;
--accent:#22B3A6;  --accent-2:#3ECBBD; --accent-ink:#22B3A6;
--link:#5AA6E0;
--cert:#35C06A;    --review:#E0B24E;   --stale:#E06A54;  --flat:#8A9794;
```

**Contrast (WCAG 2.1 AA).** Body ink on both canvases clears 4.5:1. Teal fills use light `--on-accent`
text for AA; teal *text* uses the darker `--accent-ink` on light surfaces. Certification green / review
amber / stale red are validated on their own soft-tinted chip backgrounds in both editions, and never
carry meaning by hue alone — an icon and a text label always accompany the color.

---

## 5. The Certification System (signature)

Bedrock's semantic core is **trust**, expressed as certification status.

| Token | Status | Meaning | Used for |
| --- | --- | --- | --- |
| `--cert`   | **Certified**  | Reviewed, owned, ships to BI | catalog cell, lineage metric node, doughnut, healthy sources, fresh ≤8h |
| `--review` | **Review**     | In governance review | catalog cell, aging ≤24h, degraded sources, medium-priority issues |
| `--stale`  | **Deprecated** | Superseded / do not use | catalog cell, stale >24h, down sources, high-priority issues |
| `--flat`   | **Uncertified**| Backlog, not yet triaged | doughnut backlog, paused sources, low-priority issues |

The same three-value scale is reused, honestly, across surfaces: a metric's **certification**, a
source's **status**, a node's **freshness**, and an issue's **priority** all read from one palette, so
a chip in the catalog, a node in the lineage graph, a slice in the doughnut, and a dot next to a
freshness figure all mean the same thing. Changing a metric's certification inline recomputes the
catalog-wide doughnut live.

---

## 6. Typography

- **UI / display:** Lexend (400–800). A legible humanist sans tuned for reading comprehension — apt
  for a catalog of definitions; distinct from the gallery's grotesks and serifs.
- **Identifiers / figures:** Roboto Mono, `font-variant-numeric: tabular-nums`. Every identifier
  (`metric.net_rev`, `raw.gl_lines`), freshness figure, row count, and axis tick is mono so columns
  and identifiers line up.
- **Labels:** mono, 10px, uppercase, `.13em` tracking — the schedule caps of a spec sheet.

---

## 7. Responsive Layout

- **≥1280px:** graphite-teal sidebar (240px) + top bar; catalog full-width; lineage as a picker +
  graph split; charts in a 3-col grid; KPI tiles in a 5-up strip.
- **768–1279px:** sidebar persists; grids fold to 1–2 columns; tiles 2–3-up.
- **<768px:** sidebar → **mobile nav drawer** (hamburger); tiles 2-up; every table gets a horizontal
  scroll container so identifiers never crush; the edit drawer and modal go full-width; the lineage
  graph scrolls horizontally.
- Shell is `h-screen` with an internally-scrolling `<main>`, so the stratum chrome stays pinned and no
  panel grows unbounded. Touch targets ≥ 44px.

---

## 8. Elevation, Radius & Surfaces

- **Radius:** `--r: 9px` (cards, panels), `--r-sm: 6px` (controls, chips, nodes). Calm, engineered.
- **Surfaces:** `--canvas` (page) → `--surface` (cards/catalog) → `--surface-2` (insets, fields, zebra
  rows). Hairlines use `--line`; the chrome seam uses the stronger `--chrome-line` so the stratum edge
  reads clearly.
- **Shadow:** low and cool on light; deeper on dark. Overlays (modal, drawer) use `--shadow-lg`.

---

## 9. Components & Patterns

- **App shell** — pinned graphite-teal sidebar + top bar with a branch chip, global metric search, a
  **Propose metric** button, edition toggle, issues bell, and a workspace footer. All **7** nav items
  route to a distinct, populated page: Overview, Catalog, Lineage, Domains, Issues, Sources, Settings.
- **KPI tiles** — value, a good/bad delta chip, a sub-label, and a sparkline.
- **Catalog table** (hero) — sortable-look headers, zebra + hover, responsive scroll, an **inline
  certification `<select>`** per row, and a click-to-open **edit drawer**. Search, domain filter
  chips, and a certified/review segmented filter.
- **Lineage graph** — an inline, no-library source → transform → metric explorer (see §10).
- **Data tables** — the Issues queue (inline priority + status selects) and the Sources registry
  (inline status select, freshness dots).
- **Inputs** — text, search, `<select>`, textarea, **toggle switch**, **segmented control**,
  **+/− stepper** (freshness SLA), **filter chips** (domain, source lineage, certify-from-domains),
  and numeric/inline-editable fields. All keyboard-usable with a visible blue focus ring.
- **Modal** — a centered **Propose a Metric** dialog: scrim, Esc-to-close, name, identifier,
  definition textarea, domain/owner selects, source-lineage tag chips, a request-certification toggle,
  and a working **Submit proposal** that adds the metric to the catalog + toast.
- **Edit drawer** — a right-hand **Edit metric** drawer opened by clicking a catalog (or overview) row:
  name, identifier, definition, owner, domain, certification, freshness (with live band), an
  **expose-in-BI toggle**, and a steward note. Save writes back to the row and refreshes the doughnut.
- **Inline edits** — the inline certification / status / priority `<select>`s in the tables, plus a
  **click-to-edit workspace name** on Settings that becomes an input with Save/Cancel.
- **Feedback** — kind-aware toasts (ok / info / warn) for every action; certification / freshness /
  status chips from one token set; coverage tracks on the Domains page.

---

## 10. The Lineage Graph

Bedrock's second signature (after certification). A metric's provenance is drawn as three columns —
**Sources**, **Transforms**, **Metric** — of positioned `.lg-node` cards, with connectors computed as
SVG cubic beziers between node centers.

- **No external library.** Node vertical centers are computed from the column length and container
  height; each edge is a single `M … C …` segment, and all edges in a layer are concatenated into one
  `<path>` `d` string (so no per-segment `<template>` lives inside the SVG, which Alpine cannot clone).
- **Focus any metric.** A left-hand picker swaps the focused metric; the getter recomputes nodes and
  connectors, and the metric node shows its live certification chip.
- **Semantic reuse.** Source nodes carry a freshness dot; source→transform edges use the neutral
  `--link-line`; transform→metric edges use the certified `--accent`.

---

## 11. Motion

Restrained and functional. Overlays fade/scale in ~200ms; the drawer and mobile nav slide; toasts rise
and auto-dismiss. **Charts do not animate** (`animation:false`) — a governance console draws instantly,
which also removes any first-frame render race. Hover/active transitions are ~120ms.
`prefers-reduced-motion: reduce` disables transitions and animations wholesale.

---

## 12. Accessibility

- WCAG 2.1 AA contrast on real surfaces in both editions, including tinted chip backgrounds.
- Status never by color alone — an icon and a text label reinforce every certification, freshness, and
  priority signal.
- Visible focus ring (`--link`, 2px, offset) on every interactive element.
- Esc closes the modal, edit drawer, and mobile nav (`@keydown.escape.window`).
- Toggles expose `role="switch"` / `aria-checked`; icon-only buttons and inline selects carry
  `aria-label`; the toast region is `aria-live="polite"`.
- Touch targets ≥ 44px; tabular figures and identifiers avoid layout shift under text scaling.

---

## 13. Tokens in Practice

```css
/* a certified catalog cell */
.chip-cert { color: var(--cert); background: var(--cert-soft); }
/* the certified metric node in the lineage graph */
.lg-node.metric { border-color: var(--accent); box-shadow: 0 0 0 1px var(--accent), var(--shadow); }
/* the certified-teal primary action */
.btn-primary { background: var(--accent); color: var(--on-accent); }
```

Because certification, freshness, chrome, teal, and surfaces are all tokens, a catalog chip, a lineage
node, a doughnut slice, a source-status cell, and a KPI delta all read from the same source — and the
Vault edition is a single `body.dark`.

---

## 14. Anti-Patterns Bedrock Forbids

- **A number without a definition.** Never show a metric you can't name, identify, and define.
- **Certification theater.** Never mark a metric Certified that has no owner or breached freshness.
- **Color-only status.** Never rely on green/amber/red without an icon or label.
- **A lineage you can't trace.** Never show a metric node with no path back to its sources.
- **Proportional-font identifiers.** Identifiers and figures are tabular mono, never UI sans.
- **A phone mock on a desktop.** Bedrock is a full console on a monitor and an app on a phone.
- **Decorative dark mode.** Vault is a real token swap, not a dimmed screenshot.

---

## 15. Pre-Ship Checklist

- [x] Four non-negotiables: distinct POV, responsive (not mobile-only), polished, token-driven & AA.
- [x] Full-fledged demo: BI dashboard (KPIs + line/area, bar, doughnut charts + a data table); data
      tables with inline-editable cells; full input range (text, search, select, textarea, toggle,
      segmented, stepper, filter chips, numeric/inline); centered modal (scrim + Esc + create);
      right-hand edit drawer + left mobile nav drawer; ≥2 inline edits; toasts + status chips;
      persistent shell where **every** nav item routes to a real, populated page; light + dark.
- [x] Certification is the semantic core; freshness is a three-band signal; lineage traces every metric.
- [x] WCAG AA verified on both editions, tinted surfaces included; status never by color alone.
- [x] Charts render on tab activation and re-render on edition swap; hidden canvases guarded
      (`offsetParent === null`); unique ids per page; no unbounded chart growth; **zero console errors**.
- [x] Wired into the gallery (root README table + landing card, count bumped).

<div align="center">
<sub>Bedrock · Version 1.0 · The metrics-semantic-layer, certification-led, data-governance member of the gallery.</sub>
</div>
