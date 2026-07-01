<div align="center">

# Pro Forma

### The model is the product — edit an assumption, watch the plan recompute.

A driver-based financial-modeling design system for **FP&A** — a graph-paper worksheet, a live
formula bar, and an editable driver grid whose every keystroke recomputes revenue, EBITDA, cash, and
a sensitivity tornado in real time. One console that's a full modeling cockpit on a monitor and a
glanceable app on a phone. Model + Terminal editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/pro-forma/) · [**📖 Design Spec**](./pro-forma.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-3B5BDB)
![License](https://img.shields.io/badge/license-MIT-181C13)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-2F49B0)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-0F8F80)

</div>

---

> Most enterprise UI shows you numbers someone else computed. **Pro Forma lets you compute them.** It
> is built for FP&A — the analysts who build the plan — where a number is never typed but **derived**,
> where the organizing truth is not a statement but an **assumption**, and where the hero surface is a
> live worksheet: an editable driver grid whose every edit recomputes the whole model in the same
> frame, under a formula bar that renders the governing equation like code.

The same tokens power a full driver-model console on a monitor and a glanceable app on a phone.
Worksheet-first, assumption-led, recompute-driven, and legible on bright graph paper *and* in a
late-night Terminal.

## The FP&A / driver-model pole

The gallery already has an *instrument panel* (**[Meridian](../meridian-enterprise/)**), a *financial
front page* (**[Broadsheet](../broadsheet/)**), and a *field/operations app*
(**[Frontline](../frontline/)**). Pro Forma is the deliberate **FP&A driver-model** pole — the plan
being built, not the actuals being reported:

| | Meridian | Broadsheet | Frontline | **Pro Forma** |
| --- | --- | --- | --- | --- |
| Domain | Enterprise ops | Enterprise data / editorial | Field operations | **FP&A / financial modeling** |
| Metaphor | Instrument panel | Financial front page | Ops app | **The spreadsheet / worksheet** |
| Organizing system | Modules & meters | Columns & rules | Work orders | **Drivers → outputs** |
| Hero element | Dashboard grid | Front page | Job cards | **Live driver grid + formula bar** |
| Palette | Carbon gray + blue | Newsprint + claret | Concrete + safety orange | **Graph-paper green-gray + formula indigo** |
| Type | IBM Plex Sans/Mono | Fraunces + Archivo | Saira + Martian Mono | **DM Sans + DM Mono** |

## Seven principles

1. **The model is the interface** — a worksheet of assumptions, not a report or a card wall.
2. **Everything recomputes, live** — edit a driver, every surface updates in the same frame.
3. **Assumptions are first-class objects** — name, unit, role, bounds, category, note.
4. **Worksheet-first, but terminal-capable** — Model is the hero; Terminal a first-class alternate.
5. **Tabular, never jittery** — monospaced figures, formulas, and cells; true minus.
6. **Sensitivity is the second signature** — inline swing bars + a ±10% EBITDA tornado + what-if.
7. **Responsive, never mobile-only** — desktop console *and* phone app from one system.

## What the demo shows

A full FP&A modeling console, responsive desktop ↔ mobile — **every nav item is a real page:**

- **Overview (BI)** — a rename-in-place model title, the signature **live formula bar**, a KPI strip
  with vs-prior sparklines, an editable key-driver grid, a sensitivity tornado, a modeled-vs-plan
  revenue projection, and a cost-mix doughnut — all recomputing live.
- **Drivers** — the full assumption register with **category filter chips**, **search**, inline
  editable cells, an EBITDA-leverage bar chart, and per-driver notes; click a row to open the
  **edit drawer** (name, unit, bounds, formula, note, apply-to-forecast toggle, Save/Cancel).
- **Projections** — a modeled P&L statement (derived, ties out) with a **12/24/36-month horizon
  segmented control**, a revenue-trend chart, and a cash-runway panel.
- **Scenarios** — Base / Upside / Downside as full driver presets: compare cards, a compare table,
  and a revenue-&-EBITDA grouped bar chart; load any scenario into the grid.
- **Sensitivity** — a **what-if panel** (driver select + a ± shock **stepper** → live EBITDA delta),
  the EBITDA tornado, and a swing table.
- **Reports** — a model-pack library plus a **custom-generation form** (type select, horizon
  segmented, format select, include-charts / lock-assumptions / email toggles, recipients, textarea).
- **Settings** — a **click-to-edit model name**, currency / fiscal-year selects, a units segmented
  control, a decimals stepper, and preference toggles (edition, auto-recompute, formula bar, rounding).
- Plus a global **New Driver modal** (scrim, Esc, steppers, tag chips, lock toggle → appends to the
  grid + recomputes), a **mobile nav drawer**, toasts, and the Model/Terminal edition toggle.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/pro-forma

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Edit any driver cell and watch the KPIs, projection, cost mix, and tornado recompute. Resize from
desktop down to phone width to see the same system reflow. The demo loads Tailwind (Play CDN),
DM Sans / DM Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including positive/negative and the graph-paper grid
— so switching editions is a class swap on `<body>`. Pro Forma is **worksheet-first**: it loads in
Model.

```css
:root, .light { --canvas:#F6F8F4; --surface:#FFFFFF; --ink:#1A1F17; --accent:#3B5BDB; /* Model */
                --grid:#E9EFE3; --chrome:#181C13; --pos:#0F8F80; --neg:#C43A4D; }
.dark          { --canvas:#10130C; --surface:#171B11; --ink:#EAEEE2; --accent:#6C86F0; /* Terminal */
                --grid:rgba(255,255,255,.032); --chrome:#0C0F08; --pos:#2CC4B0; --neg:#E7677A; }
```

Positive/negative colors and the grid are tokens too, so a driver cell, a chart bar, a sensitivity
mini-bar, and a KPI delta all read the same source — and Chart.js pulls them via
`getComputedStyle(document.body)`, so Terminal is a single `body.dark`.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Pro Forma · Version 1.0 · The FP&A, driver-model, "the model is the product" member of the gallery.</sub>
</div>
