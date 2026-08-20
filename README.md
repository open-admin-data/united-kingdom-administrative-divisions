# United Kingdom Administrative Divisions / United Kingdom



## Overview

| Item | Details |
|------|---------|
| Nation | 4 |
| County/Council | 361 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/gb](https://openadmindata.org/gb/) |
| API | [openadmindata.org/api/gb](https://openadmindata.org/api/gb/) |
| Flag | [PNG](https://onlygames.me/flags-png/gb/) · [SVG](https://onlygames.me/flags-svg/gb/) · [PDF](https://onlygames.me/flags-pdf/gb/) |
| National Anthem | [🎵 Listen & Download United Kingdom National Anthem MP3](https://onlygames.me/national-anthems/gb/) |

## Browse by Nation

| # | Nation | County/Councils | Link |
|---|----|----|------|
| 1 | England | 262 | [Browse](divisions/england-gb01/) |
| 2 | Scotland | 34 | [Browse](divisions/scotland-gb02/) |
| 3 | Northern Ireland | 11 | [Browse](divisions/northern-ireland-gb03/) |
| 4 | Wales | 54 | [Browse](divisions/wales-gb04/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-nation.json](data/all-nation.json) | JSON | All 4 nation records |
| [all-county.json](data/all-county.json) | JSON | All 361 county/council records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-nation.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['county']} county/councils")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-nation.json", "utf-8"));
console.log(`Total: ${data.length} nations`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=nation, 2=county/council |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{nation-slug}/
```

County/Councils are listed inline in each nation's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-nation links
- [Per-nation data](docs/llms-full/) — Full data by nation

## Citation

```
United Kingdom Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/united-kingdom-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
