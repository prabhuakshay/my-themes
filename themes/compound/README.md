<div align="center">

# Compound

### Capital compounds when it's allocated well — a portfolio of competing bets, ranked against the hurdle.

A capital-allocation design system for **capex and project finance** — a warm-granite ledger, a
bronze-gold accent, and a **Fund / Hold / Reject** decision as the organizing signal. One console
that's a full investment-committee cockpit on a monitor and a glanceable app on a phone. Deployed +
Reserve editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/compound/) · [**📖 Design Spec**](./compound.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-9A7B1F)
![License](https://img.shields.io/badge/license-MIT-2A241A)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-7A6013)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-2F6D46)

</div>

---

> Most enterprise UI reports what happened. **Compound decides what happens next.** It is built for
> the people who allocate a finite pool of capital — corporate development, capital planning, the
> investment committee — where a project is never a loose number but a **bet ranked against its peers**,
> where the organizing truth is a single **hurdle rate**, and where the hero surface is a ranking table
> that answers one question per project: **fund, hold, or reject.**

The same tokens power a full allocation cockpit on a monitor and a glanceable app on a phone.
Deployed-first, decision-led, hurdle-ranked, and legible in a bright committee room *and* in a
late-night Reserve.

## The capital-allocation pole

The gallery already has an *instrument panel* (**[meridian-enterprise](../meridian-enterprise/)**), a
*financial front page* (**[broadsheet](../broadsheet/)**), a *field operations app*
(**[frontline](../frontline/)**), and a statement-led *office of the CFO* (**[sterling](../sterling/)**).
Compound is the deliberate **investment-committee / capex** pole — money going *out* as bets, ranked
and decided:

| | Sterling | Broadsheet | Frontline | **Compound** |
| --- | --- | --- | --- | --- |
| Domain | Corporate finance / CFO | Enterprise data | Field operations | **Capital allocation / capex** |
| Metaphor | The ledger / statement | The front page | The field app | **Portfolio of competing bets** |
| Organizing system | Variance to plan | Story hierarchy | Task / status | **Rank vs. the hurdle rate** |
| Hero element | Financial statement | The headline | The work order | **The ranking table** |
| Palette | Ink-navy binder + gilt | Tinted newsprint + claret | Hi-vis concrete + orange | **Warm granite + bronze-gold** |
| Type | Hanken Grotesk / JetBrains | Fraunces / Archivo | Saira / Martian | **Libre Franklin / Roboto Mono** |

## Seven principles

1. **A dashboard is a portfolio of competing bets** — a ranked book, not a hero number.
2. **The hurdle rate is the single source of truth** — everything sorts and colors against it.
3. **Every decision has a consequence, computed live** — Fund recomputes deployed, headroom, IRR.
4. **Value, not just cost** — lead with NPV and IRR; spend and payback support.
5. **Deployed-first, but dark-capable** — Deployed is the hero; Reserve a first-class alternate.
6. **Tabular, never jittery** — monospaced, tabular figures; true minus; `$…M`.
7. **Responsive, never mobile-only** — desktop console *and* phone app from one system.

## What the demo shows

A full investment-committee console, responsive desktop ↔ mobile — **every nav item is a real page:**

- **Overview (BI)** — a KPI strip with trend sparklines, the signature **project ranking table** (with
  live fund/hold/reject), a capital-by-category doughnut, an NPV-by-project bar, and a deployment-trend
  area chart.
- **Projects** — the full ranking book with **search**, category **filter chips**, sortable headers, a
  risk column, an inline decision select, and **click-a-row to open the edit drawer**.
- **Pipeline** — the proposal funnel (intake → screening → review → committee → approved) with stage
  tiles, a funnel bar chart, an intake-trend chart, and a proposals table with an **inline stage select**.
- **Capital** — allocation vs. approved budget by category: a committed-mix doughnut, a committed-vs-
  budget bar chart, and a category-budget table with utilisation tracks.
- **Analysis** — per-project NPV / IRR / payback detail with a project selector, an assumptions panel,
  a **cumulative cash-flow** chart (crossing zero at payback), and an **IRR-sensitivity** bar.
- **Reports** — a report library plus a **custom-generation form** (select, segmented, toggles,
  recipients, textarea).
- **Settings** — the edition toggle, a **hurdle-rate stepper** and a **budget stepper** that re-read the
  whole book, and a **click-to-edit portfolio name**.
- Plus a global **New Project Proposal modal** (scrim, Esc, capex stepper, tag chips, fast-track
  toggle), a right-hand **edit drawer**, a **mobile nav drawer**, toasts, and the Deployed/Reserve
  toggle.

Set a project to **Fund** anywhere and capital deployed, available headroom, funded NPV, the doughnut,
and the capital-weighted **portfolio IRR** all recompute in the same tick.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/compound

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize from desktop down to phone width to see the same system reflow. The demo loads Tailwind (Play
CDN), Libre Franklin / Roboto Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including the fund/hold/reject decision colors — so
switching editions is a class swap on `<body>`. Compound is **deployed-first**: it loads in Deployed.

```css
:root, .light { --canvas:#F3F1EA; --surface:#FFFFFF; --ink:#221E17; --accent:#9A7B1F; /* Deployed */
                --chrome:#2A241A; --fav:#2F6D46; --hold:#6E6858; --unfav:#B0483B; }
.dark          { --canvas:#191510; --surface:#221D16; --ink:#EFE9DC; --accent:#C9A544; /* Reserve  */
                --chrome:#120F0A; --fav:#4FA972; --hold:#A79C86; --unfav:#D2685A; }
```

Decision colors are tokens too, so a decision pill, a row edge-mark, a chart bar, and a KPI chip all
read the same source — and Reserve is a single `body.dark`. Charts read the live token values via
`getComputedStyle` and rebuild on every edition swap.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Compound · Version 1.0 · The capital-allocation, hurdle-ranked, investment-committee member of the gallery.</sub>
</div>
