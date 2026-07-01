<div align="center">

# Bedrock

### The definitions underneath the numbers — every metric certified, owned, and traced.

A certified-metrics catalog, lineage, and data-governance design system for the **financial metrics
semantic layer** — a graphite-teal "bedrock" stratum, a certified-teal accent, and
Certified / Review / Deprecated status as the organizing signal. One console that's a full governance
cockpit on a monitor and a glanceable app on a phone. Reference + Vault editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/bedrock/) · [**📖 Design Spec**](./bedrock.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-0E9488)
![License](https://img.shields.io/badge/license-MIT-14201F)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-1E77C4)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-16A34A)

</div>

---

> Most enterprise UI shows you the number. **Bedrock shows you the definition underneath it.** It is
> built for the analytics-engineering and data-governance function — where a metric is not a chart but
> a spec: an identifier, an owner, a lineage, a freshness, and a **certification**. The organizing
> truth is not the value of a number but whether the number can be *trusted*.

The same tokens power a full catalog-and-lineage console on a monitor and a glanceable app on a phone.
Reference-first, definition-led, certification-driven, and legible in a bright office *and* in a
late-night Vault.

## The data-governance pole

The gallery already has an *instrument panel* (**[Meridian](../meridian-enterprise/)**), a *financial
front page* (**[Broadsheet](../broadsheet/)**), a *field-operations app* (**[Frontline](../frontline/)**),
and a *statement-led CFO console* (**[Sterling](../sterling/)**). Bedrock is the deliberate
**metrics-semantic-layer / governance** pole — the layer *below* the dashboard:

| | Meridian | Broadsheet | Sterling | **Bedrock** |
| --- | --- | --- | --- | --- |
| Domain | Enterprise BI | Editorial data | Corporate finance | **Metrics semantic layer / governance** |
| Metaphor | Instrument panel | Financial front page | The ledger / statement | **The certified stratum / spec sheet** |
| Organizing system | Signals | Story hierarchy | Variance to plan | **Certification status** |
| Hero element | Dashboard | Front page | Financial statement | **Metric catalog + lineage graph** |
| Palette | Cool gray | Tinted newsprint | Ink-navy binder + gilt | **Graphite-teal + certified teal** |
| Type | IBM Plex Sans/Mono | Fraunces + Archivo | Hanken / JetBrains Mono | **Lexend / Roboto Mono** |

## Seven principles

1. **The definition is the interface** — a metric catalog of names, identifiers, and definitions.
2. **Trust is a status, not a vibe** — Certified / Review / Deprecated on every metric.
3. **Lineage is legible** — a no-library source → transform → metric graph you can trace.
4. **Freshness is first-class** — a three-band signal (fresh / aging / stale) everywhere.
5. **Reference-first, but Vault-capable** — Reference is the hero; Vault a first-class alternate.
6. **The stratum frames the work** — deep graphite-teal chrome in both editions, a touch of teal.
7. **Responsive, never mobile-only** — desktop console *and* phone app from one system.

## What the demo shows

A full data-governance console, responsive desktop ↔ mobile — **every nav item is a real page:**

- **Overview (BI)** — a KPI strip with sparklines, a certification-status doughnut, a metrics-by-domain
  bar, a certified-coverage area chart, and a **Needs Attention** table with an inline certification
  select.
- **Catalog** — the full metric catalog: sortable-look headers, search, domain **filter chips**, a
  certified/review **segmented** filter, an **inline certification `<select>`** per row, and
  click-a-row to open the **edit drawer**.
- **Lineage** — a metric picker plus an inline, no-library **source → transform → metric graph** built
  from positioned nodes and computed SVG bezier connectors; pick any metric to trace its definition.
- **Domains** — metrics grouped by business domain with **coverage bars**, a domain bar chart, and a
  certification doughnut.
- **Issues** — a governance-issue queue with **inline priority and status selects**, filter segmented
  control, and an issues-by-priority doughnut.
- **Sources** — a data-source registry with freshness dots and an **inline-editable status select**.
- **Settings** — the edition **segmented** control, a default-branch select, a **freshness-SLA stepper**,
  certify-from-domain chips, preference toggles, a governance-note textarea, and a **click-to-edit
  workspace name**.
- Plus a global **Propose a Metric modal** (scrim, Esc, identifier, definition, source-lineage chips,
  request-certification toggle → adds to the catalog), a **mobile nav drawer**, kind-aware toasts, and
  the Reference/Vault edition toggle.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/bedrock

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize from desktop down to phone width to see the same system reflow. The demo loads Tailwind (Play
CDN), Lexend / Roboto Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including certification, freshness, and status — so
switching editions is a class swap on `<body>`. Bedrock is **reference-first**: it loads in Reference.

```css
:root, .light { --canvas:#F5F6F7; --surface:#FFFFFF; --ink:#1C2126; --accent:#0E9488; /* Reference */
                --chrome:#14201F; --cert:#16A34A; --review:#B5871E; --stale:#C34733; }
.dark          { --canvas:#0D1315; --surface:#141C1E; --ink:#E7EDEC; --accent:#22B3A6; /* Vault */
                --chrome:#0A1211; --cert:#35C06A; --review:#E0B24E; --stale:#E06A54; }
```

Status colors are tokens too, so a catalog chip, a lineage node, a doughnut slice, a source-status
cell, and a KPI delta all read the same source — and Vault is a single `body.dark`.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Bedrock · Version 1.0 · The metrics-semantic-layer, certification-led, data-governance member of the gallery.</sub>
</div>
