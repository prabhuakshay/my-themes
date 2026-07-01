<div align="center">

# Foundry

### Watch the metal move through the plant.

A design system for data-pipeline & ETL orchestration consoles — a blueprint-grid slate surface,
a molten-amber execution graph you can watch flow, a six-state run system, and monospace run logs
that read like the terminal you trust. One app shell that's a full orchestration console on a
monitor and a thumb-driven ops app on a phone. Blueprint + Control Room editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/foundry/) · [**📖 Design Spec**](./foundry.md) · [**← All themes**](../../README.md)

![Version](https://img.shields.io/badge/version-1.0-F97316)
![License](https://img.shields.io/badge/license-MIT-0F1B2A)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-2563EB)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-059669)

</div>

---

> Most data tools show you a table of runs and call it observability. **Foundry treats the pipeline
> as a plant** — raw material enters at a source, flows through extract, transform, and load, and
> comes out refined. The interface is the shop floor: a blueprint grid under every surface, molten
> amber animating the live edges of the execution graph, and every number and log line set in
> monospace so it aligns like a spec sheet.

It's built for the people who build and babysit pipelines — data and platform engineers watching
throughput, chasing a failed run, and reading stdout at 2 a.m.

## The fifth pole

This gallery's other themes are an instrument panel (**[Meridian](../meridian-enterprise/)**), a
front page (**[Broadsheet](../broadsheet/)**), a field-ops app (**[Frontline](../frontline/)**),
and an entry-first BI system (**[Vellum](../vellum/)**). Foundry is the deliberate
**orchestration / observability** pole — developer-facing, blueprint-technical, monospace-forward,
and equally at home in a dark control room:

| | Meridian | Broadsheet | Frontline | Vellum | **Foundry** |
| --- | --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | BI entry | **Data plant / ETL** |
| Audience | Analysts | Executives | Field crews | BI consumers | **Data engineers** |
| Surface | Flat, boxed | Flat, ruled | Tactile, rounded | Soft editorial | **Blueprint-grid slate** |
| Palette | Carbon gray | Newsprint | Hi-vis orange | Warm neutral | **Slate + molten amber** |
| Type | IBM Plex | Fraunces/Archivo | Saira/Martian | Serif + sans | **Chivo + Sometype Mono** |
| Signature | Governance | Provenance | Connectivity | First impression | **Execution graph + run logs** |
| Modes | White / Gray | Day / Evening | Field / Shift | Light / Dark | **Blueprint / Control Room** |

## Six principles

1. **The pipeline is the picture** — lead with the execution graph, not a wall of tiles.
2. **State is the system** — six run states drive color everywhere; never decorative.
3. **Numbers are monospace, and they align** — tabular figures for every count, duration, and ID.
4. **The log is a first-class surface** — stdout gets a real console, not a tooltip.
5. **Blueprint, not chrome** — a faint engineering grid, hairlines, one molten-amber accent.
6. **Two rooms, one plant** — Blueprint for the day desk, Control Room for the night shift.

## What the demo shows

A full orchestration console, responsive desktop ↔ mobile, every nav item a real populated page:

- **Dashboard (BI)** — KPI tiles + an animated **execution graph** (source → extract → transform →
  load) + throughput/duration/state charts + a recent-runs table.
- **Pipelines** — a data table with sortable headers, filter chips, search, a time-range segmented
  control, and **two inline-editable cells** (schedule + state `<select>`) plus a right-hand
  **edit drawer**.
- **Runs** — a run list and a real **monospace run-log console** with colour-keyed
  `INFO/OK/WARN/ERROR/DEBUG` levels.
- **Connections** — source/sink cards with a **click-to-edit name** (inline edit), enable toggles,
  and a Test action.
- **Settings** — Blueprint/Control Room edition toggle, switches, numeric **steppers**
  (concurrency, retries), a select, a textarea, and a click-to-edit display name.
- Plus a centered **modal** (new pipeline), a **mobile nav drawer**, an environment switcher,
  toasts, and a persistent scheduler-status indicator.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/foundry

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Toggle the sun/moon in the top bar to swap **Blueprint ↔ Control Room**, and resize from desktop
down to phone width to see the same system reflow. The demo loads Tailwind (Play CDN), Chivo /
Sometype Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including the six run-state colors — so switching
editions is a class swap on `<html>`:

```css
:root     { --canvas:#E9EEF2; --surface:#FFFFFF; --ink:#0F1B2A; --accent:#F97316; /* Blueprint */ }
html.dark { --canvas:#0A111E; --surface:#111C2E; --ink:#E7EEF7; --accent:#FB8A3C; /* Control Room */ }
```

Charts re-read the tokens and re-render on the swap; a `MutationObserver` on the `<html>` class
keeps icons and canvases in sync.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Foundry · Version 1.0 · The blueprint-technical, orchestration-and-observability member of the gallery.</sub>
</div>
