# Math Simulations Hub

A central landing page that links to all your math simulation tools — each hosted as its own GitHub Pages site.

---

## How it works

- **`index.html`** — the hub page. It reads `simulations.json` and renders a button/card for each simulation.
- **`simulations.json`** — your registry. Adding a new simulation = adding one entry here.

---

## Step-by-step setup guide

### Step 1 — Create your hub repository

1. Go to [github.com](https://github.com) and click **New repository**
2. Name it exactly: `yourusername.github.io`
   - Replace `yourusername` with your actual GitHub username
   - This special name tells GitHub to host it as your main Pages site
3. Set it to **Public**
4. Click **Create repository**

### Step 2 — Upload the hub files

1. In your new repo, click **Add file → Upload files**
2. Upload both `index.html` and `simulations.json` from this folder
3. Click **Commit changes**

### Step 3 — Enable GitHub Pages

1. In your repo, go to **Settings → Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose branch: `main`, folder: `/ (root)`
4. Click **Save**
5. Wait ~1 minute, then visit: `https://yourusername.github.io`

Your hub is live! ✓

---

## Adding a simulation

Each simulation lives in its own GitHub repo. Here's how to set one up:

### Step 4 — Create a simulation repo

1. Create a new GitHub repo, e.g. `fourier-series`
2. Add your simulation's `index.html` (and any other files) to it
3. Enable GitHub Pages on it the same way as Step 3
4. Your simulation is now live at: `https://yourusername.github.io/fourier-series`

### Step 5 — Register it in the hub

Open `simulations.json` in your hub repo and add an entry:

```json
[
  {
    "title": "Fourier Series",
    "url": "https://yourusername.github.io/fourier-series",
    "description": "Visualize wave decomposition into harmonics",
    "tags": ["analysis", "waves"]
  }
]
```

That's it — the hub page automatically shows the new card.

To edit `simulations.json` directly on GitHub:
1. Open `simulations.json` in your hub repo
2. Click the **pencil icon** (Edit this file)
3. Add your new entry inside the `[...]` array
4. Click **Commit changes**

---

## simulations.json format

Each entry supports these fields:

| Field         | Required | Description                              |
|---------------|----------|------------------------------------------|
| `title`       | ✓        | Button label (use the repo/page name)    |
| `url`         | ✓        | Full URL to the simulation               |
| `description` | optional | Short subtitle shown under the title     |
| `tags`        | optional | Array of strings — enables tag filtering |

---

## Workflow summary (once everything is set up)

Every time you build a new simulation:

1. Create a new GitHub repo for it
2. Build your simulation, push the files
3. Enable GitHub Pages on the repo
4. Add one entry to `simulations.json` in the hub repo
5. Done — it appears on the hub automatically

---

## Tips

- **Repo naming**: use lowercase with hyphens (e.g. `double-pendulum`). This becomes the URL slug.
- **Local testing**: open `index.html` via a local server (e.g. `python3 -m http.server`) not by double-clicking — `fetch()` needs a server to work.
- **Tags**: use consistent tag names across entries so the filter buttons group them well.
