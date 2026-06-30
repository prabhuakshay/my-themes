<div align="center">

# Meridian Enterprise

### Calm, governance-grade software for people who run the business.

A Carbon-grade B2B design system — disciplined tokens, sharp 1px borders, a strict 2px grid,
and motion that informs rather than entertains. Light + Dark (Gray-90 / Gray-100).

[**▶ Live Demo**](https://prabhuakshay.github.io/meridian-enterprise/) · [**📖 Design Spec**](./meridian-enterprise.md)

![Status](https://img.shields.io/badge/version-1.0-161616)
![License](https://img.shields.io/badge/license-MIT-0f62fe)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-24a148)
![Dependencies](https://img.shields.io/badge/build-zero--build-525252)

</div>

---

> A *meridian* is the line a navigator uses to fix position with confidence. In dense,
> high-stakes enterprise software, the interface should be that fixed reference — so an operator
> always knows **where they are, what is true right now, and what to do next.**

Meridian is not a marketing aesthetic bolted onto an app. It is a **productive, data-first
system** in the lineage of IBM Carbon: every value resolves to a named token, every component
earns its density, and accessibility is built in from the first frame — not bolted on by audit.

## What's inside

| File | What it is |
| --- | --- |
| [`meridian-enterprise.md`](./meridian-enterprise.md) | The full **design specification** — 23 sections, ~950 lines, covering tokens, components, accessibility, and governance. |
| [`index.html`](./index.html) | A **self-contained live demo** — open it in any browser, no build step. Light/dark themes, real components, charts, and tables. |

## Seven principles

1. **Clarity over decoration** — every pixel earns its place by communicating state, hierarchy, or affordance.
2. **Truth is immediate** — current system state is always visible without a click.
3. **Dense, but disciplined** — high information density, earned through a strict 2px grid.
4. **Sharp & precise** — small radii (2–4px), crisp 1px borders, hairline gridlines.
5. **Tokens, not decisions** — no raw hex or magic margins; everything resolves to a named token.
6. **Accessible by default** — WCAG 2.1 AA is the floor, designed in, not audited in.
7. **Productive motion** — motion explains causality, in short standard-eased durations (70–240ms).

## At a glance

- **Color** — IBM Carbon gray ramp + functional blue / red / green / yellow, with role tokens (`--text-secondary`, `--layer-01`, `--interactive`) that swap cleanly between light and dark.
- **Typography** — IBM Plex Sans for UI, IBM Plex Mono for data and code.
- **Grid** — a strict 2px spacing scale and ruthless typographic hierarchy.
- **Components** — navigation, data tables, KPIs, overlays, toasts, and full interactive-state matrices.
- **Foundations** — folds Nielsen's heuristics and the classic interaction laws into one builder-ready document.

## Quick start

```bash
git clone https://github.com/prabhuakshay/meridian-enterprise.git
cd meridian-enterprise

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

The demo loads its dependencies (Tailwind Play CDN, IBM Plex, Alpine, Lucide, Chart.js) from
CDNs, so an internet connection is needed on first open. The design spec is plain Markdown —
read it [on GitHub](./meridian-enterprise.md) or in any editor.

## Theming

Every visual decision resolves to a CSS custom property. Switching themes — or rebranding the
whole system — is a token swap, never a refactor:

```css
:root, .theme-white { --bg:#ffffff; --layer-01:#f4f4f4; --interactive:#0f62fe; /* … */ }
.theme-g100         { --bg:#161616; --layer-01:#262626; --interactive:#4589ff; /* … */ }
```

## License

[MIT](./LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Meridian Enterprise · Version 1.0 · Built to look engineered, not soft.</sub>
</div>
