<div align="center">

# Broadsheet

### Enterprise data, set like the financial press.

An editorial design system for enterprise data apps — tinted newsprint stock, high-contrast
serif headlines, a single claret accent, hairline rules instead of boxes, and every figure
carrying a byline. Day + Evening editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/broadsheet/) · [**📖 Design Spec**](./broadsheet.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-94252B)
![License](https://img.shields.io/badge/license-MIT-1C1813)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-2C6A4E)
![Build](https://img.shields.io/badge/build-zero--build-8E8573)

</div>

---

> A *broadsheet* is the large-format quality newspaper — the front page where the day's most
> consequential numbers are reported with authority and a point of view. Broadsheet treats an
> enterprise dashboard the same way: **a dashboard is a front page, a metric is a headline, and
> every figure carries a byline** that says where it came from and how far to trust it.

Broadsheet borrows a century of craft from the financial press — the FT, The Economist, Bloomberg
Businessweek — and ports it to software: editorial hierarchy over equal tiles, rules and column
gutters over boxes, a three-typeface system, and provenance treated as a first-class citizen.

## The opposite of Meridian, on purpose

This gallery's other theme, **[Meridian Enterprise](../meridian-enterprise/)**, is a Carbon-grade
*instrument panel*. Broadsheet is its deliberate inverse for the same enterprise user:

| | Meridian | **Broadsheet** |
| --- | --- | --- |
| Metaphor | Instrument panel | Front page |
| Type | IBM Plex Sans + Mono | Fraunces + Archivo + Spline Sans Mono |
| Structure | Boxed 2px grid | Hairline **rules** + columns |
| Surface | Neutral white / Gray-100 | **Tinted newsprint** stock |
| Accent | Carbon blue | **Claret** |
| Density | Maximal | Hierarchy-by-whitespace |
| Provenance | Status chip | **Byline** + footnotes |

Use Meridian for ops consoles; use Broadsheet for executive analytics, BI, and financial reporting.

## Seven principles

1. **The number is the headline** — the most consequential figure leads, set largest in the display serif.
2. **Every figure has a byline** — source, freshness, and confidence travel with the number.
3. **Structure with rules, not boxes** — hairline rules, column gutters, and whitespace organize the page.
4. **Type does the work** — hierarchy comes from a three-typeface system, not from color.
5. **One accent, spent with intent** — a single claret; green/claret-red only for data direction.
6. **Print-grade legibility on tinted stock** — AA verified on the actual tint, both editions.
7. **Calm under deadline** — motion is restrained; print doesn't animate.

## At a glance

- **Type** — Fraunces (display serif) for headlines & figures, Archivo (grotesque) for UI, Spline Sans Mono for tabular figures, kickers & bylines.
- **Color** — warm newsprint neutrals + one claret accent; semantic ledger-green / claret-red, signed and marked (▲/▼), never color-only.
- **Patterns** — lead figure, byline line, ticker, the ledger "Listings" table, pull-figure, drop cap, footnotes, double-rule masthead.
- **Editions** — Day (tinted light) and Evening (warm deep-ink dark), a single class swap on `<html>`.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/broadsheet

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

The demo pulls Tailwind (Play CDN), Fraunces / Archivo / Spline Sans Mono, Alpine, Lucide, and
Chart.js from CDNs, so an internet connection is needed on first open. The spec is plain Markdown.

## Editions (theming)

Every visual decision resolves to a CSS custom property; switching editions is a class swap:

```css
:root     { --paper:#F2EBDC; --ink:#1C1813; --accent:#94252B; /* … Day */ }
html.dark { --paper:#13100B; --ink:#EFE6D4; --accent:#D76A6E; /* … Evening */ }
```

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Broadsheet · Version 1.0 · The editorial counterpart to Meridian Enterprise.</sub>
</div>
