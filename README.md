# ☀️ Sun Exposure Checker

**Live app:** https://raketen-rudi.github.io/sun-exp/

How many hours of direct sun does a house, a building plot or a mountain hut really get — in midwinter and in midsummer? Flat-horizon sunrise/sunset tables are useless in the mountains, because neighbouring peaks block the sun for hours. This app computes the **real terrain horizon** for any point and from it the **direct-sun hours for every day of the year**.

## Features

- **Pick a point:** tap the map, paste coordinates (decimal, degrees-minutes-seconds or a Google Maps link), search a place name, or use 📍 your current location
- **Terrain horizon:** 720 rays (every 0.5°) out to 60 km, with earth curvature and atmospheric refraction; the horizon outline is drawn on the map
- **Sun-path chart:** sun paths from 21 June through the equinox to 21 December as colour bands, the selected day with hour marks, and the times of first/last direct sun
- **Key figures:** direct sun on 21 Dec / 20 Mar / 21 Jun, winter and summer averages, potential sun hours per year, days without any direct sun
- **Year chart and monthly table:** sun hours per day vs. a flat horizon, first and last sun per month
- **Cross-check:** recompute with a second elevation dataset and see how much the result depends on the data
- **Compare locations:** save several candidates side by side (stored in your browser), copy as a table
- **Export:** one-page A4 report as PNG or PDF; share a link that opens the app directly at a location
- **Installable:** works as a home-screen app on iPhone/Android (Safari → Share → Add to Home Screen)

## How it works

1. Elevation tiles around the point are loaded in the browser — finest resolution near the point, coarser further away.
2. For each direction, the terrain profile is scanned and the highest elevation angle (corrected for earth curvature, refraction coefficient 0.13) becomes the horizon.
3. The sun position is computed every 2 minutes for the whole year (NOAA solar position algorithm incl. refraction). The sun counts as visible when its centre is above the terrain horizon.

Everything runs in the browser; there is no server and no data is collected.

## Limits

- **Clear-sky potential only** — clouds, fog and haze are not included.
- **Bare-earth terrain** — trees and buildings are *not* in the elevation models. A forest edge or a neighbouring house can remove low winter sun completely. Check on site.
- **Point elevation** can be off on steep slopes or ridges; use *Elevation override* if you know the real elevation.
- Accuracy depends on the elevation data: excellent where national LiDAR exists (e.g. Austria, Germany, Switzerland), coarser (~30 m) elsewhere. Use the cross-check.

## Data sources & attribution

| What | Source | License / terms |
|---|---|---|
| Elevation (default) | [Mapterhorn](https://mapterhorn.com) — national LiDAR terrain models, Copernicus GLO-30 elsewhere | see [Mapterhorn attribution](https://mapterhorn.com/attribution) |
| Elevation (alternative) | [Terrain Tiles on AWS](https://registry.opendata.aws/terrain-tiles) (Mapzen/Tilezen Joerd) | see [Joerd attribution](https://github.com/tilezen/joerd/blob/master/docs/attribution.md) |
| Map | © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors, [OpenTopoMap](https://opentopomap.org) (CC-BY-SA) | ODbL / CC-BY-SA |
| Satellite layer | Esri World Imagery | Esri terms |
| Place search | [Nominatim](https://nominatim.org) (OpenStreetMap) | [usage policy](https://operations.osmfoundation.org/policies/nominatim/) |
| Libraries | [Leaflet](https://leafletjs.com), [jsPDF](https://github.com/parallax/jsPDF) | BSD-2 / MIT |

Intended for personal, low-volume use. The free map and search services above have fair-use policies; heavy use would need own tile/search providers.

## Repository

| File | Purpose |
|---|---|
| `index.html` | the complete app (single file: HTML, CSS, JavaScript) |
| `manifest.webmanifest`, `icon-*.png` | home-screen install |
| `.nojekyll` | serve files as-is on GitHub Pages |
| `CHANGELOG.md` | version history |

**Updating:** edit `index.html` and push to `main` — GitHub Pages republishes within about a minute.

## License

Code: [MIT](LICENSE). Map and elevation data remain under their providers' licenses.
