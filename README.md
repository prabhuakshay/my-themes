<div align="center">

# my-themes

### A gallery of design systems & UI themes.

Self-contained, zero-build themes — each with a full design spec and a live, in-browser demo.

[**▶ Browse the live gallery**](https://prabhuakshay.github.io/my-themes/)

![Themes](https://img.shields.io/badge/themes-13-161616)
![License](https://img.shields.io/badge/license-MIT-0f62fe)
![Build](https://img.shields.io/badge/build-zero--build-525252)

</div>

---

This repo collects design themes I build. Every theme is **self-contained** — open its
`index.html` in any browser, no install or build step — and ships with a written spec so the
intent behind every token and component is documented, not just demonstrated.

## Themes

| Theme | Description | Links |
| --- | --- | --- |
| **[Meridian Enterprise](./themes/meridian-enterprise/)** | Calm, governance-grade B2B design system — a Carbon-grade *instrument panel*: mono tokens, 2px grid, sharp 1px borders, cool gray, light + dark. | [Demo](https://prabhuakshay.github.io/my-themes/themes/meridian-enterprise/) · [Spec](./themes/meridian-enterprise/meridian-enterprise.md) · [README](./themes/meridian-enterprise/README.md) |
| **[Broadsheet](./themes/broadsheet/)** | Editorial system for enterprise data — a *front page*: tinted newsprint, serif headlines, claret accent, hairline rules, every figure bylined. Day + Evening. | [Demo](https://prabhuakshay.github.io/my-themes/themes/broadsheet/) · [Spec](./themes/broadsheet/broadsheet.md) · [README](./themes/broadsheet/README.md) |
| **[Frontline](./themes/frontline/)** | Responsive system for field & ops software — a *field app*: hi-vis palette, five-state operational status, tactile elevated cards, offline-aware. Desktop **and** phone. Field + Shift. | [Demo](https://prabhuakshay.github.io/my-themes/themes/frontline/) · [Spec](./themes/frontline/frontline.md) · [README](./themes/frontline/README.md) |
| **[Vellum](./themes/vellum/)** | Premium system for BI apps built around data entry — *the record is the hero*: warm porcelain paper, iris ink, tabular figures, a legible records pipeline, an entry sheet that's a page not a modal. Light only. | [Demo](https://prabhuakshay.github.io/my-themes/themes/vellum/) · [Spec](./themes/vellum/vellum.md) · [README](./themes/vellum/README.md) |
| **[Cardinal](./themes/cardinal/)** | Revenue / sales pipeline — a *revenue desk*: warm paper, cardinal red + deep teal, executive-scale figures, a pipeline stage-board. Sora. Daybook + After-hours. | [Demo](https://prabhuakshay.github.io/my-themes/themes/cardinal/) · [Spec](./themes/cardinal/cardinal.md) · [README](./themes/cardinal/README.md) |
| **[Beacon](./themes/beacon/)** | Customer support / helpdesk — a *calm signal in the queue*: soft lilac, friendly violet + SLA amber, rounded, CSAT & ticket queue. Manrope. Daylight + Nightwatch. | [Demo](https://prabhuakshay.github.io/my-themes/themes/beacon/) · [Spec](./themes/beacon/beacon.md) · [README](./themes/beacon/README.md) |
| **[Foundry](./themes/foundry/)** | Data pipeline / ETL orchestration — the *plant*: blueprint-grid slate, molten amber, monospace run logs, pipeline health. Chivo. Blueprint + Control Room. | [Demo](https://prabhuakshay.github.io/my-themes/themes/foundry/) · [Spec](./themes/foundry/foundry.md) · [README](./themes/foundry/README.md) |
| **[Sage](./themes/sage/)** | HR / people ops — the *roster*: cream paper, moss green + clay, humane and airy, headcount & attrition. Schibsted Grotesk. Daylight + Lamplight. | [Demo](https://prabhuakshay.github.io/my-themes/themes/sage/) · [Spec](./themes/sage/sage.md) · [README](./themes/sage/README.md) |
| **[Voltaic](./themes/voltaic/)** | Energy / grid monitoring — the *control gauge*: charcoal SCADA chrome, electric lime + amber alarms, load gauges & substations. Red Hat Display. Day Board + Control Room. | [Demo](https://prabhuakshay.github.io/my-themes/themes/voltaic/) · [Spec](./themes/voltaic/voltaic.md) · [README](./themes/voltaic/README.md) |
| **[Tessera](./themes/tessera/)** | Procurement / inventory — the *warehouse mosaic*: true-neutral zinc, cobalt accent, tiled KPIs, SKU & PO tables. Familjen Grotesk. Floor + Nightshift. | [Demo](https://prabhuakshay.github.io/my-themes/themes/tessera/) · [Spec](./themes/tessera/tessera.md) · [README](./themes/tessera/README.md) |
| **[Prism](./themes/prism/)** | Marketing / campaign analytics — the *spectrum*: bright white, magenta + a five-hue spectrum, channel mix & campaigns. Bricolage Grotesque. Daylight + Nightshift. | [Demo](https://prabhuakshay.github.io/my-themes/themes/prism/) · [Spec](./themes/prism/prism.md) · [README](./themes/prism/README.md) |
| **[Dossier](./themes/dossier/)** | Legal / contract lifecycle — the *case file*: serif-led porcelain, burgundy + navy, hairline rules, renewals & obligations. Spectral. Daylight + Lamplight. | [Demo](https://prabhuakshay.github.io/my-themes/themes/dossier/) · [Spec](./themes/dossier/dossier.md) · [README](./themes/dossier/README.md) |
| **[Sterling](./themes/sterling/)** | Corporate finance / office of the CFO — the *ledger*: ink-navy binder, gilt accent, statement tables that tie out, favorable/unfavorable variance, the month-end close. Hanken Grotesk. Statement + Ledger. | [Demo](https://prabhuakshay.github.io/my-themes/themes/sterling/) · [Spec](./themes/sterling/sterling.md) · [README](./themes/sterling/README.md) |

> _Thirteen full systems — each a distinct pole for the same enterprise user, and each a complete,
> token-driven, light + dark app demo with its own written spec. More land in their own folders
> under [`themes/`](./themes)._

## Repository layout

```
my-themes/
├── index.html                      # landing page — the live gallery
├── themes/
│   ├── meridian-enterprise/
│   │   ├── index.html              # live, self-contained demo
│   │   ├── meridian-enterprise.md  # full design specification
│   │   └── README.md               # theme overview
│   ├── broadsheet/
│   │   ├── index.html              # live, self-contained demo
│   │   ├── broadsheet.md           # full design specification
│   │   └── README.md               # theme overview
│   ├── frontline/
│   │   ├── index.html              # live, self-contained demo
│   │   ├── frontline.md            # full design specification
│   │   └── README.md               # theme overview
│   ├── vellum/
│   │   ├── index.html              # live, self-contained demo
│   │   ├── vellum.md               # full design specification
│   │   └── README.md               # theme overview
│   └── …                           # cardinal, beacon, foundry, sage, voltaic,
│                                    #   tessera, prism, dossier — same three-file layout
├── CLAUDE.md                       # standards for building new themes
├── PRINCIPALS.md                   # the UI/UX instruction set all themes follow
└── README.md                       # you are here
```

## Using a theme

```bash
git clone https://github.com/prabhuakshay/my-themes.git
cd my-themes

# open any theme's demo directly — no build, no install
open themes/meridian-enterprise/index.html        # macOS
xdg-open themes/meridian-enterprise/index.html    # Linux
```

Each theme's `README.md` has its own quick-start, principles, and theming notes.

## Adding a theme

Each theme is a folder under `themes/<theme-name>/` containing at least an `index.html` demo
and a `README.md`. Add a row to the table above and a card to `index.html`, and it shows up in
the gallery.

## License

[MIT](./LICENSE) — use it, adapt it, ship it.

<div align="center">
<sub>my-themes · by Akshay Prabhu</sub>
</div>
