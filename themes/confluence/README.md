<div align="center">

# Confluence

### Many books, one truth — every entity rolls up, and the group ties out.

A consolidation design system for the **group controller** — a steel-indigo chrome over a cool
institutional canvas, an entity rollup that translates Local → FX → Consolidated and *ties out*, and a
clickable close heatmap (entities × tasks) that drives a live group-close %. One console that's a full
consolidation cockpit on a monitor and a glanceable app on a phone. Light + Dark editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/confluence/) · [**📖 Design Spec**](./confluence.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-445A9C)
![License](https://img.shields.io/badge/license-MIT-20294A)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-3D5AAE)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-1E8E5A)

</div>

---

> Most enterprise UI shows one company's numbers. **Confluence shows fourteen entities becoming one
> group.** It is built for the people who consolidate — group controllers, consolidation accountants,
> corporate finance — where the organizing act is a *confluence*: many local ledgers, in nine
> currencies, translated through FX, netted of intercompany, and closed on a schedule, flowing into a
> single consolidated truth that **ties out**.

The same tokens power a full consolidation-and-close console on a monitor and a glanceable app on a
phone. Institutional, provenance-first, rollup-driven, and legible in a bright office *and* in a
late-night close.

## The group-consolidation pole

The gallery already has an *instrument panel* (**[Meridian](../meridian-enterprise/)**), a *financial
front page* (**[Broadsheet](../broadsheet/)**), a *field operations app* (**[Frontline](../frontline/)**),
and an *office-of-the-CFO statement binder* (**[Sterling](../sterling/)**). Confluence is the deliberate
**group-consolidation** pole — not one company's books, but *many* books rolled into one:

| | Meridian | Broadsheet | Frontline | Sterling | **Confluence** |
| --- | --- | --- | --- | --- | --- |
| Domain | Platform ops | Editorial data | Field ops | Corporate finance | **Group consolidation** |
| Metaphor | Instrument panel | Front page | Field app | The ledger | **Rivers joining** |
| Organizing system | Signals | Columns/rules | Work orders | Variance to plan | **Rollup + close grid** |
| Hero element | Boxed grid | Broadsheet | Rounded cards | Statement | **Entity rollup + heatmap** |
| Palette | Cool gray | Newsprint | Hi-vis concrete | Ink-navy + gilt | **Blue-gray + steel-indigo** |
| Type | IBM Plex | Fraunces/Archivo | Saira | Hanken Grotesk | **Albert Sans / Fira Mono** |

## Seven principles

1. **Consolidation is the interface** — the rollup worksheet, not a card wall.
2. **It always ties out** — region subtotals, gross, less eliminations and NCI, to the group total.
3. **Many books, one truth** — every figure carries its entity, currency, FX rate, method, ownership.
4. **The close is a grid** — entities × tasks as a clickable heatmap driving a live group-close %.
5. **Tabular, never jittery** — monospaced, tabular figures; a true minus for eliminations.
6. **The chrome frames the confluence** — deep steel-indigo in both editions, a touch of accent.
7. **Responsive, never mobile-only** — desktop console *and* phone app from one system.

## What the demo shows

A full group-consolidation console, responsive desktop ↔ mobile — **every nav item is a real page:**

- **Overview (BI)** — a KPI strip with sparklines, a consolidated-revenue area chart, a revenue-by-
  region doughnut, the **entity rollup that ties out**, the **close heatmap**, and an eliminations bar.
- **Entities** — a searchable, region-filtered registry with inline close-status selects and ownership
  %; clicking a row opens the **edit drawer** (name, currency, ownership, close status, FX rate, local,
  method, sub-consolidated toggle, note, Save/Cancel writing back to the rollup).
- **Consolidation** — the Local → FX-translated → Consolidated **worksheet** with region subtotals, an
  eliminations and NCI line, a consolidated total, and a Gross → Consolidated **bridge chart**.
- **Eliminations** — a seller → buyer **intercompany matrix** with inline match-status selects, a
  by-type bar, a mix doughnut, and type filter chips.
- **Close** — the **entities × tasks heatmap**, clickable to advance each cell, with a by-status
  doughnut and a live group-close %.
- **FX Translation** — a rates table with an **inline-editable rate cell** that propagates into every
  entity's translation, plus per-currency exposure, FX impact, and an impact chart; a basis segmented
  control.
- **Reports** — a consolidation-report library plus a **custom-generation form** (select, segmented,
  toggles, recipients, textarea).
- **Settings** — the edition segmented control, a reporting-currency select, and a **click-to-edit
  group name**.
- Plus a global **Add Entity modal** (name, parent, currency, method, ownership stepper, note, eliminate
  toggle), a **mobile nav drawer**, toasts, and the Light/Dark edition toggle.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/confluence

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize from desktop down to phone width to see the same system reflow. The demo loads Tailwind (Play
CDN), Albert Sans / Fira Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including the semantic states — so switching editions
is a class swap on `<body>`. Confluence is **light-first**: it loads in the Light edition.

```css
:root, .light { --canvas:#EEF2F6; --surface:#FFFFFF; --ink:#17222E; --accent:#445A9C; /* Light */
                --chrome:#20294A; --pos:#1E8E5A; --neg:#C34733; }
.dark          { --canvas:#0E1420; --surface:#151D2C; --ink:#E6ECF3; --accent:#7E93D6; /* Dark */
                --chrome:#0A0F1B; --pos:#35C08A; --neg:#E06A54; }
```

Semantic colors are tokens too, so a rollup cell, a heatmap tile, a status chip, a chart bar, and a KPI
delta all read the same source — and Dark is a single `body.dark`.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Confluence · Version 1.0 · The group-consolidation, many-books-one-truth member of the gallery.</sub>
</div>
