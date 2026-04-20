# Strategic Fusion Dashboard (SFD) v2.4

A web-based **Multi-Source Intelligence Fusion Dashboard** for ingesting, visualizing, and analyzing OSINT, HUMINT, and IMINT data on a unified geospatial interface.

## Live Demo
> After deploying: `https://<your-username>.github.io/sfd-dashboard/`

---

## Features

| Feature | Description |
|---|---|
| **Map View** | Interactive terrain map with color-coded intelligence nodes |
| **Hover Pop-up** | Hover any node to see metadata, coordinates, confidence, and imagery info |
| **Data Ingestion** | Ingest OSINT (JSON), HUMINT (CSV), and IMINT (JPEG/PNG) in real time |
| **Source Filtering** | Toggle OSINT / HUMINT / IMINT layers on/off independently |
| **Intel Table** | Sortable record view with confidence bar color grading |
| **Logic View** | Built-in explanation of all system logic for onboarding |
| **Activity Feed** | Live log of all ingestion events with UTC timestamps |

---

## Logic Overview

1. **Validation** — lat/lon range checks, required fields, confidence bounds
2. **Node Mapping** — lat/lon → pixel position on terrain canvas
3. **Hover-and-View** — pop-up modal with boundary overflow correction
4. **Layer Filtering** — per-source visibility toggle, real-time re-render
5. **Confidence Grading** — green ≥80%, amber 60–79%, red <60%
6. **Duplicate Detection** — 0.01° tolerance check before node insertion
7. **Session Logging** — activity feed + bulk log per session

---

## Deploy to GitHub Pages (step by step)

### 1. Create a GitHub repository
- Go to [github.com](https://github.com) and sign in
- Click **New repository**
- Name it `sfd-dashboard` (or any name you like)
- Set it to **Public**
- Click **Create repository**

### 2. Upload the file
- In your new repo, click **Add file → Upload files**
- Upload `index.html` and `README.md`
- Commit with message: `Initial deploy`

### 3. Enable GitHub Pages
- Go to **Settings → Pages**
- Under **Source**, select `main` branch and `/ (root)` folder
- Click **Save**
- Wait ~60 seconds, then visit: `https://<your-username>.github.io/sfd-dashboard/`

---

## Local Development

No build tools needed. Just open `index.html` in any browser:

```bash
# Option 1 — open directly
open index.html

# Option 2 — serve locally
npx serve .
# or
python3 -m http.server 8080
```

---

## Data Ingestion Formats

**OSINT (JSON)**
```json
{"lat": 33.8, "lon": -118.2, "label": "Node X", "conf": 85}
```

**HUMINT (CSV)**
```
33.5, -117.8, Agent Report, 72
```

**IMINT**
- Enter coordinates in the same CSV format, or drag-and-drop a JPG/PNG file

---

## Tech Stack
- Pure HTML / CSS / JavaScript — zero dependencies
- No build step, no framework
- Fully deployable as a single `index.html` file

---

## Problem Statement
Built to address **Problem Statement 1: Multi-Source Intelligence Fusion Dashboard** — eliminating fragmented data silos across MongoDB/S3 (OSINT), manual CSV/JSON (HUMINT), and image formats (IMINT) by providing a unified, interactive geospatial interface.
