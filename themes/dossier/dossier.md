# Dossier — Theme Design Specification

> **Version 1.0** · Serif-led design system for contract lifecycle management · Daylight + Lamplight editions
> Tagline: **"Every contract is a case file."**

Most contract software treats an agreement as a row in a database. **Dossier treats it as a case
file** — a bound, indexed, authoritative record that a lawyer opens, reads, annotates, and closes.
It is a design system for the people who manage the *lifecycle* of commercial agreements: counsel,
contract managers, procurement, and the deal desk who live in renewals, obligations, and the
clauses that allocate risk. The interface is set in a serif, organized by hairline rules, and
printed on porcelain — it looks like something you would trust with a signature.

> **A distinct pole.** This repository already ships **Broadsheet** — the other serif-led theme.
> Broadsheet is a *newspaper front page*: editorial columns, oversized headlines, a single claret
> accent on tinted newsprint, provenance as a byline. Dossier is a *legal case file*: a numbered
> case index, a ruled ledger register, **two** accents (burgundy for the brand, navy as a
> structural secondary), porcelain stock, and a five-state contract-lifecycle status system. Same
> serif discipline, a completely different room. §2 maps the contrast in full.

---

## Table of Contents

1. [Design Principles](#1-design-principles)
2. [Dossier vs. the others](#2-dossier-vs-the-others)
3. [Brand & Voice](#3-brand--voice)
4. [Color System](#4-color-system)
5. [The Contract-Lifecycle Status System](#5-the-contract-lifecycle-status-system)
6. [Typography](#6-typography)
7. [Responsive Layout](#7-responsive-layout)
8. [Elevation, Radius & Surfaces](#8-elevation-radius--surfaces)
9. [Components & Patterns](#9-components--patterns)
10. [Renewals & Obligations](#10-renewals--obligations)
11. [Motion](#11-motion)
12. [Accessibility](#12-accessibility)
13. [Tokens in Practice](#13-tokens-in-practice)
14. [Anti-Patterns Dossier Forbids](#14-anti-patterns-dossier-forbids)
15. [Pre-Ship Checklist](#15-pre-ship-checklist)

---

## 1. Design Principles

Seven principles. When two conflict, the **earlier** wins.

### P1 — The record is authoritative
A contract is a legal instrument, not a card in a Kanban board. Every surface should read like a
document of record: a serif voice, real punctuation, hairline rules, and a quiet confidence. The
interface earns the trust it asks for when a user changes a status or files a new agreement.

### P2 — Structure with rules, not boxes-within-boxes
Dossier organizes with **hairline rules (1px), a numbered case index, and the double-ruled ledger
header** — the toolkit of a bound legal file — not by nesting shadowed cards three deep. Cards
exist, but they are flat, thin-bordered, and used as *sections of the file*, never as decoration.
The 3px double rule beneath a table header is the signature move.

### P3 — Status is the spine
The lifecycle state of a contract — **Draft → In review → Executed → Renewal due → Expired** — is
the backbone of the system (§5). Color, label, and icon travel together and mean the same thing in
a chip, a ledger cell, a renewal card, and the dashboard bar chart. Color reports state; it is
never spent on ornament.

### P4 — Two accents, each with a job
Burgundy is the **brand and the primary action** — the mark, links, the executed button, focus.
Navy is the **structural secondary** — it carries "in review", secondary data series, and the
navy avatar/chrome cues. This deliberate two-accent discipline (distinct from Broadsheet's single
claret) reads as *counsel's red-and-blue pen* rather than a rainbow.

### P5 — Legible on porcelain
The page is **porcelain** — a warm off-white paper stock, not stark white — easier across a long
day of document review. Tinted stock is an accessibility hazard done carelessly, so every
text/stock pair is measured against WCAG 2.1 AA *on the actual tint* (§12), in both editions.

### P6 — Numbers are set, not shouted
Figures — values, IDs, dates, notice periods — are set in a tabular monospace so columns align and
an identifier never blurs into prose. Headline figures use the serif at large size for a
document-cover gravity; the small print is mono for instrument-grade precision.

### P7 — Calm, deliberate motion
A case file does not animate. Transitions explain a state change in one short, eased beat —
a drawer slides in, a toast lifts, a modal fades up — and then get out of the way. Nothing loops,
nothing bounces, nothing delays the reader from the fact.

---

## 2. Dossier vs. the others

Both Dossier and Broadsheet are serif-led, hairline-ruled, and AA-accessible. They diverge on
metaphor, structure, color, and domain — deliberately, so the gallery holds two serif systems that
never read alike.

| Axis | **Broadsheet** | **Frontline** | **Dossier** |
| --- | --- | --- | --- |
| Metaphor | Newspaper front page | Field / ops app | **Legal case file** |
| Domain | Executive BI / financial reporting | Field service & dispatch | **Contract lifecycle management** |
| Structure | Editorial columns + headlines | Tactile elevated cards | **Numbered case index + ruled ledger** |
| Type | Fraunces + Archivo + Spline Mono | Saira + Martian Mono | **Spectral + Roboto Mono** |
| Surface | Tinted **newsprint** | Hi-vis concrete | **Porcelain** (warm off-white) |
| Accent | **One** claret | Safety orange | **Two** — burgundy + navy |
| Neutral ramp | Warm stone | Cool concrete | **Warm parchment** |
| Signature move | Byline under every figure | Offline sync state | **Double-rule ledger + lifecycle status** |
| Organizing idea | Editorial hierarchy | Operational status + glance | **Provenance & obligation** |
| Modes | Day / Evening | Field / Shift | **Daylight / Lamplight** |

Use **Dossier** for CLM, legal operations, procurement, vendor management, and any product whose
job is to make a portfolio of *agreements* — their value, their renewals, and their obligations —
legible and trustworthy.

---

## 3. Brand & Voice

Dossier speaks like careful commercial counsel: **precise, attributed, and unhurried.** It uses
the vocabulary of a law office, applied consistently as product language:

- **Case index** — the numbered navigation rail (the binder's table of contents).
- **Register** — the master contracts ledger.
- **Counterparty** — the other side of an agreement (never "customer/vendor" generically).
- **Instrument / type** — MSA, SOW, NDA, Lease, License, Supply.
- **Notice window** — the period before renewal in which notice must be served.
- **Obligation** — a post-signature duty (report, audit, certificate) with an owner and a due date.
- **File a contract** = create; **execute** = sign; **lapse / expire** = end of term.
- **Privileged & Confidential** — the footer stamp; the record is treated with discretion.

The mark is a **burgundy block with a scale (`⚖`)** and the wordmark set in Spectral. The tone is
plain and active — "Renewal due", "Save changes", "File contract" — never cheerful filler, never
system jargon.

---

## 4. Color System

Two editions, one token set. **Daylight** (light) is porcelain for desk work; **Lamplight** (dark)
is a warm ink-brown charcoal for late review under a desk lamp. Every value is a role token, so the
swap is a single class on `<html>`.

### Daylight edition (light)

| Role | Token | Value |
| --- | --- | --- |
| App background (porcelain) | `--canvas` | `#F2F1EC` |
| Surface (cards, chrome) | `--surface` | `#FFFFFF` |
| Inset surface | `--surface-2` | `#F7F6F1` |
| Primary text | `--ink` | `#21201C` |
| Secondary text | `--ink-2` | `#57544C` |
| Caption / label | `--ink-3` | `#736D5E` |
| Hairline (cards, rows) | `--line` | `#E5E2D9` |
| Structural separator (chrome, ledger head) | `--line-2` | `#D3CEC1` |
| Brand (burgundy) | `--accent` | `#7C2D3A` |
| Brand pressed | `--accent-press` | `#642430` |
| Brand tint (chips, active nav) | `--accent-soft` | `#F3E1E3` |
| Structural secondary (navy) | `--navy` | `#26364D` |
| Positive | `--pos` | `#2F6B4F` |
| Warning | `--warn` | `#8F6410` |
| Negative | `--neg` | `#A03443` |

### Lamplight edition (dark)

Warm ink-brown, never pure black. `--canvas #16130E`, `--surface #1F1B15`, `--surface-2 #26221A`,
`--ink #F0EBE0`, hairlines `#332D23` / separators `#443C2E`. **Burgundy lifts to a lamp-lit rose**
`--accent #E29AA4` and **navy lifts to a slate-blue** `--navy #9DB2D6`, so both accents clear AA on
the dark stock (7.7:1 and 8.0:1 on surface). Semantic colors lighten in step (`--pos #74C193`,
`--warn #D8A63F`, `--neg #E58A94`).

**Rules of use.** Burgundy is the brand and primary action — decisive, not sprayed. Navy is the
structural secondary — "in review", the second data series, avatar chrome. A **dedicated structural
separator** (`--line-2`, a touch stronger than card hairlines) defines the sidebar edge, top bar,
and the ledger header rule so the file reads as a bound document; row and card borders stay on the
lighter `--line`. Status colors (§5) are reserved for lifecycle state.

---

## 5. The Contract-Lifecycle Status System

The heart of the system. Five lifecycle states, each a fixed triplet of **color + label + icon**,
used identically in filter chips, the inline-editable ledger cell, renewal cards, and the
dashboard "contracts by stage" bar chart — all reading one token source.

| State | Token | Daylight | Meaning |
| --- | --- | --- | --- |
| Draft | `--s-draft` | `#736D5E` | Being drafted; not yet circulated |
| In review | `--s-review` | `#26364D` (navy) | Under legal / counterparty review |
| Executed | `--s-exec` | `#2F6B4F` (green) | Signed and in force |
| Renewal due | `--s-renew` | `#8F6410` (amber) | Inside the notice window |
| Expired | `--s-expired` | `#A03443` (red) | Term lapsed |

Status is **never carried by color alone** — a label (and dot/icon) always accompanies it. Chips
tint the state color at ~14% alpha for the fill, a 30% hairline border, and full strength for
text, holding AA on the tint. In Lamplight all five lighten in step (`--s-review #9DB2D6`,
`--s-exec #74C193`, `--s-renew #D8A63F`, `--s-expired #E58A94`, `--s-draft #948C7A`).

**Obligations** use a parallel compliance triplet — **Met / Due / Overdue** — mapped onto the
semantic `--pos / --warn / --neg` tokens and rendered with the *same chip component*, so the two
systems feel like one family without overloading a single scale.

---

## 6. Typography

Two typefaces, chosen for a documentary, authoritative legibility — a serif that reads like a
printed instrument, and a mono that sets every figure like a schedule.

| Role | Typeface | Used for |
| --- | --- | --- |
| Voice / display / body | **Spectral** | Headings, headline figures, body, buttons — the document voice |
| Figures / codes / labels | **Roboto Mono** | Values, contract IDs, dates, notice periods, small-caps kickers |

- **Spectral** is a screen-tuned serif with the contrast and calm of a legal document — confident,
  not decorative. Headline figures are set large in Spectral for a document-cover gravity that a
  grotesk cannot give.
- **Roboto Mono** (tabular) aligns every number and identifier in the ledger and gives the small
  uppercase **kicker** labels an instrument-grade, engineered counterpoint to the serif.
- Hierarchy is by size and weight within a restrained scale (≈ `12, 14, 15, 18, 20, 24, 34`), not
  by color. Body is a comfortable **15px**; kickers are 10px uppercase with wide `0.18em` tracking.

---

## 7. Responsive Layout

One app shell, two shapes — driven by breakpoints, not a separate build.

- **Desktop (≥ 1024px):** persistent left **case-index sidebar** + sticky **top bar** + fluid
  content. The dashboard is a multi-column grid (KPI tiles → charts → register table).
- **Tablet (≥ 640px):** grids relax to two columns; tables keep priority columns and scroll
  horizontally within their card; the sidebar persists.
- **Phone (< 1024px):** the sidebar becomes a **left navigation drawer** behind a hamburger; a
  dedicated mobile search sits under the top bar; content stacks to one column; the ledger scrolls
  horizontally. Touch targets ≥ 44px throughout.

The same tokens, components, and status system render in both — only the arrangement changes. A
phone mock floating in a desktop window is a failure, not a feature.

---

## 8. Elevation, Radius & Surfaces

Dossier is **crisp and flat**, the opposite of a playful, deeply-rounded SaaS look — its depth is
in the *paper*, not in drop shadows.

- **Small radii:** `--radius` 4px for controls and cards, `--radius-lg` 6px for larger surfaces
  (modal, drawer). Documentary and precise, never bubbly.
- **Restrained elevation:** `--shadow-sm` for resting cards (a whisper), `--shadow-md` for toasts,
  `--shadow-lg` for overlays (drawer, modal) that must lift clearly above the file.
- **Three surface levels:** `--canvas` (porcelain page) → `--surface` (cards & chrome) →
  `--surface-2` (insets, fields, ledger header, zebra hover). The double-ruled ledger header and
  the dotted case-index leaders are the texture; shadows stay subtle.

---

## 9. Components & Patterns

- **Case index (nav)** — a numbered table of contents with dotted leaders and per-item counts; the
  active entry is marked with a burgundy left-border and tint. The signature navigation surface.
- **KPI tile** — kicker + oversized serif figure + trend delta; the dashboard's glance layer.
- **Charts** — area (contract value + renewal count over time), bar (contracts by lifecycle stage,
  colored by the status system), doughnut (portfolio by risk tier), and a renewals-by-month bar —
  all styled to the edition and re-rendered on edition swap and tab activation.
- **Ledger / register table** — double-ruled small-caps header, sortable-looking headers (real
  sort on ID / party / value / renewal), hairline zebra hover, an **inline-editable status
  `<select>`** that updates the row optimistically, and a responsive horizontal scroll.
- **Edit drawer (right)** — open a contract, edit party, type, value, status, renewal, owner, and
  risk in place; Save/Cancel with a toast. Esc closes.
- **Nav drawer (left)** — the mobile case index.
- **Modal** — a centered "New contract" dialog with scrim, Esc-to-close, and a working file action
  that inserts a draft and routes to the register.
- **Inline edits** — an editable ledger cell (status), an editable obligation owner/status, and a
  click-to-edit name on Settings that swaps to an input with Save/Cancel.
- **Inputs** — text, search, `<select>`, textarea, toggle switch, segmented control, **stepper**
  (+/− notice period), filter chips, and a numeric field — all keyboard-usable with visible focus.
- **Status / risk chip**, **toast** (action feedback), and a **Daylight/Lamplight** edition toggle.

---

## 10. Renewals & Obligations

The Dossier-specific concern — the part of the lifecycle that generic tools drop.

- **The notice window is a first-class object.** Every renewal carries a per-contract **notice
  period** (adjusted with a +/− stepper) and an **auto-renew** toggle. A missed notice window is
  the single most expensive contract mistake; Dossier makes it visible and adjustable.
- **Renewal urgency is computed and colored.** Days-to-renewal is derived from a fixed "today" and
  tinted amber inside 30 days, so a due renewal reads at a glance and matches the lifecycle status.
- **Obligations track duties, not documents.** Each obligation has an owner, a due date, and a
  compliance state (Met / Due / Overdue), both inline-editable. Overdue is stated plainly in red —
  informative, not alarmist.

---

## 11. Motion

Motion is functional and quick (**140–220ms**, standard ease): drawer slide, modal fade-scale,
toast rise, chip and nav hover. It confirms an action landed and shows where a surface came from.
`prefers-reduced-motion` is honored with a calm, motion-free alternative. Forbidden: decorative
loops, long entrances, and number animations that delay a figure the reviewer needs now.

---

## 12. Accessibility

- **AA on the actual stock, both editions.** Body, secondary, caption, accent, navy, and all
  semantic/status colors clear WCAG 2.1 AA on their real surfaces — porcelain *and* Lamplight,
  including tinted `--surface-2` — verified by contrast calculation, not assumed on white.
- **Never color-only** — every lifecycle and compliance state pairs its color with a label (and a
  dot/icon).
- **Visible focus** — a 2px burgundy outline on every interactive element; full keyboard
  operability; logical order; role-tagged switches and links reachable by Enter.
- **Overlays behave** — Esc closes the drawer and modal; scrims dismiss; icon-only buttons carry
  `aria-label`; toasts sit in an `aria-live="polite"` region.
- **Honest states** — the register has a designed empty state with a "Clear filters" recovery; due
  and overdue are surfaced explicitly.
- **Touch first where it counts** — targets ≥ 44px; steppers and toggles have large hit areas.

---

## 13. Tokens in Practice

Light under `:root`, dark under `html.dark`; Daylight → Lamplight is one class swap:

```css
:root     { --canvas:#F2F1EC; --surface:#FFFFFF; --ink:#21201C; --accent:#7C2D3A; --navy:#26364D;
            --line:#E5E2D9; --line-2:#D3CEC1; /* … Daylight */ }
html.dark { --canvas:#16130E; --surface:#1F1B15; --ink:#F0EBE0; --accent:#E29AA4; --navy:#9DB2D6;
            --line:#332D23; --line-2:#443C2E; /* … Lamplight */ }
```

The five lifecycle statuses are tokens too (`--s-draft … --s-expired`), so a filter chip, an inline
ledger cell, a renewal card, and a bar-chart slice all read the same source. No raw hex in markup,
no magic spacing, no one-off durations.

> **Note — chrome separators.** App chrome (sidebar edge, top bar, ledger header rule) uses
> `--line-2` via a CSS **class** (`.sidebar`, `.topbar`, `table.dossier thead tr`), *not* a
> clobberable inline `:style`. Binding layout with a framework's dynamic `:style` while also setting
> borders inline can wipe the border — keep structural styling in classes.

---

## 14. Anti-Patterns Dossier Forbids

- ❌ **Reading like Broadsheet** — no editorial column-and-headline front page; Dossier is a case
  file (numbered index + ruled ledger), a different domain, and a two-accent palette.
- ❌ **Boxes within boxes within boxes** — structure with rules and the case index, not nested
  shadowed cards.
- ❌ **Decorative use of burgundy or navy** — burgundy is brand/primary, navy is structural; neither
  is a highlighter.
- ❌ **Color-only status** with no label.
- ❌ **A phone mock floating in a desktop window** — the demo is one responsive layout.
- ❌ **Deep rounding / heavy shadows** — the file is crisp and flat; depth lives in the paper.
- ❌ **Placeholder-as-label** in forms, or clearing input on error.
- ❌ **Low-contrast "elegant" grays** on porcelain that fail AA on the tint.

---

## 15. Pre-Ship Checklist

- [ ] Excellent on desktop **and** phone; reflows at ~375 / ~768 / ≥1280px; no phone-in-a-window.
- [ ] Every case-index item routes to a real, populated page (Overview, Contracts, Renewals,
      Obligations, Clauses, Settings).
- [ ] BI dashboard with KPI tiles, area + bar + doughnut charts, and a register table.
- [ ] Lifecycle status system consistent (color + label + icon) across chips, ledger cell, renewal
      cards, and the stage bar chart.
- [ ] Inline edits work (status cell, obligation owner/status, click-to-edit name); edit drawer,
      nav drawer, and modal all function with Esc/scrim dismissal.
- [ ] Notice-period steppers and auto-renew toggles operate; renewal urgency is computed & colored.
- [ ] Targets ≥ 44px; visible burgundy focus; never color-only; AA contrast in Daylight **and**
      Lamplight, measured on the actual (tinted) stock.
- [ ] Daylight **and** Lamplight both polished; charts re-render on edition swap and tab activation
      (hidden canvases guarded via `offsetParent === null`).
- [ ] Chrome separators use class-based `--line-2`, not a clobberable inline style.

---

> **Colophon.** Set in Spectral and Roboto Mono. Dossier is one theme in the
> [`my-themes`](../../README.md) gallery — the case-file, contract-lifecycle counterpart to the
> newspaper-front-page Broadsheet and the field-first Frontline.
