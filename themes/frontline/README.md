<div align="center">

# Frontline

### Enterprise software for the people who don't sit at a desk.

A responsive design system for field & operations software — hi-vis daylight palette, a five-state
operational status system, tactile elevated surfaces, and offline-aware sync. One app shell that's
a full dispatch console on desktop and a thumb-driven app on a phone. Field + Shift editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/frontline/) · [**📖 Design Spec**](./frontline.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-FB5A1F)
![License](https://img.shields.io/badge/license-MIT-13171C)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-2563EB)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-16A34A)

</div>

---

> Most enterprise UI assumes a desk, a mouse, and a steady connection. **Frontline assumes one
> hand, a glove, direct sunlight, and a flaky signal.** It's built for the people who run
> operations in the world — field techs, drivers, inspectors, warehouse and utility crews — and
> for the dispatchers coordinating them from a screen.

The same tokens power a full operations console on a monitor and a glanceable, thumb-driven app on
a phone. High-contrast, tactile, status-driven, and built to keep working when the network doesn't.

## The third pole

This gallery's other themes — **[Meridian](../meridian-enterprise/)** and
**[Broadsheet](../broadsheet/)** — are both *flat, light, desktop-first*. Frontline is the
deliberate third pole:

| | Meridian | Broadsheet | **Frontline** |
| --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | **Field / ops app** |
| Device | Desktop | Desktop | **Phone *and* desktop** |
| Surface | Flat, boxed | Flat, ruled | **Tactile — elevated, rounded** |
| Palette | Carbon gray | Tinted newsprint | **Hi-vis + safety orange** |
| Type | IBM Plex | Fraunces/Archivo | **Saira + Martian Mono** |
| Signature concern | Governance | Provenance | **Connectivity / offline** |

## Seven principles

1. **Designed for the thumb, not the cursor** — reachable actions, ≥44px targets, no hover-only.
2. **Legible in daylight** — high-contrast, hi-vis, glanceable.
3. **Status is the system** — five operational states drive color; never decorative.
4. **Resilient to bad signal** — offline-aware, optimistic, sync state always visible.
5. **Responsive, never mobile-only** — desktop console *and* phone app from one system.
6. **Glanceable density** — the thing that matters now is biggest; detail on a tap.
7. **Tactile and immediate** — elevation signals tappable; feedback on every action.

## What the demo shows

A full field-operations app, responsive desktop ↔ mobile:

- **Operations dashboard (BI)** — KPI tiles + line, bar, and doughnut charts + a data table.
- **Work orders** — a data table with filter chips, search, an **inline-editable status cell**,
  and a right-hand **edit drawer**.
- **Dispatch** — a route timeline of the day's stops.
- **Capture** — a field data-entry form (reading stepper, selects, dynamic parts list, evidence).
- **Inventory** — van stock with +/- steppers and low-stock flags.
- **Settings** — Field/Shift edition toggle, offline mode, and a click-to-edit name (inline edit).
- Plus a centered **modal** (new work order), a **mobile nav drawer**, toasts, and a persistent
  sync/offline indicator.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/frontline

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize the window from desktop down to phone width to see the same system reflow. The demo loads
Tailwind (Play CDN), Saira / Martian Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including the five status colors — so switching
editions is a class swap:

```css
:root     { --bg:#EDF0F3; --surface:#FFFFFF; --ink:#13171C; --brand:#FB5A1F; /* … Field */ }
html.dark { --bg:#0A0D11; --surface:#161B21; --ink:#EAEEF2; --brand:#FF6A2E; /* … Shift */ }
```

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Frontline · Version 1.0 · The tactile, responsive, field-first member of the gallery.</sub>
</div>
