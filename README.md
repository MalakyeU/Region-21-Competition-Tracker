# Region 21 Competition Tracker 🧗

An interactive map of the **USA Climbing Youth Region 21** (Northern California & Northern Nevada) 2026–2027 competition season.

**Live site:** `https://<your-username>.github.io/region-21-tracker/` (after enabling GitHub Pages — see below)

## Features

- **Season timeline**: every Qualification Event plus Regional and Divisional Championships, color-coded from green (soonest) to red (farthest out). Events that have already happened (or are happening today) are grayed out.
- **Hover cards**: hover a pin for the date, gym, address, distance from home, registration info, and a link to the official USAC info sheet. Events without a posted sheet link to the [Region 21 page](https://usaclimbing.org/compete/region-21/).
- **Filters**: Boulder vs. Lead/TR, max distance from home, how far ahead in time, and a toggle for past events.
- **USAC region borders**: vector outlines of Region 21 (plus R31/R32 split) built from US county shapes.
- **Potential host gyms**: gyms in Region 21 that aren't hosting this season, shown with a separate climbing-hold icon.
- **Home pin** in Capitola, CA (distances are measured from here).

## Updating the data

Everything lives in `index.html`:

| What | Where |
| --- | --- |
| Events, dates, info-sheet links | `eventsData` array |
| Home location | `HOME` constant |
| Potential host gyms | `prospectGyms` array |
| Nevada north/south split | `R31_NV` set |

Info sheets are usually posted 2–3 weeks before each event on the
[Region 21 schedule](https://usaclimbing.org/compete/region-21/). Paste the doc link
(the `https://docs.google.com/document/d/e/.../pub` URL, **not** the `google.com/url?q=` redirect) into that event's `infoUrl`.

## Publishing on GitHub Pages

1. Create a new public repository on GitHub named `region-21-tracker`.
2. Upload `index.html`, `README.md`, and `.nojekyll` (drag-and-drop on the repo page works), or:
   ```bash
   git init
   git add .
   git commit -m "Region 21 competition tracker"
   git branch -M main
   git remote add origin https://github.com/<your-username>/region-21-tracker.git
   git push -u origin main
   ```
3. In the repo go to **Settings → Pages**, set **Source** to *Deploy from a branch*, branch `main`, folder `/ (root)`, and save.
4. After a minute the site is live at `https://<your-username>.github.io/region-21-tracker/`.

## Data sources

- Event schedule & info sheets: [USA Climbing Region 21](https://usaclimbing.org/compete/region-21/)
- Region definitions: USA Climbing Region 21 / 22 / 31 / 32 pages
- Borders: [us-atlas](https://github.com/topojson/us-atlas) (US Census Bureau cartographic boundaries)
- Basemap: Esri World Dark Gray Canvas · Map library: [Leaflet](https://leafletjs.com/)

*Unofficial fan-made tool — not affiliated with USA Climbing. Always confirm details on the official info sheet.*
