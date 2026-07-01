<div align="center">

# Voltaic

### The control gauge — every reading at a glance, every alarm in its place.

A dark-forward, control-room design system for grid & energy monitoring — charcoal SCADA chrome,
electric-lime accents, radial load gauges, and a five-level alarm-severity system. One console
that's a full dispatch board on a monitor and a thumb-driven app on a phone. Control Room + Day
Board editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/voltaic/) · [**📖 Design Spec**](./voltaic.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-A3E635)
![License](https://img.shields.io/badge/license-MIT-14181D)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-38BDF8)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-4ADE80)

</div>

---

> Most enterprise UI is a form on a white page. **Voltaic is an instrument.** It is built for the
> people who watch the grid — dispatch operators, substation engineers, energy-network control
> desks — where a number is never just a number but a *reading against a limit*, and a colour on
> screen means a breaker is about to trip.

The same tokens power a full monitoring console on a monitor and a glanceable app on a phone.
Dark-forward, gauge-first, severity-driven, and legible in a dim 24/7 control room *and* in
daylight.

## The fourth pole

The gallery's other themes — **[Meridian](../meridian-enterprise/)**, **[Broadsheet](../broadsheet/)**,
and **[Frontline](../frontline/)** — are all *light-forward*. Voltaic is the deliberate **dark,
monitoring** pole:

| | Meridian | Broadsheet | Frontline | **Voltaic** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **The control gauge** |
| Default edition | Light | Light | Field (light) | **Control Room (dark)** |
| Organizing system | Density | Editorial hierarchy | Operational status | **Alarm severity** |
| Hero element | Data grid | Headline | Status + glance | **Radial load gauges** |
| Palette | Carbon gray | Tinted newsprint | Hi-vis + orange | **Charcoal + electric lime** |
| Type | IBM Plex | Fraunces/Archivo | Saira/Martian | **Red Hat Display/Mono** |
| Domain | Enterprise BI | Financial editorial | Field service | **Grid & energy** |

## Seven principles

1. **The gauge is the interface** — show a value against its limit, not just the digit.
2. **Dark-forward, built for the desk** — Control Room is the hero; Day Board a first-class alternate.
3. **Severity is the system** — five levels drive every colour; never decorative.
4. **Calm until it matters** — a nominal grid is quiet; attention is earned by severity.
5. **Instrument-grade legibility** — monospaced, tabular readings that never jitter.
6. **Responsive, never mobile-only** — desktop console *and* phone app from one system.
7. **Live and honest** — reads as live, never fakes it; offline is offline.

## What the demo shows

A full grid-control console, responsive desktop ↔ mobile:

- **Dashboard (BI)** — a KPI strip, a **radial gauge cluster** (load, frequency, renewable mix,
  reserve margin), an alarm banner, area + doughnut + bar charts, and a substation table.
- **Substations** — a data table with severity filter chips, search, **click-to-sort** headers, an
  **inline-editable condition select**, an **inline-editable setpoint**, and a right-hand **edit drawer**.
- **Alarms** — an active alarm queue with acknowledge actions, an alarm-rules table with toggles,
  and a centered **"New alarm rule" modal**.
- **Assets** — a plant register with +/- **steppers** for transformer tap position and severity cells.
- **Settings** — Control Room / Day Board edition toggle, preference switches, a segmented
  escalation floor, a shift-notes textarea, and a **click-to-edit operator name** (inline edit).
- Plus a **mobile nav drawer**, toasts, and a live SCADA-link / frequency / clock cluster.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/voltaic

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize the window from desktop down to phone width to see the same system reflow. The demo loads
Tailwind (Play CDN), Red Hat Display / Red Hat Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including the five severity colours — so switching
editions is a class swap. Voltaic is **dark-forward**: the page loads in Control Room.

```css
html.dark, :root { --canvas:#0C0F13; --surface:#14181D; --ink:#E7ECEF; --accent:#A3E635; /* Control Room */ }
html.light       { --canvas:#F7F9FA; --surface:#FFFFFF; --ink:#14181D; --accent:#84CC16;
                   --accent-ink:#4D7C0F; --chrome:#14181D; /* Day Board */ }
```

Severity colours are tokens too (`--sev-normal … --sev-offline`), so a tag, a table cell, a gauge
chip, and an alarm banner all read the same source.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Voltaic · Version 1.0 · The dark, control-room, severity-driven member of the gallery.</sub>
</div>
