<div align="center">

# Tessera

### The warehouse mosaic — every SKU in its place.

A modular, tile-driven design system for procurement & inventory software — true-neutral zinc surfaces,
a single cobalt accent, a bento mosaic of KPIs, monospace figures, and two fixed status systems for stock
and purchase orders. One app shell that's a full supply-chain console on desktop and a thumb-driven app on
a phone. Floor + Nightshift editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/tessera/) · [**📖 Design Spec**](./tessera.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-2563EB)
![License](https://img.shields.io/badge/license-MIT-18181B)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-2563EB)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-15803D)

</div>

---

> Most inventory software is a wall of tables. **Tessera treats the console like a warehouse: a grid of
> tiles, each one a bin with a known place, a known count, and a known state.** It's built for the people
> who move stock and cut purchase orders — buyers, warehouse leads, and planners — and for the managers
> watching fill rate and turns from a desk.

The same tokens power a full procurement console on a monitor and a single-column app on a phone.
Neutral, modular, figure-dense, and organized around one idea: the **tessera** — a single tile in a
mosaic, where every SKU, KPI, and PO has its place.

## The fourth pole

This gallery's other themes each stake out a corner — **[Meridian](../meridian-enterprise/)** (a Carbon
instrument panel), **[Broadsheet](../broadsheet/)** (an editorial front page), and
**[Frontline](../frontline/)** (a tactile field-ops app). Tessera is the deliberate fourth pole:
**modular, true-neutral, and procurement-first.**

| | Meridian | Broadsheet | Frontline | **Tessera** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **Warehouse mosaic** |
| Domain | Governance / BI | Enterprise data | Field service | **Procurement & inventory** |
| Structure | Boxed grid | Hairline columns | Elevated cards | **Modular tile bento** |
| Surface | Cool gray | Tinted newsprint | Hi-vis concrete | **True-neutral zinc** |
| Type | IBM Plex | Fraunces/Archivo | Saira/Martian | **Familjen Grotesk + Geist Mono** |
| Accent | Carbon blue | Claret | Safety orange | **Cobalt `#2563EB`** |
| Signature | Governance | Provenance | Connectivity | **The mosaic grid + figures** |

## Six principles

1. **Everything is a tile** — a modular bento mosaic; nothing floats, everything has a place.
2. **True-neutral, so the data is the color** — a zinc grayscale with no temperature.
3. **One accent, one path forward** — cobalt marks the single primary action and active state.
4. **Figures are first-class** — every number is monospace and tabular-aligned.
5. **Status is a fixed vocabulary** — stock and PO states pair color with a label, never color alone.
6. **Edit in place, confirm with feedback** — steppers, inline selects, and a drawer, each with a toast.

## What the demo shows

A full procurement app, responsive desktop ↔ mobile, across five distinct pages:

- **Overview (BI)** — a bento mosaic of KPI tiles, an area chart (value & turns), a bar chart (stock by
  warehouse), a doughnut (PO status), and a replenishment watchlist table.
- **Inventory** — the full SKU table with sort-affordant headers, filter chips, an **inline stock
  stepper** (+/−), a **click-to-edit reorder point**, and an **inline stock-state `<select>`**.
- **Purchase orders** — a PO table with the draft/sent/partial/received/cancelled status system, an
  inline state select, and a right-hand **edit drawer**.
- **Suppliers** — a card mosaic (lead time, on-time %, open POs, spend, star rating) plus a scorecard
  table.
- **Settings** — the Floor/Nightshift edition toggle, table density, alert/automation switches, a
  safety-stock stepper, a note-template textarea, and a **click-to-edit** display name.
- Plus a centered **New purchase order modal**, a **mobile nav drawer**, a confirm-guarded reset, and
  toasts throughout.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/tessera

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize the window from desktop down to phone width to see the same mosaic reflow from four columns to one.
The demo loads Tailwind (Play CDN), Familjen Grotesk / Geist Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including both status systems — so switching editions is
a class swap on `<html>`:

```css
:root     { --canvas:#F4F4F5; --surface:#FFFFFF; --ink:#18181B; --accent:#2563EB; /* … Floor */ }
html.dark { --canvas:#09090B; --surface:#18181B; --ink:#FAFAFA; --accent:#3B82F6; /* … Nightshift */ }
```

Stock states (`--ok`, `--low`, `--warn`, `--crit`) and PO states share the same token source across chips,
tables, drawers, and charts — no raw hex in the markup.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Tessera · Version 1.0 · The modular, figure-dense, procurement-first member of the gallery.</sub>
</div>
