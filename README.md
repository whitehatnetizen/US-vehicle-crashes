# US Vehicle Crashes — Time-Replay Map

Live: https://whitehatnetizen.github.io/US-vehicle-crashes/

Self-contained interactive visualisation of every fatal vehicle crash in the United States from 2000 to 2024 — about 820,000 events — drawn from the NHTSA **Fatality Analysis Reporting System (FARS)** bulk releases.

## Modes

- **Replay** — time-scrubber animation; each crash flashes briefly at its location with marker size by fatality count and colour by alcohol involvement (red = alcohol-impaired driver, amber = otherwise). Trailing 30-day window.
- **Heatmap** — kernel-density of fatal crashes weighted by fatality count.

## Filters

Three filters that combine with AND semantics:

- **alcohol** — at least one driver coded as alcohol-impaired
- **multi-fatal** — crashes with two or more fatalities
- **night** — light condition coded as dark or dark-but-lighted

A live cumulative-fatality counter updates as the scrubber advances and re-labels itself to reflect the active filter combination.

## Data sources

- NHTSA FARS bulk releases: https://www.nhtsa.gov/file-downloads?p=nhtsa/downloads/FARS/
- Basemap: [OpenFreeMap](https://openfreemap.org)

## Tech

deck.gl 9.x for rendering · MapLibre GL JS 4.x for the basemap · all libs inlined in `index.html`, no build needed at deploy time. The full source (Python build pipeline + parquet ingest) lives in a separate repo.

## License

MIT. FARS data is public domain (US federal government work). Basemap tiles © OpenFreeMap and OpenStreetMap contributors.
