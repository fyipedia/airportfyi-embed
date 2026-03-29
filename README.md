# airportfyi-embed

[![npm](https://img.shields.io/npm/v/airportfyi-embed)](https://www.npmjs.com/package/airportfyi-embed)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-blue)](https://www.typescriptlang.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/airportfyi-embed)

Embed **AirportFYI** widgets — airports, glossary terms, interactive tools, and inline elements — on any website. **6 widget types**, zero dependencies, Shadow DOM style isolation, 4 built-in themes (light, dark, sepia, auto), 2 styles (modern, clean), and live data from the [AirportFYI](https://airportfyi.com) database.

Every widget includes a "Powered by AirportFYI" backlink directing readers to the full reference.

> **Try the interactive widget builder at [widget.airportfyi.com](https://widget.airportfyi.com)**

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-airportfyi="entity" data-slug="airports" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/airportfyi-embed@1/dist/embed.min.js"></script>
```

That's it. The widget fetches data from the AirportFYI API and renders with full style isolation.

## Widget Types

| Type | Usage | Description |
|------|-------|-------------|
| `entity` | `<div data-airportfyi="entity" data-slug="..."></div>` | Entity detail card — airport, airline, aircraft, or station |
| `glossary` | `<div data-airportfyi="glossary" data-slug="..."></div>` | Glossary term definition with cross-references |
| `faq` | `<div data-airportfyi="faq" data-slug="..."></div>` | FAQ accordion with expand/collapse |
| `search` | `<div data-airportfyi="search" data-slug="..."></div>` | Search box linking to the full database |
| `compare` | `<div data-airportfyi="compare" data-slug="..."></div>` | Side-by-side entity comparison |
| `type-badge` | `<div data-airportfyi="type-badge" data-slug="..."></div>` | Inline airport type badge (e.g. "International", "Regional") |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-airportfyi` | entity, glossary, faq, search, compare, [tools] | required | Widget type |
| `data-slug` | e.g. "airports" | — | Entity slug from the AirportFYI database |
| `data-theme` | light, dark, sepia, auto | light | Visual theme (`auto` follows OS preference) |
| `data-style` | modern, clean | modern | Widget design style |
| `data-size` | default, compact, large | default | Widget size |
| `data-placeholder` | any string | "Search Airports..." | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-airportfyi="entity" data-slug="airports" data-theme="light"></div>

<!-- Dark -->
<div data-airportfyi="entity" data-slug="airports" data-theme="dark"></div>

<!-- Sepia -->
<div data-airportfyi="entity" data-slug="airports" data-theme="sepia"></div>

<!-- Auto — follows OS dark/light preference -->
<div data-airportfyi="entity" data-slug="airports" data-theme="auto"></div>
```

## Styles

```html
<!-- Modern (default) — clean lines, rounded corners, accent gradients -->
<div data-airportfyi="entity" data-slug="airports" data-style="modern"></div>

<!-- Clean — minimal borders, utility-focused, data-first aesthetic -->
<div data-airportfyi="entity" data-slug="airports" data-style="clean"></div>
```

## Web Components (Custom Elements)

As an alternative to `data-*` attributes, you can use native HTML custom elements:

```html
<!-- Custom element form -->
<airportfyi-entity slug="airports" theme="light"></airportfyi-entity>
<airportfyi-compare slugs="airports,other-slug"></airportfyi-compare>
<airportfyi-search placeholder="Search Airports..."></airportfyi-search>

<script src="https://cdn.jsdelivr.net/npm/airportfyi-embed@1/dist/embed.min.js"></script>
```

Use `style-variant` (not `style`) to avoid conflicts with the HTML reserved `style` attribute.

## Examples

### Entity Card

```html
<div data-airportfyi="entity" data-slug="airports" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/airportfyi-embed@1/dist/embed.min.js"></script>
```

### Side-by-Side Comparison

```html
<div data-airportfyi="compare" data-slugs="airports,other-slug"></div>
<script src="https://cdn.jsdelivr.net/npm/airportfyi-embed@1/dist/embed.min.js"></script>
```

### Search Box

```html
<div data-airportfyi="search" data-placeholder="Search Airports..."></div>
<script src="https://cdn.jsdelivr.net/npm/airportfyi-embed@1/dist/embed.min.js"></script>
```

### Glossary Term

```html
<div data-airportfyi="glossary" data-slug="example-term" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/airportfyi-embed@1/dist/embed.min.js"></script>
```

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/airportfyi-embed@1/dist/embed.min.js"></script>
```

### Specific version (production stability)

```html
<script src="https://cdn.jsdelivr.net/npm/airportfyi-embed@1.0.0/dist/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install airportfyi-embed
```

```javascript
import 'airportfyi-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **2 styles**: Modern (accent gradients) and Clean (minimal, data-first)
- **4 themes**: Light, Dark, Sepia, Auto (OS preference detection)
- **CORS**: AirportFYI API has CORS enabled for all origins
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **IntersectionObserver**: Lazy loading — widgets only fetch when entering viewport (200px margin)
- **Rich Snippets**: DefinedTerm JSON-LD injected for glossary widgets
- **Bundle size**: Tree-shaken per site — only includes tools available on AirportFYI

## Learn More About Airports

Visit [airportfyi.com](https://airportfyi.com) — AirportFYI is a comprehensive airports reference with interactive tools, guides, and developer resources.

- **API docs**: [airportfyi.com/developers/](https://airportfyi.com/developers/)
- **Widget builder**: [widget.airportfyi.com](https://widget.airportfyi.com)
- **npm package**: [npmjs.com/package/airportfyi-embed](https://www.npmjs.com/package/airportfyi-embed)
- **GitHub**: [github.com/fyipedia/airportfyi-embed](https://github.com/fyipedia/airportfyi-embed)

## Transport FYI Family

Part of [FYIPedia](https://fyipedia.com) — open-source developer tools ecosystem. Transport FYI covers airports, airlines, aircraft, and railway networks. Hub: [transitfyi.com](https://transitfyi.com).

| Site | Domain | Focus | Package |
|------|--------|-------|---------|
| **AirportFYI** | [airportfyi.com](https://airportfyi.com) | 71,631 airports, IATA/ICAO codes, runways, routes | **[npm](https://www.npmjs.com/package/airportfyi-embed)** |
| AirlineFYI | [airlinefyi.com](https://airlinefyi.com) | 6,161 airlines, fleets, alliances, routes | [npm](https://www.npmjs.com/package/airlinefyi-embed) |
| PlaneFYI | [planefyi.com](https://planefyi.com) | 81 aircraft types, specs, manufacturers, fleet data | [npm](https://www.npmjs.com/package/planefyi-embed) |
| TrainFYI | [trainfyi.com](https://trainfyi.com) | 51,425 stations, operators, route pairs | [npm](https://www.npmjs.com/package/trainfyi-embed) |

## FYIPedia Developer Tools

| Package | PyPI | npm | Description |
|---------|------|-----|-------------|
| colorfyi | [PyPI](https://pypi.org/project/colorfyi/) | [npm](https://www.npmjs.com/package/@fyipedia/colorfyi) | Color conversion, WCAG contrast, harmonies — [colorfyi.com](https://colorfyi.com) |
| emojifyi | [PyPI](https://pypi.org/project/emojifyi/) | [npm](https://www.npmjs.com/package/emojifyi) | Emoji encoding & metadata for 3,953 emojis — [emojifyi.com](https://emojifyi.com) |
| unitfyi | [PyPI](https://pypi.org/project/unitfyi/) | [npm](https://www.npmjs.com/package/unitfyi) | Unit conversion, 220 units — [unitfyi.com](https://unitfyi.com) |
| timefyi | [PyPI](https://pypi.org/project/timefyi/) | [npm](https://www.npmjs.com/package/timefyi) | Timezone ops & business hours — [timefyi.com](https://timefyi.com) |
| holidayfyi | [PyPI](https://pypi.org/project/holidayfyi/) | [npm](https://www.npmjs.com/package/holidayfyi) | Holiday dates & Easter calculation — [holidayfyi.com](https://holidayfyi.com) |
| namefyi | [PyPI](https://pypi.org/project/namefyi/) | [npm](https://www.npmjs.com/package/namefyi) | Korean romanization & Five Elements — [namefyi.com](https://namefyi.com) |
| fyipedia | [PyPI](https://pypi.org/project/fyipedia/) | — | Unified CLI for all FYI tools — [fyipedia.com](https://fyipedia.com) |

## Embed Widget

Embed [AirportFYI](https://airportfyi.com) widgets on any website with [airportfyi-embed](https://widget.airportfyi.com):

```html
<script src="https://cdn.jsdelivr.net/npm/airportfyi-embed@1/dist/embed.min.js"></script>
<div data-airportfyi="entity" data-slug="example"></div>
```

Zero dependencies · Shadow DOM · 4 themes (light/dark/sepia/auto) · [Widget docs](https://widget.airportfyi.com)

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [FYIPedia](https://fyipedia.com).
