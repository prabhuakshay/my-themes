# Broadsheet — Theme Design Specification

> **Version 1.0** · Editorial design system for enterprise data · Day + Evening editions
> Tagline: **"Enterprise data, set like the financial press."**

A *broadsheet* is the large-format quality newspaper — the front page where the day's most
consequential numbers are reported with authority, hierarchy, and a point of view. Broadsheet
treats an enterprise data app the same way: a dashboard is a **front page**, a metric is a
**headline**, and every figure carries a **byline** that says where it came from and how much to
trust it. This is not decoration borrowed from print — it is a discipline. The financial press
spent a century learning how to make dense, high-stakes numbers legible and credible under a
deadline. Broadsheet ports that craft to software.

> **Why a second system?** This repository already ships **Meridian Enterprise** — a Carbon-grade
> *instrument panel*: monospace tokens, boxed grids, cool gray, density as a virtue. Broadsheet is
> its deliberate opposite on every axis that matters, while serving the same user. Where Meridian
> is the cockpit, Broadsheet is the morning paper. The contrast is the point: same rigor, opposite
> temperament. §2 lays out the axes explicitly.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Broadsheet vs. Meridian — the contrast](#2-broadsheet-vs-meridian--the-contrast)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [Typography](#5-typography)
6. [The Editorial Grid](#6-the-editorial-grid)
7. [Rules, Stock & Elevation](#7-rules-stock--elevation)
8. [Signature Patterns](#8-signature-patterns)
9. [Motion](#9-motion)
10. [Data & Reporting](#10-data--reporting)
11. [Accessibility](#11-accessibility)
12. [Voice & Microcopy](#12-voice--microcopy)
13. [Tokens in Practice](#13-tokens-in-practice)
14. [Anti-Patterns Broadsheet Forbids](#14-anti-patterns-broadsheet-forbids)
15. [Pre-Ship Checklist](#15-pre-ship-checklist)

---

## 1. Design Principles

Seven principles. When two conflict, the **earlier** wins.

### P1 — The number is the headline
The single most consequential figure on any view is set largest, in the display serif, like a
front-page headline. Hierarchy is decided by editorial judgement — *what matters most today* —
not by giving every KPI an equal card. A page with twelve equal tiles has no front page.

### P2 — Every figure has a byline
No number appears without its provenance: **source**, **freshness**, and **confidence**. "Updated
12s ago · Source: Billing API · audited" is not a tooltip afterthought — it is set beneath the
figure like a byline beneath a headline. In enterprise data, an unattributed number is a rumor.

### P3 — Structure with rules, not boxes
The page is organized by **hairline rules, column gutters, and whitespace** — the broadsheet's
toolkit — not by wrapping everything in bordered, shadowed cards. Boxes fragment; rules and
columns let the eye read across. Reserve the inset surface for genuine data tables and charts.

### P4 — Type does the work
Voice, hierarchy, and rhythm come from a **three-typeface system** — a high-contrast display
serif, a sturdy grotesque, and a tabular mono — not from a rainbow of colors or weights. If a
view reads clearly in one accent color, it is designed correctly.

### P5 — One accent, spent with intent
A single **claret** carries the brand: the masthead rule, kickers, links, the primary action,
focus. Semantic up/down green and claret-red are the *only* other hues. Color is a scarce
editorial resource; spend it where it reports something.

### P6 — Print-grade legibility on tinted stock
The page is **tinted newsprint**, not stark white — warmer, lower-glare, easier across an
eight-hour shift. Tinted backgrounds are an accessibility *hazard* if done carelessly, so every
text/stock pair is held to WCAG 2.1 AA *as measured on the tint* (§11), never on an assumed white.

### P7 — Calm under deadline
Motion is restrained because print doesn't animate. Transitions explain a state change in one
short, eased beat and then get out of the way. The desk is busy; the page is calm.

---

## 2. Broadsheet vs. Meridian — the contrast

Both are enterprise, data-first, token-driven, and AA-accessible. They diverge on temperament:

| Axis | **Meridian Enterprise** | **Broadsheet** |
| --- | --- | --- |
| Metaphor | Instrument panel / cockpit | Quality newspaper / front page |
| Lineage | IBM Carbon, Swiss systems | FT, The Economist, Bloomberg Businessweek |
| Type | IBM Plex Sans + Plex Mono | Fraunces (serif) + Archivo + Spline Sans Mono |
| Headline figures | Mono, equal-weight tiles | Oversized display **serif**, editorial hierarchy |
| Structure | Boxed 2px grid, 1px borders | Hairline **rules** + column gutters, few boxes |
| Surface | Neutral white / Gray-100 | **Tinted newsprint** stock, warm |
| Neutral ramp | Cool Carbon gray | **Warm** stone / ink |
| Accent | Carbon blue `#0f62fe` | **Claret** `#94252B` |
| Density | Maximal, dense-but-disciplined | Generous, hierarchy-by-whitespace |
| Provenance | Status chip / freshness label | **Byline** + footnotes |
| Modes | White / Gray-100 | **Day / Evening edition** |
| Temperament | Engineered, exact, neutral | Authoritative, narrative, warm |

Use **Meridian** for control surfaces, ops consoles, and dense operational tooling. Use
**Broadsheet** for executive analytics, BI, financial reporting, and any view whose job is to make
a reader *understand and trust* a set of numbers.

---

## 3. Brand & Voice

Broadsheet speaks like a respected financial desk: **precise, attributed, and quietly confident.**
It reports; it does not hype. Numbers lead, claims are sourced, and uncertainty is stated plainly
("unaudited, subject to revision") rather than hidden. The vocabulary is borrowed from the
newsroom and used consistently as product language:

- **Kicker** — the small-caps label above a figure (the section/eyebrow).
- **Headline** — the figure or title itself, in the display serif.
- **Standfirst / dek** — the one-sentence summary under a headline.
- **Byline** — the provenance line: source · freshness · confidence.
- **Dispatch** — a notification or alert.
- **The desk** — the workspace; "file a report" = create; "spike" = discard.
- **Edition** — a saved view or a theme mode (Day / Evening).

---

## 4. Color System

Broadsheet runs on **warm** neutrals and one editorial accent. Every value is a role token so the
Day → Evening swap is a token change, never a refactor.

### Day edition (light)

| Role | Token | Value |
| --- | --- | --- |
| Page (newsprint) | `--paper` | `#F2EBDC` |
| Raised surface | `--stock` | `#FBF7EE` |
| Data inset (tables/charts) | `--inset` | `#FFFFFF` |
| Ink (primary text) | `--ink` | `#1C1813` |
| Secondary text | `--ink-2` | `#5B5346` |
| Caption / metadata | `--ink-3` | `#8E8573` |
| Hairline rule | `--rule` | `#DAD1BD` |
| Strong rule | `--rule-2` | `#C3B7A0` |
| Accent (claret) | `--accent` | `#94252B` |
| Accent on paper (text) | `--accent-2` | `#7C1E24` |
| Positive (ledger green) | `--up` | `#2C6A4E` |
| Negative (claret) | `--down` | `#94252B` |
| Caution (ochre) | `--warn` | `#946312` |

### Evening edition (dark)

The Evening edition is a warm deep-ink, not a cool black — the paper goes to dusk, not to a
terminal. `--paper #13100B`, `--stock #1B1711`, `--inset #211C15`, `--ink #EFE6D4`, rules warm up
to `#352E23` / `#4A4233`, and the accent **lightens** to `#D76A6E` so claret survives on dark
stock at AA. Green/red semantics lighten in step (`--up #6FB58F`, `--down #D76A6E`).

**Rules of use.** One accent per view for brand/interaction; green and claret-red *only* for
data direction; ochre *only* for caution. Never tint a large surface — color rides on rules,
figures, and small marks. Direction is never carried by color alone (§11).

---

## 5. Typography

Three typefaces, each with one job. This is the system's loudest signal and its primary tool for
hierarchy.

| Role | Typeface | Used for |
| --- | --- | --- |
| Display | **Fraunces** (opsz, high contrast) | Headlines, figures, the masthead, pull-figures |
| Text / UI | **Archivo** (grotesque) | Body, labels, buttons, dek/standfirst |
| Figures / meta | **Spline Sans Mono** | Tabular numbers, bylines, kickers, table data |

- **Display (Fraunces)** — weight 600, tight leading (1.0–1.05), negative tracking. Reserved for
  the things that lead: the big number, the section headline, the wordmark. Never set body in it.
- **Tabular figures everywhere numbers align** — `font-feature-settings:'tnum' 1`. Columns of
  money must line up to the digit; this is non-negotiable in a ledger.
- **Kickers & bylines** are Spline Sans Mono, small (10–11px), uppercase, letter-spacing `.12–.18em`.
  The mono + tracking is what makes a label read as "newsroom metadata" rather than a generic tag.
- **Type scale (Day):** figure-lead 72 / headline 24–26 / sub-headline 20 / secondary figure 34 /
  body 14–17 / caption 11. Hierarchy is steep on purpose — the front page is not flat.

---

## 6. The Editorial Grid

- A **12-column** grid with **generous gutters** (24–36px). The lead spread is asymmetric —
  typically `1.55fr / 1fr` — so the eye knows the lead story from the secondary column. Symmetry
  is for grids of equals; a front page has a lead.
- **Column rules** (a 1px vertical hairline in the gutter) separate the lead from the secondary
  column, exactly as a newspaper does. Horizontal hairline rules separate sections.
- Spacing rhythm is a **4px base**; section breaks are generous (28–32px) and carry a rule.
- Line length for any reading text (dek, standfirst, notes) is capped at **~54–66 characters**.

---

## 7. Rules, Stock & Elevation

Broadsheet is almost **flat** — depth comes from *stock* (surface tint) and *rules*, not shadow.

- **Three stock levels:** `--paper` (the page) → `--stock` (raised reading areas: sidebar,
  masthead, modals) → `--inset` (data surfaces: tables and charts sit on the cleanest stock so
  figures read crisply).
- **Rules** are the structural device: hairline `--rule` for in-content separation, `--rule-2`
  for section breaks, the **double rule** and **3px claret rule** for the masthead, and a `3px
  double` rule for the colophon/footer. A box is used only when content is genuinely tabular.
- **Radius is near-zero** (0–2px). Newspapers have square corners; so does Broadsheet. (Note this
  is *not* how it differs from Meridian — both are sharp. The difference is serif type, tinted
  stock, rules-over-boxes, and editorial hierarchy.)
- **Shadow** is reserved for true overlays (modal, toast) only, and kept soft and low.

---

## 8. Signature Patterns

These are the components that make a screen unmistakably Broadsheet.

- **Lead figure** — kicker + oversized Fraunces number + inline YoY delta + dek + byline.
- **Byline line** — `Source: X · Updated Ns ago · Confidence: audited` in mono, with optional
  superscript footnote markers linking to a notes block. The accountability primitive of the system.
- **Secondary column** — a stack of smaller figures divided by hairline rules, each with its own
  kicker and delta. The "rest of the front page."
- **Ticker** — a single mono strip of headline metrics with ▲/▼ direction marks; the running
  state of the business above the fold.
- **The Listings (ledger table)** — a data table styled as a stock listing: mono tabular figures,
  small-caps column heads, hairline rows, right-aligned numbers, status as a `dot + label`, and
  deltas colored by direction *and* signed (`+6.2%` / `-1.4%`).
- **Pull-figure** — an oversized number with a claret left-rule and a one-line dek, for calling
  out a single statistic mid-page.
- **Drop cap** — an optional editorial flourish on a lead standfirst.
- **Notes / footnotes** — numbered provenance and caveats in mono, at the foot of a section.
- **Masthead** — title + edition line + double claret rule; the page's nameplate.

## 9. Motion

Print doesn't animate, so Broadsheet barely does. Durations **120–220ms**, standard ease.
Permitted: overlay fade/scale (modal, toast), hover tints, edition (theme) cross-fade, segmented-
control selection. Forbidden: parallax, attention-seeking loops, number odometers that delay the
truth, decorative entrance animations on data. A figure should be *correct on arrival*, not
performed.

## 10. Data & Reporting

- **Report, don't just plot.** Every chart gets a serif title, a kicker ("Figure 1"), and a
  **source line** beneath it — the infographic conventions of the financial press.
- **Direction is signed and marked**, never color-only: `▲ 2.4%` / `▼ 0.3pt`, green/claret as
  reinforcement.
- **State the audit boundary.** Mark unaudited/in-progress figures explicitly ("current month
  unaudited, subject to revision"). Never present an estimate as settled.
- **Charts are quiet:** 1.5px lines, faint accent fill, hairline gridlines, mono axis ticks,
  no chartjunk. The data is the ink.
- **Tabular alignment is sacred:** money right-aligned, tabular figures, consistent precision per
  column.

## 11. Accessibility

Tinted stock makes contrast *easier to get wrong*, so it is verified deliberately, not assumed.

- **WCAG 2.1 AA on the actual tint.** Body `--ink` on `--paper` and on `--stock` both clear 4.5:1;
  `--ink-2` clears 4.5:1 for secondary text; `--ink-3` is used only for ≥18px/caption metadata and
  is held to 3:1+. Claret `--accent-2` is the on-paper text weight; `--accent` is reserved for
  fills/marks where it isn't carrying small text.
- **Never color-only.** Up/down always pair color with a glyph (▲/▼) and a sign (+/−); status
  always pairs the dot with a word ("Healthy / Watch / At risk").
- **Visible focus:** a 2px claret outline with 1px offset on every interactive element; full
  keyboard operability; logical tab order following the editorial reading order.
- **Targets** ≥ 36px (controls) trending to 44px for primary actions; reduced-motion honored.
- **Both editions** (Day and Evening) are independently held to AA — the accent lightens in
  Evening precisely so it stays legible on dark stock.

## 12. Voice & Microcopy

- **Headlines are nouns and numbers**, not exhortations. "$48.2M" and "Top accounts by MRR", not
  "Check out your revenue!"
- **Attribute everything.** A figure without a source line is incomplete copy.
- **State uncertainty plainly.** "Unaudited", "subject to revision", "estimated" — the desk is
  honest about what it doesn't yet know.
- **Newsroom verbs, used consistently:** file / publish / spike / embargo / dispatch. Use them in
  the product the way the spec defines them, or not at all — half-applied metaphor is worse than none.

## 13. Tokens in Practice

Every value resolves to a CSS custom property; the Day → Evening edition is a single class swap on
`<html>`:

```css
:root            { --paper:#F2EBDC; --ink:#1C1813; --accent:#94252B; /* … Day */ }
html.dark        { --paper:#13100B; --ink:#EFE6D4; --accent:#D76A6E; /* … Evening */ }
```

```css
.kicker  { font-family:'Spline Sans Mono'; text-transform:uppercase; letter-spacing:.18em;
           color:var(--accent-2); font-size:10.5px; font-weight:600; }
.headline{ font-family:'Fraunces'; font-weight:600; line-height:1.04; }
.figure  { font-family:'Fraunces'; font-weight:600; font-feature-settings:'tnum' 1; }
.byline  { font-family:'Spline Sans Mono'; font-size:11px; color:var(--ink-3);
           text-transform:uppercase; letter-spacing:.04em; }
```

No raw hex in a feature branch, no magic margins, no one-off durations — theming, rebranding, and
the Evening edition are all token swaps.

## 14. Anti-Patterns Broadsheet Forbids

- ❌ **A wall of equal KPI cards** with no lead — every metric shouting at the same volume.
- ❌ **Unattributed numbers** — a figure with no source, freshness, or confidence.
- ❌ **Color as the only signal** for direction or status.
- ❌ **Stark white pages** — the system is tinted stock; white is for data insets only.
- ❌ **Boxing everything** in bordered, shadowed cards instead of using rules and columns.
- ❌ **Body text in the display serif**, or more than the three sanctioned typefaces.
- ❌ **Odometer/number-spinner animations** that delay or perform the truth.
- ❌ **A second accent color** introduced for decoration.
- ❌ **Proportional figures in a ledger** — numbers that don't line up by digit.

## 15. Pre-Ship Checklist

- [ ] The most important number on the view is the largest, in the display serif.
- [ ] Every figure carries a byline: source · freshness · confidence.
- [ ] Direction is signed (+/−) and marked (▲/▼), not color-only; status pairs dot + word.
- [ ] Structure uses rules and columns; boxes only wrap genuine data tables.
- [ ] Only claret + semantic green/claret-red + ochre appear; one accent per view.
- [ ] Tabular figures and right-aligned money in every ledger.
- [ ] Charts have a kicker, a serif title, and a source line.
- [ ] Day **and** Evening editions both pass WCAG 2.1 AA on the actual tinted stock.
- [ ] Visible 2px claret focus on every interactive element; full keyboard path.
- [ ] Unaudited/estimated figures are labeled as such.

---

> **Colophon.** Set in Fraunces, Archivo, and Spline Sans Mono. Broadsheet is one theme in the
> [`my-themes`](../../README.md) gallery — the editorial counterpart to **Meridian Enterprise**.
> Same reader, opposite temperament.
