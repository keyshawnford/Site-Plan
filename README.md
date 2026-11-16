# Site Yield Planner

A single-page tool for testing how many lots and housing units fit on a parcel under a set of zoning standards.

## What it does

- **Parcel input:** pick a preset shape, drag corners, type bearings and distances, trace an uploaded site plan image, or import GeoJSON, ArcGIS JSON or DXF boundaries. It also builds Tulare County ArcGIS parcel queries by APN or by latitude and longitude.
- **Zoning presets:** Visalia R-1-5 (with an optional small-lot mode), R-1-12.5, R-1-20, R-M-2 and R-M-3, or custom values for setbacks, height, stories, density, coverage, FAR, open space and parking.
- **Layout engine:** generates a loop street, perimeter lots, interior blocks with back-to-back rows, and setback-compliant building footprints for up to three lot types mixed by share.
- **Results:** units, lots, gross density, coverage, FAR, street and open-space shares, required parking, and a pass or fail result for each zoning check.
- **Maximize units:** tries combinations of street angle, lot depth and row offset, and keeps the layout with the most units that passes the most checks.
- **Exports:** the plan as SVG or PNG, the lot table as CSV, and the full scenario as JSON for the clipboard.

The zoning presets are a planning aid only. Check every number against the adopted municipal code and the City's engineering standards.

## Running it

It's a static page with no build step. Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000/
```

## Built with

- Vanilla HTML, CSS and JavaScript
- [Clipper](https://sourceforge.net/projects/jsclipper/) (`vendor/clipper.js`, clipper-lib 6.4.2, Boost Software License 1.0) for polygon offsetting and boolean operations
