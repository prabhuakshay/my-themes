<div align="center">

# Sage

### People software that reads like a roster, not a spreadsheet.

A humane, airy design system for HR & people-ops software — cream paper surfaces, moss green + clay
accents, a four-state employment-status system, and honest tabular figures. One app shell that's a
full people console on desktop and a thumb-driven app on a phone. Daylight + Lamplight editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/sage/) · [**📖 Design Spec**](./sage.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-4F7A4E)
![License](https://img.shields.io/badge/license-MIT-23261F)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-C1683C)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-3F7A4E)

</div>

---

> Most HR software treats people as rows in a database — dense grids, system jargon, and the visual
> warmth of a payroll export. **Sage treats the org as a roster you tend to.** It's built for people
> teams — HR business partners, recruiters, people-ops leads, and the managers they support — for
> the calm, considered work of hiring, onboarding, retaining, and caring for a workforce.

The same tokens power a full people console on a monitor and a glanceable, thumb-driven app on a
phone. Warm, low-density, status-driven, and voiced like a thoughtful partner rather than a system.

## The pole

This gallery's other themes are cool, dense, or hi-vis. Sage is the **warm, airy, people-first**
pole:

| | Meridian | Broadsheet | Frontline | **Sage** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **The roster** |
| Domain | Generic BI | Enterprise data | Field service | **HR / people ops** |
| Surface | Flat, boxed | Flat, ruled | Tactile, hi-vis | **Warm cream paper** |
| Density | High | Editorial | Glanceable | **Low — airy** |
| Palette | Carbon gray | Tinted newsprint | Hi-vis + orange | **Cream + moss + clay** |
| Type | IBM Plex | Fraunces/Archivo | Saira + Martian Mono | **Schibsted Grotesk + Overpass Mono** |
| Signature concern | Governance | Provenance | Connectivity | **People & employment status** |

## Six principles

1. **The roster is the metaphor** — the person, not a database row, is always the primary object.
2. **Humane before dense** — generous space, one idea per region; people aren't inventory.
3. **Status is the system** — four employment states drive color; never decorative.
4. **Honest, legible numbers** — tabular mono figures, trends labelled with direction and magnitude.
5. **Quiet, warm, and calm** — boldness spent on one moss accent; everything else stays soft.
6. **Responsive, never mobile-only** — desktop console *and* phone app from one system.

## What the demo shows

A full people-ops app, responsive desktop ↔ mobile:

- **Dashboard (BI)** — KPI tiles + headcount-growth area chart, hires-vs-exits bar chart, and a
  headcount-by-department doughnut, plus a department-snapshot data table.
- **People (roster)** — a data table with status filter chips, a department filter, search, sortable
  headers, an **inline-editable status cell**, and a right-hand **edit drawer** (open a person → edit
  inline → Save/Cancel).
- **Hiring** — open-roles table with an **inline-editable stage cell**, pipeline KPIs, and this
  month's onboarding cohort.
- **Time off** — leave requests with approve/decline, semantic status chips, and a request form with
  a **+/− stepper**, date pickers, and a note.
- **Settings** — Daylight/Lamplight edition toggle, preference switches, and a **click-to-edit name**
  (inline edit).
- Plus a centered **modal** (Add person), a **mobile nav drawer**, toasts, and the full input range
  (text, search, select, textarea, toggle, segmented control, stepper, chips).

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/sage

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize the window from desktop down to phone width to see the same system reflow. The demo loads
Tailwind (Play CDN), Schibsted Grotesk / Overpass Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including the four employment-status colors — so
switching editions is a class swap:

```css
:root     { --canvas:#F4F2EB; --surface:#FFFFFF; --ink:#23261F; --accent:#4F7A4E; /* … Daylight */ }
html.dark { --canvas:#191B14; --surface:#22251C; --ink:#ECEADF; --accent:#86B27F; /* … Lamplight */ }
```

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Sage · Version 1.0 · The warm, airy, people-first member of the gallery.</sub>
</div>
</content>
