<div align="center">

# Cardinal

### A dashboard is a revenue desk — read the number, then work the board.

A revenue design system for sales-pipeline software — warm paper surfaces, cardinal red + deep teal,
executive-scale figures, and a signature **pipeline stage-board** that flows Prospect → Won. One app
shell that's a full revenue console on desktop and a glanceable app on a phone. Daybook + After-hours
editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/cardinal/) · [**📖 Design Spec**](./cardinal.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-B4232F)
![License](https://img.shields.io/badge/license-MIT-1A140E)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-0F766E)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-157347)

</div>

---

> Most sales software buries the one number a revenue leader cares about — *are we going to make the
> quarter?* — under a grid of equal-weight widgets. **Cardinal puts the money first.** It's built for
> the revenue desk: pipeline, deals, forecast, and the accounts behind them.

The signature is a **pipeline stage-board** that reads left-to-right like a deal flowing from
Prospect to Won, and **executive-scale figures** set in a confident display face. Warm, deliberate,
and opinionated — cardinal red for the decisive action, deep teal for the steady one, on paper that
looks like a well-kept ledger, not a cold SaaS grid.

## The pole

This gallery's other themes — **[Meridian](../meridian-enterprise/)** (instrument panel),
**[Broadsheet](../broadsheet/)** (front page), **[Frontline](../frontline/)** (field app), and
**[Vellum](../vellum/)** (records studio) — each own a pole. Cardinal is the **revenue-desk** pole:

| | Meridian | Broadsheet | Frontline | Vellum | **Cardinal** |
| --- | --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | Records studio | **The revenue desk** |
| Domain | Enterprise | Data journalism | Field service | BI data entry | **Sales pipeline & forecast** |
| Surface | Flat, boxed | Flat, ruled | Tactile, elevated | Soft sheets | **Warm paper, elevated cards** |
| Palette | Carbon gray | Tinted newsprint | Hi-vis + orange | Porcelain + iris | **Warm paper + cardinal red + teal** |
| Type | IBM Plex | Fraunces/Archivo | Saira + Martian | Hanken + JetBrains | **Sora + Azeret Mono** |
| Signature concern | Governance | Provenance | Connectivity | Entry ergonomics | **Pipeline & forecasting** |

## Six principles

1. **The money is the hero** — one executive figure per screen, biggest thing in view.
2. **The pipeline is a board** — deals flow Prospect → Won; the funnel is legible at a glance.
3. **Stage is the system** — five stages drive color; never decorative; Lost is neutral, not alarm.
4. **Figures are typeset** — tabular mono money and percentages; prose in the display sans.
5. **Warm, not clinical** — warm paper and walnut, considered cardinal red, never a blue-gray grid.
6. **Two editions, one desk** — Daybook by day, After-hours after the close, from one token set.

## What the demo shows

A full revenue-desk app, responsive desktop ↔ mobile:

- **Overview (BI)** — executive KPI tiles + sparklines, the **pipeline stage-board**, an area chart
  (bookings vs target), a bar (value by stage), a doughnut (pipeline by region), and a recent-deals
  table.
- **Deals** — a sortable data table with filter chips, search, an **inline-editable stage cell**, a
  **click-to-edit amount**, and a right-hand **edit drawer** (with a probability slider).
- **Accounts** — account cards with ARR, health chips, owners, and a stats strip.
- **Forecast** — commit / best-case / pipeline rollup, a weighted-forecast gauge, a scenario toggle,
  a cumulative forecast-vs-quota chart, and a per-rep quota-attainment table.
- **Activities** — an activity timeline and a task checklist with toggle-complete.
- **Settings** — Daybook/After-hours toggle, currency select, a quota stepper, notification toggles,
  a company field, a notes textarea, and a click-to-edit profile name.
- Plus a centered **modal** (new deal), a **mobile nav drawer**, and toasts on every action.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/cardinal

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize the window from desktop down to phone width to see the same system reflow. The demo loads
Tailwind (Play CDN), Sora / Azeret Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including the five stage colors — so switching
editions is a class swap on `<html>`:

```css
:root     { --canvas:#FAF8F5; --surface:#FFFFFF; --ink:#1A140E; --accent:#B4232F; /* … Daybook */ }
html.dark { --canvas:#14100C; --surface:#1E1813; --ink:#F3ECE2; --accent:#C22F3A; /* … After-hours */ }
```

The accent splits into a **fill** token (`--accent`, always carries white text at AA) and an **ink**
token (`--accent-ink`, for red text/icons on tints and on dark), so cardinal red stays legible in
both editions. Stage chips derive their fill from a single stage token with `color-mix` — no second
palette to maintain.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Cardinal · Version 1.0 · The warm, figure-forward, revenue-desk member of the gallery.</sub>
</div>
