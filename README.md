<div align="center">

# my-themes

### A gallery of design systems & UI themes.

Self-contained, zero-build themes — each with a full design spec and a live, in-browser demo.

[**▶ Browse the live gallery**](https://prabhuakshay.github.io/my-themes/)

![Themes](https://img.shields.io/badge/themes-1-161616)
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
| **[Meridian Enterprise](./themes/meridian-enterprise/)** | Calm, governance-grade B2B design system — Carbon-grade tokens, 2px grid, sharp 1px borders, light + dark. | [Demo](https://prabhuakshay.github.io/my-themes/themes/meridian-enterprise/) · [Spec](./themes/meridian-enterprise/meridian-enterprise.md) · [README](./themes/meridian-enterprise/README.md) |

> _More themes coming — each lands in its own folder under [`themes/`](./themes)._

## Repository layout

```
my-themes/
├── index.html                      # landing page — the live gallery
├── themes/
│   └── meridian-enterprise/
│       ├── index.html              # live, self-contained demo
│       ├── meridian-enterprise.md  # full design specification
│       └── README.md               # theme overview
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
