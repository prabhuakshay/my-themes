<div align="center">

# Dossier

### Every contract is a case file.

A serif-led enterprise design system for contract lifecycle management — porcelain surfaces,
hairline rules, a numbered case index, a double-ruled ledger register, and a five-state
contract-lifecycle status system. Burgundy for the brand, navy as a structural secondary. One app
shell that runs the full CLM console on desktop and reflows to a phone. Daylight + Lamplight editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/dossier/) · [**📖 Design Spec**](./dossier.md) · [**← All themes**](../../README.md)

![Status](https://img.shields.io/badge/version-1.0-7C2D3A)
![License](https://img.shields.io/badge/license-MIT-21201C)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-26364D)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-2F6B4F)

</div>

---

> Most contract software treats an agreement as a row in a database. **Dossier treats it as a case
> file** — a bound, indexed, authoritative record you open, read, annotate, and close. It is built
> for the people who manage the *lifecycle* of commercial agreements: counsel, contract managers,
> procurement, and the deal desk who live in renewals, obligations, and the clauses that allocate
> risk.

Set in a serif, organized by hairline rules, printed on porcelain — it looks like something you
would trust with a signature.

## The pole

This gallery's other serif system, **[Broadsheet](../broadsheet/)**, is a *newspaper front page*.
Dossier is a *legal case file* — same serif discipline, a completely different room:

| | Broadsheet | Frontline | **Dossier** |
| --- | --- | --- | --- |
| Metaphor | Newspaper front page | Field / ops app | **Legal case file** |
| Domain | Executive BI / reporting | Field service | **Contract lifecycle** |
| Structure | Editorial columns + headlines | Tactile cards | **Case index + ruled ledger** |
| Type | Fraunces / Archivo / Spline | Saira / Martian Mono | **Spectral + Roboto Mono** |
| Surface | Tinted newsprint | Hi-vis concrete | **Porcelain** |
| Accent | One claret | Safety orange | **Two — burgundy + navy** |
| Signature | Byline under every figure | Offline sync state | **Double-rule ledger + lifecycle status** |

## Seven principles

1. **The record is authoritative** — a serif voice, real punctuation, quiet confidence.
2. **Structure with rules, not boxes** — a numbered case index and a double-ruled ledger, not
   nested cards.
3. **Status is the spine** — five lifecycle states drive color; never decorative.
4. **Two accents, each with a job** — burgundy is brand/primary, navy is structural.
5. **Legible on porcelain** — warm stock, AA measured on the actual tint.
6. **Numbers are set, not shouted** — tabular mono for every figure and ID.
7. **Calm, deliberate motion** — one short eased beat, then out of the way.

## What the demo shows

A full contract-lifecycle app, responsive desktop ↔ mobile:

- **Overview (BI)** — KPI tiles + area, bar, and doughnut charts + a recently-active table.
- **Contracts** — the register/ledger: filter chips, search, sortable headers, an
  **inline-editable status cell**, and a right-hand **edit drawer**.
- **Renewals** — the notice calendar: per-contract **notice-period steppers**, **auto-renew
  toggles**, computed days-to-renewal, and a renewals-by-month chart.
- **Obligations** — post-signature duties with inline-editable owner and Met/Due/Overdue status.
- **Clauses** — a searchable clause library with a risk-tagged detail panel.
- **Settings** — the Daylight/Lamplight toggle, notification switches, and a **click-to-edit name**.
- Plus a centered **modal** (new contract), a **mobile nav drawer**, toasts, and the numbered
  case-index navigation.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/dossier

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize the window from desktop down to phone width to see the same system reflow. The demo loads
Tailwind (Play CDN), Spectral / Roboto Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including the five lifecycle status colors — so
switching editions is a class swap:

```css
:root     { --canvas:#F2F1EC; --surface:#FFFFFF; --ink:#21201C; --accent:#7C2D3A; --navy:#26364D; /* … Daylight */ }
html.dark { --canvas:#16130E; --surface:#1F1B15; --ink:#F0EBE0; --accent:#E29AA4; --navy:#9DB2D6; /* … Lamplight */ }
```

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Dossier · Version 1.0 · The case-file, contract-lifecycle member of the gallery.</sub>
</div>
