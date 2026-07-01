<div align="center">

# Prism

### Every channel gets a color. The color is the data.

A design system for marketing & campaign analytics — a warm bright-white surface, a magenta
primary, and a signature **five-hue channel spectrum** that flows through every chart, chip, dot,
and card. One editorial masthead app shell that's a full analytics console on desktop and a
thumb-driven app on a phone. Daylight + Nightshift editions.

[**▶ Live Demo**](https://prabhuakshay.github.io/my-themes/themes/prism/) · [**📖 Design Spec**](./prism.md) · [**← All themes**](../../README.md)

![Version](https://img.shields.io/badge/version-1.0-DB2777)
![License](https://img.shields.io/badge/license-MIT-1B1524)
![Responsive](https://img.shields.io/badge/responsive-desktop_%2B_mobile-2563EB)
![WCAG](https://img.shields.io/badge/WCAG_2.1-AA-16A34A)

</div>

---

> Most analytics UI treats color as decoration — a palette picked for mood, then sprinkled across
> charts at random. **Prism inverts that.** It splits the light into a fixed five-hue spectrum,
> binds one hue permanently to each marketing channel, and lets that spectrum carry meaning
> everywhere. See cyan, read *Paid Social* — before you read the label.

It's built for growth and performance marketers: campaign management, channel and audience
analytics, and the reporting that ties them together. Bright, editorial, numerate, and disciplined
about color.

## The fourth pole

This gallery's other themes are an instrument panel, a front page, and a field app —
**[Meridian](../meridian-enterprise/)**, **[Broadsheet](../broadsheet/)**, and
**[Frontline](../frontline/)**. Prism is the deliberate fourth pole: **marketing analytics**, with
an editorial *top-nav masthead* instead of a sidebar and a color system that *is* the information.

| | Meridian | Broadsheet | Frontline | **Prism** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **The spectrum** |
| Domain | Governance BI | Enterprise data | Field service | **Marketing / campaigns** |
| Shell | Sidebar | Sidebar | Sidebar | **Top-nav masthead** |
| Surface | Flat, boxed | Flat, ruled | Tactile | **Bright white, softly elevated** |
| Palette | Carbon gray | Newsprint | Hi-vis + orange | **White + magenta + 5-hue spectrum** |
| Type | IBM Plex | Fraunces/Archivo | Saira + Martian | **Bricolage Grotesque + Fragment Mono** |
| Signature | Governance | Provenance | Connectivity | **Channel identity as color** |

## Six principles

1. **The spectrum is the system** — five fixed hues, one per channel, reused everywhere.
2. **Two color languages, never crossed** — channel *identity* (spectrum) vs. campaign *state*
   (status), kept strictly separate.
3. **Editorial clarity** — a masthead, an oversized lead figure, one focal point per page.
4. **Bright, but never washed out** — AA on real surfaces; saturation reserved for small marks.
5. **Responsive, never mobile-only** — desktop console *and* phone app from one shell.
6. **Direct, immediate feedback** — optimistic edits, toasts, instant state changes.

## What the demo shows

A full marketing-analytics app, responsive desktop ↔ mobile, across six routed pages:

- **Overview (BI)** — an editorial hero (lead KPI + live trend), a 4-up KPI row, spend-by-channel
  bar, traffic doughnut, and a recent-campaigns table.
- **Campaigns** — a sortable data table with filter chips, search, an **inline-editable status
  select**, a **click-to-edit budget cell**, a right-hand **edit drawer**, a designed empty state,
  and a "New campaign" **modal**.
- **Channels** — five spectrum channel cards, a spend-share doughnut, a five-series per-channel CTR
  line chart, and a pacing table — all reading the fixed channel→hue spectrum.
- **Audiences** — segment cards, a reach bar chart, segment-health bars, and a segments table.
- **Reports** — a report builder (segmented control, selects, channel chips, toggle, textarea) plus
  a saved & scheduled reports table.
- **Settings** — the Daylight/Nightshift edition toggle, a **click-to-edit display name**, toggles,
  a budget stepper, a density segmented control, timezone select, and a textarea.
- Plus a **mobile nav drawer** (hamburger), toasts, status pills, and the persistent spectrum
  masthead.

## Quick start

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes/themes/prism

# Open the live demo — no build, no install
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Resize the window from desktop down to phone width to see the same system reflow. The demo loads
Tailwind (Play CDN), Bricolage Grotesque / Fragment Mono, Alpine, Lucide, and Chart.js from CDNs.

## Editions (theming)

Every value resolves to a CSS custom property — including the five spectrum hues — so switching
editions is a class swap on `<html>`, and the charts recolor because Chart.js reads the tokens on
each render:

```css
:root     { --canvas:#FBFAFC; --surface:#FFFFFF; --ink:#1B1524; --accent:#DB2777;
            --sp-1:#DB2777; --sp-2:#7C3AED; --sp-3:#2563EB; --sp-4:#0891B2; --sp-5:#E08600; }
html.dark { --canvas:#120E18; --surface:#1B1526; --ink:#F2ECF8; --accent:#F0559E;
            --sp-1:#F472B6; --sp-2:#A78BFA; --sp-3:#60A5FA; --sp-4:#22C3DD; --sp-5:#F5B547; }
```

## License

[MIT](../../LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>Prism · Version 1.0 · The marketing-analytics, spectrum-driven member of the gallery.</sub>
</div>
