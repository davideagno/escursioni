# 🏔️ Escursioni — GPX Hiking Map

A beautiful, interactive hiking trail map built with **Leaflet** and **Stadia Alidade Satellite** tiles. Designed to run as a **GitHub Pages** website.

![Screenshot](https://img.shields.io/badge/map-Stadia_Satellite-blue) ![License](https://img.shields.io/badge/license-MIT-green)

## 🚀 Deploy to GitHub Pages

1. **Create a GitHub repository** (e.g., `escursioni`)
2. **Push this folder** to the repo:
   ```bash
   cd escursioni
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/escursioni.git
   git push -u origin main
   ```
3. **Enable GitHub Pages**: go to repo **Settings → Pages → Source** and select `main` / `/ (root)`
4. Your map will be live at: `https://YOUR_USERNAME.github.io/escursioni/`

## ➕ Adding New Trails

### Step 1 — Drop your GPX file

Put your `.gpx` file in the `gpx/` folder:

```
gpx/
├── example-trail.gpx
├── monte-grappa.gpx      ← new!
└── alta-via-1.gpx         ← new!
```

### Step 2 — Register it in `index.html`

Open `index.html` and find the `TRAILS` array near the top of the `<script>` section:

```javascript
const TRAILS = [
  { file: "gpx/example-trail.gpx", name: "", color: "" },
  // ← Add more trails here
];
```

Add a new entry:

```javascript
const TRAILS = [
  { file: "gpx/example-trail.gpx", name: "", color: "" },
  { file: "gpx/monte-grappa.gpx", name: "Monte Grappa", color: "#22cc88" },
  { file: "gpx/alta-via-1.gpx", name: "Alta Via 1", color: "#3388ff" },
];
```

### Options

| Field   | Required | Description                                      |
|---------|----------|--------------------------------------------------|
| `file`  | ✅       | Path to the GPX file (relative to `index.html`)  |
| `name`  | ❌       | Display name. Display name. Falls back to GPX track name         |
| `color` | ❌       | Hex color for the trail. Auto-assigned if blank    |

### Step 3 — Commit & push

```bash
git add .
git commit -m "Add Monte Grappa trail"
git push
```

GitHub Pages will update automatically within a minute.

## ✨ Features

- **Stadia Alidade Satellite** base map (high-res imagery)
- Sidebar with trail list, search, distance, and elevation stats
- Click a trail in the sidebar or on the map to zoom + highlight
- Elevation profile chart (canvas-based)
- Fully responsive — works on mobile
- Dark theme with polished UI
- No build step — pure HTML/CSS/JS

## 🔑 Stadia Maps API Key

For **localhost** development, no API key is needed. For production on GitHub Pages, you may need a (free) Stadia Maps API key:

1. Sign up at [stadiamaps.com](https://stadiamaps.com)
2. Add your GitHub Pages domain under **Authentication Configuration**
3. Alternatively, append `?api_key=YOUR_KEY` to the tile URL in `index.html`

## 📁 Project Structure

```
escursioni/
├── index.html          ← Main app (everything in one file)
├── gpx/                ← Your GPX track files
│   └── example-trail.gpx
└── README.md
```

## License

MIT
