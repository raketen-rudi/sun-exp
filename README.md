# Sun Exposure Checker

Web app that computes the real terrain horizon for any point (neighbouring mountains, earth curvature, refraction) and from it the direct-sun hours for every day of the year: sun paths for solstices/equinox, first/last sun, monthly table, cross-check between two elevation datasets, PNG/PDF export.

- Elevation: [Mapterhorn](https://mapterhorn.com) (national LiDAR where available, Copernicus GLO-30 elsewhere) and Terrain Tiles on AWS (Mapzen/Joerd)
- Map: © OpenStreetMap contributors, OpenTopoMap
- Sun position: NOAA solar position algorithm

Clear-sky potential only: trees, buildings and weather are not included.
Single file app — `index.html`; hosted via GitHub Pages.
