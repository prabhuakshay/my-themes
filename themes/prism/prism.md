# Prism — Theme Design Specification

> **Version 1.0** · A design system for marketing & campaign analytics · Daylight + Nightshift editions
> Tagline: **"Every channel gets a color. The color is the data."**

Most analytics UI treats color as decoration — a palette picked for mood, then sprinkled across
charts at random. **Prism inverts that.** It starts from a single disciplined idea: split the light
into a fixed **five-hue spectrum**, assign one hue permanently to each marketing channel, and let
that spectrum flow through every chart, chip, dot, and card in the product. When a marketer sees
cyan, they read *Paid Social* before they read the label. The system is a marketing command center
for growth and performance teams — bright, confident, editorial — where the through-line from a
doughnut slice to a table row to a KPI tile is a color you can trust.

> **A distinct pole.** This repository already ships **Meridian** (a flat Carbon instrument panel),
> **Broadsheet** (a flat editorial front page), and **Frontline** (a tactile, field-first ops app).
> Prism is the **marketing-analytics pole**: an editorial *top-nav masthead* rather than a sidebar,
> a warm bright-white surface with a **magenta** primary, the **Bricolage Grotesque** display voice,
> and a signature five-hue channel spectrum no other theme uses. §2 maps the contrast.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Prism vs. the others](#2-prism-vs-the-others)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [The Five-Hue Channel Spectrum](#5-the-five-hue-channel-spectrum)
6. [The Campaign Status System](#6-the-campaign-status-system)
7. [Typography](#7-typography)
8. [Responsive Layout](#8-responsive-layout)
9. [Elevation, Radius & Surfaces](#9-elevation-radius--surfaces)
10. [Components & Patterns](#10-components--patterns)
11. [Motion](#11-motion)
12. [Accessibility](#12-accessibility)
13. [Tokens in Practice](#13-tokens-in-practice)
14. [Anti-Patterns Prism Forbids](#14-anti-patterns-prism-forbids)
15. [Pre-Ship Checklist](#15-pre-ship-checklist)

---

## 1. Design Principles

Six principles. When two conflict, the **earlier** wins.

### P1 — The spectrum is the system
Color is not decoration; it is identity. A fixed set of **five hues** maps one-to-one to the five
marketing channels (§5) and is reused *identically* in every chart series, channel dot, progress
bar, and card accent. A marketer learns the spectrum once and reads it everywhere. Hues are never
spent on mood or on making a chart "pop."

### P2 — Two color languages, never crossed
Prism runs **two** disciplined color vocabularies and keeps them strictly separate: the **channel
spectrum** (identity — who the traffic is) and the **campaign status system** (state — what the
campaign is doing). Channel = a colored dot or chart hue; status = a tinted pill with a label.
Blurring the two would make the interface lie.

### P3 — Editorial clarity
Prism reads like a well-set magazine, not a control panel. A confident masthead, an oversized lead
figure, generous whitespace, and a hairline spectrum rule give each page one obvious focal point.
The display type carries personality; everything around it stays quiet.

### P4 — Bright, but never washed out
The default edition is a warm near-white built for a lit office and a projector in a pitch. Text,
magenta, and all five hues clear WCAG AA on their real surfaces. Saturation is reserved for small
marks (dots, slices, bars); large fills stay calm so the data doesn't vibrate.

### P5 — Responsive, never mobile-only
One masthead app shell, two shapes. On desktop it is a full analytics console — a horizontal nav
masthead, a multi-column BI grid, dense tables. On a phone the masthead collapses to a hamburger
**nav drawer**, the grid stacks to one column, and every target stays ≥ 44px. A phone mock floating
in a desktop window is a failure, not a feature.

### P6 — Direct, immediate feedback
Every action answers instantly: a toast, a status change, an inline commit. Edits are optimistic —
a budget you type is live the moment you press Enter. The interface never makes a marketer wonder
whether the click landed.

---

## 2. Prism vs. the others

| Axis | Meridian | Broadsheet | Frontline | **Prism** |
| --- | --- | --- | --- | --- |
| Metaphor | Instrument panel | Front page | Field / ops app | **The spectrum** |
| Domain | Governance BI | Enterprise data | Field service | **Marketing / campaigns** |
| Shell | Sidebar | Sidebar | Sidebar | **Editorial top-nav masthead** |
| Surface | Flat, boxed | Flat, ruled | Tactile, elevated | **Bright white, softly elevated** |
| Palette | Carbon gray | Tinted newsprint | Hi-vis + orange | **White + magenta + 5-hue spectrum** |
| Type | IBM Plex | Fraunces/Archivo | Saira + Martian | **Bricolage Grotesque + Fragment Mono** |
| Accent | Carbon blue | Claret | Safety orange | **Magenta `#DB2777`** |
| Organizing idea | Density | Editorial hierarchy | Operational status | **Channel identity as color** |
| Signature | Governance | Provenance | Connectivity | **The five-hue spectrum** |
| Editions | White / Gray | Day / Evening | Field / Shift | **Daylight / Nightshift** |

Use Prism for marketing dashboards, campaign management, channel and audience analytics, growth
reporting, and any product where the *channel mix* is the story.

---

## 3. Brand & Voice

Prism sounds like a sharp growth marketer briefing a stakeholder: **confident, concrete, and
numerate.** Plain marketing nouns ("campaign", "channel", "audience", "ROAS"), active verbs on
controls ("Create campaign", "Generate", "Save changes"), and figures stated without hedging
("$92k spend", "+12.6%"). No hype, no exclamation marks, no "supercharge your funnel." The brand
mark is the spectrum itself — a conic-gradient prism block that fans magenta → violet → blue →
cyan → amber — paired with the Bricolage Grotesque wordmark and a hairline spectrum rule that caps
every masthead and modal.

---

## 4. Color System

Two editions, one token set. **Daylight** (light) is a warm near-white for lit rooms and pitches;
**Nightshift** (dark) is a deep plum-ink for late reporting and low-light review. Every value is a
role token, so the edition swap is a single class on `<html>`.

### Daylight edition (light)

| Role | Token | Value |
| --- | --- | --- |
| App canvas | `--canvas` | `#FBFAFC` |
| Surface (cards, chrome) | `--surface` | `#FFFFFF` |
| Inset surface | `--surface-2` | `#F7F5FA` |
| Primary text | `--ink` | `#1B1524` |
| Secondary text | `--ink-2` | `#5B5268` |
| Caption | `--ink-3` | `#948BA3` |
| Hairline (cards) | `--line` | `#ECE8F0` |
| Structural separator (chrome) | `--line-2` | `#DAD3E2` |
| Brand (magenta) | `--accent` | `#DB2777` |
| Brand text-safe | `--accent-ink` | `#BE1B63` |
| Brand tint (active surfaces) | `--accent-soft` | `#FBE3F0` |

### Nightshift edition (dark)

Deep plum-ink, not pure black: `--canvas #120E18`, `--surface #1B1526`, `--surface-2 #241C32`,
`--ink #F2ECF8`, hairlines `#2E2740` / separators `#3E3452`. Magenta brightens to `--accent #F0559E`
(text-safe `--accent-ink #F98AC1`, tint `--accent-soft #37172A`) so the brand stays punchy on dark.

**Rules of use.** Magenta is the brand and the single primary action — used decisively on the "New
campaign" button, active nav underline, focus ring, and toast icon, but never sprayed as a
highlighter. A **dedicated structural separator** (`--line-2`, a touch stronger than the card
hairline `--line`) draws the app chrome — the masthead's lower edge, drawer and modal edges — so
the layout reads clearly; card borders stay on the lighter `--line`. The channel spectrum (§5) and
the status system (§6) own all other color and are never borrowed for decoration.

## 5. The Five-Hue Channel Spectrum

The signature of the theme. Light is split into **five fixed hues**, and each hue is bound
permanently to one marketing channel. The mapping never changes — not per chart, not per page.

| Channel | Token | Daylight | Nightshift | Reads as |
| --- | --- | --- | --- | --- |
| Search | `--sp-1` | `#DB2777` | `#F472B6` | magenta |
| Display | `--sp-2` | `#7C3AED` | `#A78BFA` | violet |
| Video | `--sp-3` | `#2563EB` | `#60A5FA` | blue |
| Paid Social | `--sp-4` | `#0891B2` | `#22C3DD` | cyan |
| Email | `--sp-5` | `#E08600` | `#F5B547` | amber |

- The order **magenta → violet → blue → cyan → amber** is a genuine spectral sweep; the masthead
  and modal `spectrum-rule` render it as a 4px gradient, and the brand mark fans it as a conic
  gradient.
- The five hues drive **every** chart series (the channel bar, the spend-share and traffic
  doughnuts, the per-channel CTR multi-line), every **channel dot** in tables and cards, every
  channel **progress bar**, and each channel card's top accent.
- Hues are used as **graphic marks**, not as body text. Where a channel is labelled in text, the
  label uses `--ink-2` next to a colored dot — so the amber channel never becomes low-contrast
  amber text. As chart fills and 7–12px marks, all five clear the 3:1 graphic-contrast bar in both
  editions; in Nightshift each hue lightens in step to stay legible on the plum surface.

## 6. The Campaign Status System

A **separate** vocabulary from the spectrum — this reports *state*, not identity. Five campaign
states, each a fixed pair of **color + label**, rendered as a tinted pill (and as the inline status
`<select>` in the campaigns table).

| State | Dot color | Meaning |
| --- | --- | --- |
| Draft | `#8B8398` (slate) | Built, not launched |
| Scheduled | `#4F46E5` (indigo) | Queued to go live |
| Live | `#16A34A` (green) | Running now |
| Paused | `#C2740B` (amber-brown) | Temporarily stopped |
| Ended | `#9A93A6` (muted) | Complete |

Status is **never carried by color alone** — the label always travels with the pill, and the dot is
a redundant cue. Each state resolves to a tinted background + darker foreground pair, defined per
edition so the pill keeps AA text contrast in both Daylight and Nightshift. Critically, the status
palette (slate / indigo / green / amber-brown / muted) is chosen to stay **visually distinct** from
the channel spectrum so the two languages never collide in a marketer's eye.

## 7. Typography

Two typefaces, chosen for an editorial, confident, numerate voice.

| Role | Typeface | Used for |
| --- | --- | --- |
| Display / UI | **Bricolage Grotesque** | Headings, wordmark, labels, buttons, body — a characterful grotesque with an optical-size axis that stays warm at display sizes and crisp at 14px |
| Figures / codes | **Fragment Mono** | KPI deltas, table numbers, budgets, CTR, timestamps, small-caps table headers |

- Bricolage Grotesque is the personality of the system — its slightly irregular, contemporary
  cut reads as a modern marketing brand, not a neutral dashboard. It's used with restraint: heavy
  weights (700–800) only on lead figures and page titles.
- **Fragment Mono** gives tabular alignment and an analytical feel to every figure; the tiny
  uppercase mono table headers are a signature detail.
- Hierarchy is by size and weight: an oversized editorial lead figure (`clamp(52–88px)`), page
  titles at 24px/800, section headings at 16–18px/700, a sturdy 14px body, and 11–12px mono
  captions. Numbers use tabular figures (`tnum`) everywhere so columns align.

## 8. Responsive Layout

One masthead app shell, two shapes — driven by breakpoints, not a separate build.

- **Desktop (≥ 1024px):** a sticky **top-nav masthead** (wordmark + brand prism, horizontal nav
  with an active magenta underline, search, edition toggle, notifications, primary action, avatar)
  over a fluid `max-w-[1400px]` content column. The dashboard is a multi-column BI grid: an
  editorial hero, a 4-up KPI row, an asymmetric 2/1 chart row, and full-width tables.
- **Tablet (≥ 640px):** KPI and chart grids relax to two columns; tables keep priority columns and
  scroll horizontally; the masthead nav persists.
- **Phone (< 1024px):** the masthead nav becomes a **left nav drawer** behind a hamburger; content
  stacks to one column; the search moves into the page; primary actions stay reachable; tables
  scroll within their card. Targets ≥ 44px.

The same tokens, components, spectrum, and status system render in both — only the arrangement
changes.

## 9. Elevation, Radius & Surfaces

Prism is **bright and softly elevated** — depth is gentle, used to lift cards a hair off the canvas
and to float overlays clearly above the page.

- **Three shadow levels:** `--shadow-sm` for resting cards, `--shadow-md` for hover/raised, and
  `--shadow-lg` for overlays (drawer, modal, toasts) that lift decisively. Shadows are soft,
  low-opacity, and single-source; in Nightshift they deepen rather than invert.
- **Radius:** `--radius` 14px for cards and surfaces, `--radius-sm` 10px for controls and buttons,
  `--radius-xs` 8px for chart bars, and pill (999px) for chips, toggles, and status pills.
- **Surfaces:** three levels — `--canvas` (page) → `--surface` (cards & chrome) → `--surface-2`
  (fields, steppers, insets). The 4px `spectrum-rule` caps cards-as-mastheads (the hero, the modal)
  as the theme's signature edge.

## 10. Components & Patterns

- **Editorial hero** — an oversized lead KPI figure + delta chip beside a live trend chart; the
  dashboard's focal point.
- **KPI tile** — tinted channel-hued icon, figure in heavy Bricolage, mono delta chip.
- **Charts** — line/area (conversions vs spend), bar (spend by channel), doughnut (channel & traffic
  mix), and a five-series multi-line (per-channel CTR). All read the spectrum from CSS tokens and
  **re-render on edition swap and tab activation**, with hidden canvases guarded (`offsetParent`).
- **Data table** — small-caps mono headers with a sortable caret, zebra rows, magenta-tint hover,
  channel dots, right-aligned mono figures, an **inline-editable status `<select>`**, and a
  **click-to-edit budget cell** (numeric, commit on Enter/blur) that updates the row optimistically.
- **Edit drawer (right)** — open a campaign, edit name / channel / budget / CTR / status / notes on
  a cloned form, Save (commit + toast) or Cancel (discard). Esc and scrim also close it.
- **Nav drawer (left)** — the mobile navigation surface behind the hamburger, with the edition
  toggle in its footer.
- **Modal** — a centered "New campaign" dialog capped by the spectrum rule, with scrim,
  Esc-to-close, a create action that prepends the row and toasts, and a mobile bottom-sheet reflow.
- **Inputs** — text, search, `<select>`, textarea, toggle switch, segmented control, stepper (+/−),
  filter chips, and numeric/inline-editable fields — all ≥ 44px with a visible magenta focus ring.
- **Status pill / channel dot**, **toast** (action feedback, top-stacked, auto-dismiss), and the
  **edition toggle** (sun/moon).

## 11. Motion

Motion is functional and quick (**120–250ms**, standard ease): press-scale on the primary button,
drawer slide, modal fade-scale-up (bottom-sheet on mobile), toast in, active-nav underline. Chart
entrance animation is intentionally **disabled** — charts are rebuilt on every edition swap and tab
change, so an instant redraw is both more robust (no orphaned animation frame drawing to a
destroyed canvas) and calmer for `prefers-reduced-motion`, which additionally collapses all
transitions to near-zero. Forbidden: decorative loops, long entrances, and number count-ups that
delay a figure a marketer needs now.

## 12. Accessibility

- **AA on real surfaces, both editions** — body, caption, magenta, status-pill text, and all five
  spectrum hues (as graphics) clear WCAG 2.1 AA on their actual tinted backgrounds in Daylight
  **and** Nightshift.
- **Never color-only** — channel identity always pairs a hue with a text label; status always pairs
  a color with a label and a dot.
- **Touch first** — targets ≥ 44px; steppers, chips, selects, and nav all have large hit areas; no
  hover-only affordances.
- **Visible focus** — a 2px magenta `:focus-visible` outline on every interactive element; full
  keyboard operability; logical order; Esc closes every overlay; icon-only buttons carry
  `aria-label`; toasts announce via an `aria-live` region.
- **Honest states** — the campaigns table has a designed empty state (icon + explanation + reset);
  every action returns immediate feedback.

## 13. Tokens in Practice

Light under `:root`, dark under `html.dark`; the Daylight → Nightshift edition is one class swap:

```css
:root     { --canvas:#FBFAFC; --surface:#FFFFFF; --ink:#1B1524; --accent:#DB2777;
            --line:#ECE8F0; --line-2:#DAD3E2;
            --sp-1:#DB2777; --sp-2:#7C3AED; --sp-3:#2563EB; --sp-4:#0891B2; --sp-5:#E08600; }
html.dark { --canvas:#120E18; --surface:#1B1526; --ink:#F2ECF8; --accent:#F0559E;
            --line:#2E2740; --line-2:#3E3452;
            --sp-1:#F472B6; --sp-2:#A78BFA; --sp-3:#60A5FA; --sp-4:#22C3DD; --sp-5:#F5B547; }
```

The five spectrum hues are tokens, so a doughnut slice, a table dot, a progress bar, and a card
accent all read the same source; Chart.js reads them via `getComputedStyle` on every render, which
is why the charts recolor correctly on an edition swap. No raw hex in markup for spectrum or status
color, no magic spacing, no one-off durations.

> **Note — chrome separators.** App chrome (masthead edge, drawer edge, modal edge) uses `--line-2`,
> a touch stronger than card hairlines. Where a border must survive alongside a framework's dynamic
> `:style`/`:class` binding, set it in a class or a static inline `style` — not in the same
> reactive `:style` object — so the binding can't clobber the border.

## 14. Anti-Patterns Prism Forbids

- ❌ **Random chart color** — a hue that doesn't map to its channel. The spectrum is fixed.
- ❌ **Crossing the two color languages** — using a status color as a channel mark or vice-versa.
- ❌ **Spectrum hues as body text** — amber-on-white captions and the like; hues are graphic marks.
- ❌ **Magenta as a highlighter** — it is the brand and single primary action, not decoration.
- ❌ **A phone mock floating in a desktop window** — the demo is a real responsive layout.
- ❌ **Color-only status** with no label and no dot.
- ❌ **Dead nav** — every masthead item routes to a real, populated page.
- ❌ **Charts that don't recolor on edition swap** or that error on a hidden tab.

## 15. Pre-Ship Checklist

- [ ] Excellent on desktop **and** phone; reflows at ~375 / ~768 / ≥1280px; no phone-in-a-window.
- [ ] Every masthead item routes to a real, populated page (Overview, Campaigns, Channels,
      Audiences, Reports, Settings).
- [ ] BI dashboard with KPI tiles, line/area + bar + doughnut charts, and a data table.
- [ ] The five-hue spectrum is consistent (fixed channel→hue) across every chart, dot, bar, and card.
- [ ] Status system consistent (color + label + dot) across pills, the inline select, and forms —
      and distinct from the spectrum.
- [ ] Inline edits (status select + click-to-edit budget + click-to-edit name), edit drawer, nav
      drawer, and modal all work; Esc closes overlays.
- [ ] Full input range present (text, search, select, textarea, toggle, segmented, stepper, chips,
      numeric) — all keyboard usable with visible focus.
- [ ] Targets ≥ 44px; AA contrast in Daylight **and** Nightshift, including tinted pills and all
      five hues.
- [ ] Daylight **and** Nightshift both polished; charts re-render on swap and on tab activation;
      hidden canvases guarded.
- [ ] Chrome separators use `--line-2`; no console errors.

---

> **Colophon.** Set in Bricolage Grotesque and Fragment Mono. Prism is one theme in the
> [`my-themes`](../../README.md) gallery — the marketing-analytics, spectrum-driven counterpart to
> Meridian, Broadsheet, and Frontline.
