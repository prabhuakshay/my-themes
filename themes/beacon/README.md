<div align="center">

# Beacon

### A calm signal in the queue.

A design system for customer-support & helpdesk software — soft-lilac surfaces, a friendly violet
accent, a two-part **signal system** (priority + status), and CSAT/SLA as first-class metrics. One
app shell that's a full support console on desktop and a thumb-driven app on a phone. Daylight +
Nightwatch editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/beacon/) · [**📖 Design Spec**](./beacon.md) · [**← All themes**](../../README.md)

![Version](https://img.shields.io/badge/version-1.0-6D5CE7)
![License](https://img.shields.io/badge/license-MIT-1C1A2E)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-8574F0)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-17B26A)

</div>

---

> A support queue is a stressful place — the clock is running, the customer is already frustrated,
> and the agent is juggling a dozen conversations. Most helpdesk UIs answer that with *more* red,
> more badges, more noise. **Beacon answers it with calm.**

Soft-lilac, rounded, and human-first: the ticket about to breach, the unhappy customer, the next
reply owed — the thing that matters *now* is the clearest thing on screen, and everything else stays
quiet. Beacon treats support as a human craft, not a ticket factory: real names, real faces, CSAT,
and a warm, plain voice.

## The pole

This gallery's other themes are operational in tone — **[Meridian](../meridian-enterprise/)** (a
flat instrument panel) and **[Broadsheet](../broadsheet/)** (a flat editorial front page) are
desk-bound and neutral; **[Frontline](../frontline/)** is rugged and hi-vis for the field. Beacon is
the deliberate **calm, human, service** pole:

| | Meridian | Broadsheet | Frontline | **Beacon** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **Support console** |
| Tone | Precise, neutral | Authoritative | Rugged, operational | **Calm, warm, human** |
| Surface | Flat, boxed | Flat, ruled | Tactile, hi-vis | **Soft lilac, rounded** |
| Palette | Carbon gray | Tinted newsprint | Concrete + orange | **Lilac + violet + SLA amber** |
| Type | IBM Plex | Fraunces/Archivo | Saira + Martian Mono | **Manrope + DM Mono** |
| Signature concern | Governance | Provenance | Connectivity / offline | **CSAT, SLA & tone of voice** |

## Seven principles

1. **Calm over loud** — energy spent reducing noise; one focal point; colour only for meaning.
2. **Status is a shared language** — priority + status, colour + label + dot, identical everywhere.
3. **The human is the product** — names, faces, CSAT; a warm voice, not case numbers.
4. **Glance, then act** — what matters now is biggest; the controls to act on it are inline.
5. **Two editions, one system** — token-driven Daylight (day shift) and Nightwatch (night desk).
6. **Responsive, never mobile-only** — a desktop console *and* a phone app from one system.
7. **Accessible calm** — AA on tinted lilac in both editions; never colour-only; visible focus.

## What the demo shows

A full support console, responsive desktop ↔ mobile:

- **Overview (BI dashboard)** — KPI tiles + line/area, bar, and doughnut charts + an SLA gauge, an
  agent-load panel, and a recent-activity data table.
- **Tickets** — a sortable data table with filter chips, search, a timeframe segmented control, and
  **two inline-editable cells** (priority *and* status `<select>`s), each row opening a right-hand
  **edit drawer** (draft Save/Cancel).
- **Customers** — accounts with plan, open count, CSAT, and a health signal chip; an inline-editable
  plan cell and search.
- **Reports** — CSAT trend, satisfaction mix, resolution-time-by-team charts, and an agent
  leaderboard.
- **Settings** — the full input range (text, email, selects, textarea, **toggles**, **segmented
  control**, **steppers**, **filter chips**), a **click-to-edit** display name (inline edit), and
  the Daylight/Nightwatch edition switch.
- Plus a centred **New-ticket modal** (adds a row + toast), a **mobile nav drawer**, and semantic
  toasts for every action.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/beacon

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize the window from desktop down to phone width to watch the same system reflow. The demo loads
Tailwind (Play CDN), Manrope / DM Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including the priority and status colours, which
ship as **paired fill/ink tokens** so chips stay AA in both editions — so switching editions is a
class swap on `<html>`:

```css
:root     { --canvas:#F6F6FB; --surface:#FFFFFF; --ink:#1C1A2E; --accent:#6D5CE7; /* … Daylight */ }
html.dark { --canvas:#0E0D18; --surface:#1A1826; --ink:#ECEAF6; --accent:#8B7BF0; /* … Nightwatch */ }
```

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Beacon · Version 1.0 · The calm, human, support-desk member of the gallery.</sub>
</div>
