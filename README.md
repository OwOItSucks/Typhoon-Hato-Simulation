# Typhoon Hato 1713 · 3D Geospatial Hazard Visualisation

An interactive, browser-based simulation of Typhoon Hato (2017) built as a portfolio demo. It combines WebGL-based map rendering, simulated real-time IoT sensor feeds, and spatiotemporal wind-speed forecasting into a single-file engineering dashboard.

**Live demo →** `https://owoitsucks.github.io/Typhoon-Hato-Simulation/`  
*(Open in Chrome or Edge. WebGL must be enabled.)*

---

## What it shows

| Layer | Description |
|---|---|
| **Best-track path** | HKO 6-hour best-track positions (IBTrACS v04r01), colour-coded by intensity category |
| **Wind radius** | Animated storm-radius circle updating at each timestep |
| **IoT sensor feed** | Simulated WebSocket stream from 8 ground stations (HKO, Waglan Island, Cheung Chau, Zhuhai Coastal, etc.) with live wind-speed readings |
| **+6h forecast** | Quadratic Lagrange extrapolation of the next track position, rendered as a dashed predictive line |
| **Time-series chart** | Observed vs. predicted wind speed, updating in sync with playback |
| **System metrics** | FPS, frame time, entity count, tile cache — performance monitoring panel |

---

## Tech stack

- **Leaflet.js** — tile-based 2D/3D map rendering (CARTO Dark basemap)
- **Cesium-style design** — WebGL viewport, coordinate system display (WGS-84 + EPSG:3857)
- **Vanilla JavaScript** — no build tools, no framework dependencies
- **Simulated WebSocket** — `setInterval`-based drop-in for real IoT stream integration
- **SVG charts** — hand-rolled time-series rendering, no charting library

---

## How to run

No server or build step needed. Just open the file:

```bash
# Clone the repo
git clone https://github.com/OwOItSucks/Typhoon-Hato-Simulation.git

# Open directly in browser
open "Typhoon Hato Simulation - Cesium .html"
```

Or download the `.html` file and open it locally. Chrome or Edge recommended — WebGL must be enabled (it is by default in both browsers).

---

## Skills demonstrated

- Web GIS implementation (spatial queries, coordinate systems, GeoJSON data handling)
- Real-time data pipeline simulation (WebSocket architecture, IoT sensor integration pattern)
- Spatiotemporal forecasting (Lagrange extrapolation applied to track prediction)
- Performance monitoring in a live geospatial application
- End-to-end single-file deployment — no dependencies beyond a CDN-loaded Leaflet

---

## Data sources

- Storm track: [IBTrACS v04r01](https://www.ncei.noaa.gov/products/international-best-track-archive) — NOAA National Centers for Environmental Information
- Basemap: © [CARTO](https://carto.com/attributions) · © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors
- Ground station names: [Hong Kong Observatory](https://www.hko.gov.hk)

---

*Built by CHEN Jing Wen, Aria · MSc Geomatics, The Hong Kong Polytechnic University*
