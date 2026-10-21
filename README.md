# State of AI World - open data

Every significant AI company, what it is worth, and who funds, supplies,
hosts and competes with whom. Every valuation carries a source, a
confidence grade and an as-of date. Relationships carry a source URL where
one is cited; those from the August 2026 starting set are still being
sourced and have an empty `url`. Updated daily.

This repository is a read-only mirror of the data behind
[stateofai.world](https://stateofai.world). The map, a page per company and
the change history live there; this repository holds the files, copied here
automatically after each data update.

## Files

| File | What it holds |
|---|---|
| `entities.csv` | One row per company or division: valuation, confidence, as-of date, primary source, page URL |
| `relations.csv` | One row per relationship: type, how it reads, confidence, source URL, as-of date where recorded |
| `entities.json` | Full company records: every source, notes, ticker |
| `relations.json` | Full relationship records |
| `history.json` | Daily valuation snapshots for every company since 2026-07-27 |
| `removed.json` | Companies removed from the map, with the date and the reason |

Field names are stable: new fields may be added; existing ones are not renamed
or removed without notice on [stateofai.world/open-data](https://stateofai.world/open-data).

## How to read it

- **valuation** is in millions of US dollars. For a listed company it is the
  market capitalisation, refreshed every weekday from the market price; for a
  private company it is the latest dated mark from a named round or report.
- **confidence** is `verified` (market price, or a named round with a dated
  primary report), `reported` (secondary source) or `unsourced`.
- **as_of** is the date of the fact, not the date it was checked.
- Divisions (Google DeepMind, AWS Bedrock and so on) carry no valuation: their
  value sits in the parent company.
- **Growth over time:** summing `history.json` per day gives the total tracked,
  which also rises whenever a company is added to the map. For like-for-like
  growth, compare each day only over the companies present on that day and the
  day before, and chain the daily moves. The site's
  [Trend page](https://stateofai.world/trend) does exactly this.

Full sourcing rules: [methodology](https://stateofai.world/methodology).

## Licence and credit

[CC BY 4.0](LICENSE). Use it for anything, including commercially, with credit:

> Source: State of AI World (stateofai.world), as of YYYY-MM-DD

When you cite one company, link its page, for example
`https://stateofai.world/c/anthropic`. A citation file is in `CITATION.cff`
(GitHub shows it as "Cite this repository").

## Corrections

Found a wrong number or a missing relationship? Open an issue with a source.
Corrections land on the site first and reach this mirror with the next update.

Maintained by Han Liu.
