# Eritrea Administrative Divisions / ኤርትራ



## Overview

| Item | Details |
|------|---------|
| Region | 6 |
| Sub-region | 58 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-19 |
| Website | [openadmindata.org/er](https://openadmindata.org/er/) |
| API | [openadmindata.org/api/er](https://openadmindata.org/api/er/) |
| National Anthem | [🎵 Listen & Download Eritrea National Anthem MP3](https://onlygames.me/national-anthems/er/) |

## Browse by Region

| # | Region | Sub-regions | Link |
|---|----|----|------|
| 1 | Anseba | 11 | [Browse](divisions/anseba-er4/) |
| 2 | Debub | 12 | [Browse](divisions/debub-er6/) |
| 3 | Debubawi Keih Bahri | 4 | [Browse](divisions/debubawi-keih-bahri-er1/) |
| 4 | Gash Barka | 14 | [Browse](divisions/gash-barka-er5/) |
| 5 | Maekel | 7 | [Browse](divisions/maekel-er2/) |
| 6 | Semienawi Keih Bahri | 10 | [Browse](divisions/semienawi-keih-bahri-er3/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 6 region records |
| [all-subregion.json](data/all-subregion.json) | JSON | All 58 sub-region records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['subregion']} sub-regions")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=sub-region |
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
divisions/{region-slug}/
```

Sub-regions are listed inline in each region's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Eritrea Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/eritrea-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
