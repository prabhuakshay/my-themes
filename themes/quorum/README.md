<div align="center">

# Quorum

### The board's view, told as a story — a cover, a takeaway, and every metric measured against the promise.

A premium, narrative design system for **board reporting and investor relations** — a charcoal
board-pack binder, a champagne accent, an editorial serif cover, and guidance-vs-actual as the
organizing signal. One console that's a full board-review cockpit on a monitor and a glanceable app on
a phone. Boardroom + Ivory editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/quorum/) · [**📖 Design Spec**](./quorum.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-CBB681)
![License](https://img.shields.io/badge/license-MIT-14161C)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-7FA8DA)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-4FB783)

</div>

---

> Most enterprise UI is a wall of tiles. **Quorum is a board pack.** It is built for the people who
> assemble the read that goes into the room — the CFO, IR, FP&A — where the audience is the Board and
> the Street, where the organizing truth is not magnitude but **whether you kept the guidance you
> gave**, and where the hero surface is a **cover with a one-line takeaway**, not a dashboard.

The same tokens power a full board-review console on a monitor and a glanceable app on a phone.
Boardroom-first, narrative, guidance-driven, and legible read on a screen in a dim room *and* printed
on warm Ivory stock.

## The board-reporting pole

The gallery already has a *financial front page* (**[Broadsheet](../broadsheet/)**), a *field ops app*
(**[Frontline](../frontline/)**), and an *office-of-the-CFO ledger* (**[Sterling](../sterling/)**).
Quorum is the deliberate **board-reporting / investor-relations** pole — the outward-facing story, not
the internal books:

| | Broadsheet | Frontline | Sterling | **Quorum** |
| --- | --- | --- | --- | --- |
| Domain | Enterprise data (editorial) | Field / operations | Corporate finance / CFO | **Board reporting / IR** |
| Metaphor | Financial front page | Field app | The ledger / statement | **The board pack / letter** |
| Organizing system | Story hierarchy | Job status | Variance to plan | **Actual vs. guidance range** |
| Hero element | The front page | Work order | Financial statement | **The cover + bullet chart** |
| Palette | Newsprint + claret | Concrete + safety orange | Ink-navy + gilt | **Charcoal + champagne** |
| Type | Fraunces / Archivo | Saira / Martian | Hanken / JetBrains | **DM Serif / DM Sans / DM Mono** |

## Seven principles

1. **A board pack is a story** — a document with a narrative arc, not a card wall.
2. **Say the one thing first** — a large, editable, serif one-line takeaway on the cover.
3. **Measure against the promise** — actual vs. the guidance range, shown as a bullet chart.
4. **Boardroom-first, but print-ready** — Boardroom (dark) is the hero; Ivory (light) is the hand-out.
5. **Premium restraint** — type is the ornament, space is the luxury, one champagne accent.
6. **The binder holds the pages** — a constant charcoal chrome in both editions.
7. **Responsive, never mobile-only** — desktop console *and* phone app from one system.

## What the demo shows

A full board-and-IR console, responsive desktop ↔ mobile — **every nav item is a real page:**

- **Overview (BI)** — the board-pack cover with a **click-to-edit takeaway**, a headline KPI strip with
  vs-guidance sparklines, a revenue-&-margin bar+line chart, a revenue-mix doughnut, and a headline
  scorecard table with an **inline board-status select**.
- **Financials** — guidance-vs-actual **bullet charts** with editable talking points, plus a full
  guidance scorecard; clicking a row (or the pencil) opens the **edit drawer**.
- **Segments** — a segment doughnut, a geography bar, and a segment-detail table (growth, gross margin,
  momentum).
- **KPIs** — an operating scorecard (NRR, Rule of 40, magic number, net-new ARR…) with an efficiency
  **line/area trend** and a trailing-quarters table.
- **Narrative** — board talking points as click-to-edit cards with **filter chips**, search, and an
  inline status select.
- **Distribution** — a recipients table with a per-recipient **deliver toggle**, channel selects, and a
  segmented delivery cadence.
- **Settings** — a **click-to-edit company name**, a fiscal-period select, appearance toggles, and a
  rounding stepper.
- Plus a global **New board pack modal** (scrim, Esc, period/audience selects, copies stepper, tag
  chips, confidential toggle), a **mobile nav drawer**, toasts, and the Boardroom/Ivory edition toggle.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/quorum

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize from desktop down to phone width to see the same system reflow. The demo loads Tailwind (Play
CDN), DM Serif Display / DM Sans / DM Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including above/below-guidance — so switching editions
is a class swap on `<body>`. Quorum is **Boardroom-first**: it loads dark.

```css
:root, .light { --canvas:#EFEBE1; --surface:#FBF9F4; --ink:#22242C; --accent:#B79A55; /* Ivory */
                --chrome:#161821; --pos:#14713F; --neg:#B0442F; }
.dark          { --canvas:#14161C; --surface:#1B1E26; --ink:#E9ECF2; --accent:#CBB681; /* Boardroom */
                --chrome:#101218; --pos:#4FB783; --neg:#E07A6A; }
```

The charcoal chrome is a constant in both editions, and above/below-guidance colors are tokens too, so
a bullet band, a status chip, a chart series, and a KPI delta all read the same source — and Ivory is a
single `body.light`.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Quorum · Version 1.0 · The board-reporting, investor-relations, story-led member of the gallery.</sub>
</div>
