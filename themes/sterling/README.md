<div align="center">

# Sterling

### The books balance — every figure ties out, every variance in its place.

A statement-grade design system for **corporate finance and the office of the CFO** — an ink-navy
reporting binder, a gilt accent, and favorable/unfavorable variance as the organizing signal. One
console that's a full financial-close cockpit on a monitor and a glanceable app on a phone.
Statement + Ledger editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/sterling/) · [**📖 Design Spec**](./sterling.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-B4893B)
![License](https://img.shields.io/badge/license-MIT-172436)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-2D6CB5)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-1E8E5A)

</div>

---

> Most enterprise UI is a form on a white page. **Sterling is a financial statement.** It is built
> for the people who keep the books — controllers, FP&A, treasury, the CFO — where a number is never
> loose but **ties out**, where the organizing truth is not price but **variance to plan**, and where
> the hero surface is a P&L, a balance sheet, a cash-flow statement.

The same tokens power a full close-and-report console on a monitor and a glanceable app on a phone.
Paper-first, statement-led, variance-driven, and legible in a bright office *and* in a late-night
Ledger.

## The corporate-finance pole

The gallery already has a *revenue desk* (**[Cardinal](../cardinal/)**) and a *records pipeline*
(**[Vellum](../vellum/)**). Sterling is the deliberate **office-of-the-CFO** pole — the internal
finance function, not the markets outside:

| | Cardinal | Vellum | Dossier | **Sterling** |
| --- | --- | --- | --- | --- |
| Domain | Sales / revenue | BI data entry | Legal / contracts | **Corporate finance / CFO** |
| Metaphor | Revenue desk | The record | The case file | **The ledger / statement** |
| Organizing system | Pipeline stages | Record pipeline | Obligations | **Variance to plan** |
| Hero element | Deal board | Entry sheet | Case file | **Financial statement** |
| Palette | Warm paper + red/teal | Porcelain + iris | Porcelain + burgundy | **Ink-navy binder + gilt** |
| Type | Sora | serif-led | Spectral (serif) | **Hanken Grotesk / JetBrains Mono** |

## Seven principles

1. **The statement is the interface** — a real P&L / balance sheet / cash flow, not a card wall.
2. **Every figure ties out** — subtotals sum, the sheet balances, cash rolls forward.
3. **Variance is the system** — favorable/unfavorable to plan, context-aware for expenses.
4. **Paper-first, but dark-capable** — Statement is the hero; Ledger a first-class alternate.
5. **Tabular, never jittery** — monospaced, tabular figures; true minus; em-dash zero.
6. **The binder frames the work** — deep ink-navy chrome in both editions, a touch of gilt.
7. **Responsive, never mobile-only** — desktop console *and* phone app from one system.

## What the demo shows

A full office-of-the-CFO console, responsive desktop ↔ mobile — **every nav item is a real page:**

- **Overview (BI)** — a KPI strip with vs-plan sparklines, the income statement, a budget-vs-actual
  bar+line, an operating-spend doughnut, a cash-runway area chart, and the month-end close checklist.
- **Income Statement** — a full P&L with Actual / Budget / Var $ / Var % / % of revenue, a revenue &
  net-income chart, a margin-trend chart, and a **click-to-edit "Prepared by"** field.
- **Balance Sheet** — a balanced statement (assets, liabilities, equity) with prior-period + change
  columns, liquidity ratios, and an asset-composition doughnut.
- **Cash Flow** — an indirect-method statement (operating / investing / financing) with inflows and
  outflows colored, a cash-by-activity bar, and a cash-balance trend.
- **Budget vs Actual** — department spend with **filter chips** (group), a **+/− reforecast stepper**,
  and a favorable/unfavorable **variance tornado chart**.
- **AR / AP** — aging tiles + a detail table with an **inline status select**; clicking a row opens a
  right-hand **edit drawer** (name, type, buckets, note, escalate toggle, Save/Cancel).
- **Close** — the month-end checklist as a full page with owners, due days, and inline status.
- **Reports** — a report library plus a **custom-generation form** (select, segmented, toggles,
  recipients, textarea).
- Plus a global **New Journal Entry modal** (scrim, Esc, stepper, tag chips, recurring toggle), a
  **mobile nav drawer**, toasts, and the Statement/Ledger edition toggle.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/sterling

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize from desktop down to phone width to see the same system reflow. The demo loads Tailwind (Play
CDN), Hanken Grotesk / JetBrains Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including favorable/unfavorable — so switching
editions is a class swap on `<body>`. Sterling is **paper-first**: it loads in Statement.

```css
:root, .light { --canvas:#F4F6F9; --surface:#FFFFFF; --ink:#17212E; --accent:#B4893B; /* Statement */
                --chrome:#172436; --fav:#1E8E5A; --unfav:#C34733; }
.dark          { --canvas:#10151C; --surface:#161C25; --ink:#E8EDF3; --accent:#D8B15A; /* Ledger */
                --chrome:#0C1119; --fav:#35C08A; --unfav:#E06A54; }
```

Variance colors are tokens too, so a P&L cell, a table chip, a chart bar, and a KPI delta all read the
same source — and Ledger is a single `body.dark`.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Sterling · Version 1.0 · The corporate-finance, statement-led, office-of-the-CFO member of the gallery.</sub>
</div>
