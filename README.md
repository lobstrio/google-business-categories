# Google Business Categories

The complete list of **4,053 Google Business Profile categories** (Google Maps listing categories), each with its **GCID** — Google's own internal category identifier.

Last updated: **September 2026**

Google does not publish a downloadable category list. The per-country CSV files it used to publish were retired deliberately, and the official Business Profile API requires OAuth plus an approved access application. So every public list is a compilation — this one included. The method used to build it is documented below.

## Files

| File | Contents |
| --- | --- |
| [`data/google-business-categories.txt`](data/google-business-categories.txt) | One category name per line |
| [`data/google-business-categories.json`](data/google-business-categories.json) | Flat JSON array of category names |
| [`data/google-business-categories.csv`](data/google-business-categories.csv) | `gcid, category, bucket` |
| [`data/google-business-categories.full.json`](data/google-business-categories.full.json) | Full records: gcid, name, bucket, US availability, locale count, name variants |
| [`data/google-business-categories.by-bucket.json`](data/google-business-categories.by-bucket.json) | Categories grouped by the 25 industry buckets |
| [`data/gcid-map.json`](data/gcid-map.json) | `gcid` → category name lookup |

Start with `full.json` if you're doing anything non-trivial. It's the only file that carries the name variants.

## Why GCIDs matter

**A category's name is not its identity. Its GCID is.**

The same category has different names in different countries:

| GCID | Names |
| --- | --- |
| `gcid:atm` | "ATM" (US), "Cashpoint" (UK) |
| `gcid:moving_company` | "Removals company" (45 countries), "Moving company" (1) |
| `gcid:bicycle_store` | "Bicycle store" (US), "Bicycle shop" (UK) |

And it cuts the other way: `gcid:swimming_basin` and `gcid:swimming_pool` are two *different* categories that both display as "Swimming pool".

**1,196 of the 4,053 categories carry more than one display name** across locales.

This is why name-based category lists disagree with each other. Comparing 49 European countries by name yields 4,923 categories with 879 apparently missing from the US. Comparing the same data by GCID yields 4,051, with 7 missing. Same data, off by a factor of 125.

## The taxonomy is near-universal

Checked across 70 countries:

| Measure | Value |
| --- | --- |
| Unique categories, 49 European countries | 4,051 |
| Present in **all** 49 European countries | 4,007 |
| In Europe but not the US | 7 |
| In the US but in no European country | 0 |
| Global union, 70 locales | 4,053 |

You do not need a country-specific category list. There is one taxonomy; the wording changes.

## How this list was built

- Cross-referenced every public dataset available online. The two most current agreed with each other at **99.88%**
- Pulled the taxonomy for **70 countries** to catch categories only valid in another market
- Compared against a **2022 snapshot** to separate genuinely retired categories from ones that were never valid
- Kept each category's **GCID** so every entry is verifiable
- Removed **643** entries that are not valid Google Business Profile categories, including 44 that belong to the Google **Places API** — a different taxonomy describing points of interest and geography (`postal code`, `intersection`, `island`, `natural feature`), not businesses
- Added **413** valid categories that were missing from previously circulating lists

## Industry buckets

All 4,053 categories are grouped into 25 industry buckets, with no catch-all "Other" group. See `by-bucket.json`.

## Notes

- Category names here are US English. Use `name_variants` in `full.json` for other locales.
- Google adds and retires categories continuously. 238 were retired between 2022 and 2026.
- GCIDs are stable across countries and languages; display names are not.

## Usage

Free to use. If it saved you time, a link back is appreciated.

Full write-up: [The Complete Google Business Categories List](https://www.lobstr.io/blog/google-business-categories)

Built by [lobstr.io](https://lobstr.io) — no-code cloud scraping platform with 50+ ready-made scrapers.
