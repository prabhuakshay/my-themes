<div align="center">

# Zero

### Every dollar justified from zero — nothing inherited, every package defended.

A design system for **zero-based budgeting and spend management** — a stark near-black cost meter, a
concrete work surface, and the three-way **decision** (Approve / Challenge / Cut) as the organizing
signal. One console that's a full budget-committee cockpit on a monitor and a glanceable app on a
phone. Concrete + Graphite editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/zero/) · [**📖 Design Spec**](./zero.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-141414)
![License](https://img.shields.io/badge/license-MIT-141414)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-1D4ED8)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-15803D)

</div>

---

> Most budgeting UI shows you last year's number and asks for a bigger one. **Zero shows you nothing
> until it's justified.** It is built for FP&A, cost owners, and the budget committee — where no line
> item is inherited, where every package starts at **zero** and is *defended* on its own
> justification, and where the atomic act is a **decision**: Approve, Challenge, or Cut.

The same tokens power a full zero-based-budgeting console on a monitor and a glanceable app on a
phone. Concrete-first, decision-led, recompute-driven, and legible in a bright office *and* in a
late-night Graphite committee session.

## The zero-based-budgeting pole

The gallery already has an *instrument panel* (**[Meridian](../meridian-enterprise/)**), a *financial
front page* (**[Broadsheet](../broadsheet/)**), and a *field / operations app*
(**[Frontline](../frontline/)**). Zero is the deliberate **spend-management** pole — decision-led,
not status-, column-, or task-led:

| | Meridian | Broadsheet | Frontline | **Zero** |
| --- | --- | --- | --- | --- |
| Domain | Enterprise ops | Editorial data | Field operations | **Zero-based budgeting** |
| Metaphor | Instrument panel | Financial front page | Ops app | **The cost meter** |
| Organizing system | Status | Columns & rules | Task state | **The decision** |
| Hero element | Panel grid | Front page | Work cards | **The cost-package register** |
| Palette | Cool gray + blue | Newsprint + claret | Hi-vis + orange | **Concrete + graphite + green/amber/red** |
| Type | IBM Plex | Fraunces + Archivo | Saira + Martian Mono | **Instrument Sans / Anonymous Pro** |

## Seven principles

1. **Nothing is a given** — every package shows its zero-base and its delta; no inherited numbers.
2. **The decision is the interface** — Approve / Challenge / Cut, one verb set, one color set.
3. **Justify or cut** — every package carries a defense; an undefended dollar is a candidate to cut.
4. **Concrete-first, but dark-capable** — Concrete is the hero; Graphite a first-class alternate.
5. **Tabular, never jittery** — monospaced, tabular figures; true minus; `±$0` for zero.
6. **The meter frames the work** — stark near-black chrome in both editions, a stripe of green.
7. **Responsive, never mobile-only** — desktop console *and* phone app from one system.

## What the demo shows

A full budget-committee console, responsive desktop ↔ mobile — **every nav item is a real page:**

- **Overview (BI)** — a KPI strip with trend sparklines, a savings tracker (line/area), a
  decision-mix doughnut, a spend-by-category bar chart, and a recent-decisions table.
- **Cost Packages** — the hero register: prior base vs proposed with a colored Δ, an **inline
  decision select**, category filter chips, a decision segmented filter, search, **click-to-sort**
  headers, zebra rows, an empty-state, and **click a row to open the edit drawer**.
- **Categories** — baseline vs proposed grouped bars, a proposed-share doughnut, and a category
  detail table with over/under-base status chips.
- **Savings** — target-vs-achieved tiles, a **+/− target-savings stepper**, a cumulative-savings
  line chart, and a savings-by-category breakdown.
- **Approvals** — the queue of challenged packages as cards with **Approve / Review / Cut** actions,
  a decision-progress meter, and a live decision-mix doughnut.
- **Reports** — a report library plus a **custom-generation form** (select, segmented, toggles,
  recipients, textarea).
- **Settings** — an edition segmented control, fiscal-year and cost-center selects, preference
  toggles, and a **click-to-edit budget-owner** name.
- Plus a global **New Cost Package modal** (scrim, Esc, stepper amount, tag chips, recurring toggle),
  a right-hand **edit drawer**, a **mobile nav drawer**, toasts, and the Concrete/Graphite toggle.

Every decision — in the register, the queue, or the drawer — **recomputes** the KPIs, charts, totals,
and badges live.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/zero

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize from desktop down to phone width to see the same system reflow. The demo loads Tailwind (Play
CDN), Instrument Sans / Anonymous Pro, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including approve/challenge/cut — so switching
editions is a class swap on `<body>`. Zero is **concrete-first**: it loads in Concrete.

```css
:root, .light { --canvas:#F0F0ED; --surface:#FFFFFF; --ink:#141414; --accent:#1A1A1A; /* Concrete */
                --chrome:#141414; --fav:#15803D; --warn:#B45309; --unfav:#DC2626; }
.dark          { --canvas:#121211; --surface:#1B1B19; --ink:#F0F0EA; --accent:#EDEDE6; /* Graphite */
                --chrome:#0C0C0B; --fav:#3FB56B; --warn:#D98A2B; --unfav:#F06767; }
```

Decision colors are tokens too, so a register `<select>`, a table chip, a chart slice, and a KPI
delta all read the same source — and Graphite is a single `body.dark`.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Zero · Version 1.0 · The zero-based-budgeting, decision-led, spend-management member of the gallery.</sub>
</div>
