# Google Business Categories

All **4,053 Google Business Profile categories**, each with its **GCID** (Google's own category identifier), its industry group, and how many businesses list it.

Last updated: **12 November 2026**

## Files

| File | Contents |
| --- | --- |
| [`data/google-business-categories.csv`](data/google-business-categories.csv) | One row per category |
| [`data/google-business-categories.json`](data/google-business-categories.json) | The same rows, as JSON |

Both have the same fields:

| Field | Meaning |
| --- | --- |
| `gcid` | Google's identifier, stable across countries and languages, e.g. `gcid:lawyer` |
| `category` / `name` | The name Google Maps shows in US English, e.g. `Attorney` |
| `group` | One of 25 industry groups |
| `in_us` | Available in the United States |
| `us_businesses` | US businesses that list the category, primary or secondary |
| `world_businesses` | Businesses worldwide that list it |
| `other_names` | Names other lists use, e.g. `Lawyer` for `gcid:lawyer` |

Rows are sorted by category name. 30 recent categories have no count yet.

## Sources

- Business counts: [SphereScout](https://www.spherescout.io), 12 November 2026.
- Names: checked against Google's own category picker in US English, 12 November 2026.

Method, analysis and a searchable version: [Google Business Categories List](https://www.lobstr.io/blog/google-business-categories). The same data as a [Google Sheet](https://docs.google.com/spreadsheets/d/1QahOENYdKyBjBloCoZHLrXe1BtoK0fARfx1k5z6FThE/edit?usp=sharing).

## Usage

Free to use, commercial use included, under [CC BY 4.0](LICENSE): credit lobstr.io with a link to
https://www.lobstr.io/blog/google-business-categories.

Built by [lobstr.io](https://www.lobstr.io).
