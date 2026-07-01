<div align="center">

# Vellum

### The record is the hero.

A premium design system for BI apps built around **data entry** — where entering a record is a
first-class craft and reading it back is a pleasure. Warm porcelain paper, deep iris ink, tabular
figures, a legible records pipeline, and one restrained jewel accent. A calm, expensive ledger,
wired to real BI. Single light edition, by design.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/vellum/) · [**📖 Design Spec**](./vellum.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-4B45C7)
![License](https://img.shields.io/badge/license-MIT-211E1A)
![Mode](https://img.shields.io/badge/mode-light-F1EFEA)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-1E8A5A)

</div>

---

> Most "data apps" treat entry as a chore bolted onto a dashboard — a cramped modal, a wall of gray
> inputs, a Save button you *hope* worked. **Vellum inverts that.** Entering data is the primary
> craft; reading it back as BI is the reward — both built from one type scale, one palette, one
> status system.

The result feels like a well-kept ledger: iris ink on fine paper, generous whitespace, every figure
typeset. Premium through restraint, not decoration.

## The fourth pole

This gallery's other themes — **[Meridian](../meridian-enterprise/)**,
**[Broadsheet](../broadsheet/)**, and **[Frontline](../frontline/)** — are an instrument panel, a
front page, and a field app. Vellum is the deliberate fourth pole: **premium, quiet, and
entry-first.**

| | Meridian | Broadsheet | Frontline | **Vellum** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **Records studio** |
| Device | Desktop | Desktop | Phone *and* desktop | **Desktop-first, responsive** |
| Surface | Flat, boxed | Flat, ruled | Tactile, elevated | **Soft sheets, hairline dividers** |
| Palette | Carbon gray | Tinted newsprint | Hi-vis + orange | **Warm porcelain + iris ink** |
| Type | IBM Plex | Fraunces/Archivo | Saira + Martian | **Hanken Grotesk + JetBrains Mono** |
| Signature concern | Governance | Provenance | Connectivity | **Data-entry ergonomics + restraint** |

## Seven principles

1. **The record is the hero** — entry is a full page with a live summary, not a cramped modal.
2. **Premium is what you leave out** — whitespace, hairlines, one jewel accent; no chartjunk.
3. **A pipeline you can read** — Draft → In review → Approved → Posted (+ Flagged), always color + label.
4. **Numbers are typeset** — tabular monospace money, right-aligned, decimals aligned.
5. **Enter, then read** — excellent data entry *and* excellent BI on the same tokens.
6. **Calm, not clinical** — warm paper and iris ink; premium and human, never a cold gray grid.
7. **Light by design, token by construction** — one deliberate light edition, fully themeable.

## What the demo shows

A full spend-&-records app, responsive desktop ↔ mobile:

- **Overview (BI)** — KPI tiles with sparklines + a spend area chart, a status doughnut, a category
  bar, and a top-vendors table.
- **New Entry (the star)** — a full **entry sheet**: vendor search, selects, department chips, a big
  stepped **amount** field with quick-add, **split allocation** with live reconciliation, memo,
  toggles, and tags — beside a live **summary rail** and receipt dropzone.
- **Records** — a data table with filter chips, search, an **inline-editable amount** cell and an
  **inline status select**, a right-hand **edit drawer**, and an empty state.
- **Review** — an approval queue with inline **Approve / Flag** and an "All caught up" empty state.
- **Analytics** — budget-vs-actual, spend by department, spend by method, and a live budget-utilization table.
- **Settings** — inline click-to-edit name, a real **density** toggle, defaults, and preferences.
- Plus a **quick-capture modal**, a **mobile nav drawer**, toasts, and a persistent iris keyline.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/vellum

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize the window from desktop down to phone width to watch the same system reflow — the entry
sheet's summary rail drops below the sheet, the sidebar becomes a drawer. The demo loads Tailwind
(Play CDN), Hanken Grotesk / JetBrains Mono, Alpine, Lucide, and Chart.js from CDNs.

## Theming

Every value resolves to a CSS custom property — including the five pipeline colors — so a theme
change is a single edit at the source, never a component rewrite:

```css
:root{
  --canvas:#F1EFEA; --surface:#FFFFFF; --ink:#211E1A; --accent:#4B45C7;
  --line:#E7E3DA; --line-2:#D6D0C4;
  --s-draft:#8A8579; --s-review:#3A6DD6; --s-approved:#1E8A5A;
  --s-posted:#4B45C7; --s-flagged:#C63A45; /* … */
}
```

Vellum ships a single light edition by design; because it's all tokens, adding another edition is a
second selector, not a refactor.

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Vellum · Version 1.0 · The premium, entry-first, single-light member of the gallery.</sub>
</div>
