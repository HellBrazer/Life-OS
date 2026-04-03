# Life OS 🧠

A personal life tracking dashboard built as a single HTML file. Track your **finances**, **health**, **career**, and **goals** — all in one place, no server required.

![Life OS](docs/preview.png)

---

## Features

| Module | What it tracks |
|---|---|
| 💰 Finances | Monthly income, expenses, savings rate, investments (MF / Stocks / FD), net worth |
| 🏋️ Health | Gym sessions, daily diet (calories, protein, water), weekly check-ins, bulk targets |
| 💼 Career | Current role, active projects, skills tracker, milestones |
| 🎯 Goals | Quarterly OKRs with key results, progress bars, reflections |

- **Zero dependencies** — pure HTML, CSS, JavaScript
- **localStorage persistence** — data saves automatically in your browser
- **Dark mode** — auto-detects your system preference
- **India-first** — ₹ currency, en-IN formatting
- **Offline** — works without internet once opened

---

## Getting Started

### Option 1 — Open directly (simplest)

```bash
git clone https://github.com/YOUR_USERNAME/life-os.git
cd life-os
open index.html        # macOS
start index.html       # Windows
xdg-open index.html   # Linux
```

### Option 2 — Auto-open on laptop startup

**Windows:**
1. Press `Win + R`, type `shell:startup`, press Enter
2. Create a shortcut to `index.html` in the folder that opens
3. Right-click shortcut → Properties → set browser as default app

**macOS:**
1. System Settings → General → Login Items
2. Click `+` and select `index.html`
3. Or use Automator to create a "Launch Application" workflow

**Linux:**
Add to your `.bashrc` or desktop autostart:
```bash
xdg-open /path/to/life-os/index.html
```

### Option 3 — Serve locally (for live reload during dev)

```bash
cd life-os
npx serve .
# or
python3 -m http.server 3000
```

Then open `http://localhost:3000`

---

## Project Structure

```
life-os/
├── index.html          # The entire app — open this in your browser
├── README.md           # This file
├── docs/
│   ├── ROADMAP.md      # Feature roadmap and phase plan
│   ├── DATA_SCHEMA.md  # Full data model documentation
│   └── preview.png     # Screenshot for README
└── data/
    └── sample.json     # Sample data to import and try the app
```

---

## Data & Privacy

All your data lives in your browser's `localStorage` under the key `lifeOS_v1`. Nothing is sent to any server.

**To export your data:**
Open browser DevTools → Console → paste:
```js
console.log(JSON.stringify(JSON.parse(localStorage.getItem('lifeOS_v1')), null, 2))
```

**To import/restore data:**
```js
localStorage.setItem('lifeOS_v1', JSON.stringify({ /* your data */ }))
location.reload()
```

**To reset everything:**
```js
localStorage.removeItem('lifeOS_v1')
location.reload()
```

---

## Personalisation

### Change health targets
Open `index.html`, find this line near the bottom:
```js
const T = { kcal: 2900, prot: 134, water: 3.0 };
```
Edit values to match your own targets.

### Change currency
Find all instances of `₹` and replace with your currency symbol. Also update `en-IN` locale to yours (e.g. `en-US`, `en-GB`).

### Add a new module
1. Add a new `<div class="page">` section in the HTML
2. Add a nav button
3. Create your data array in the `D` object
4. Write a `refresh` function for that module

---

## Roadmap

### Phase 1 — Data schema ✅
- [x] Defined schemas for all 4 modules
- [x] Built interactive schema designer

### Phase 2 — Core dashboards ✅
- [x] Finance dashboard with cash flow and investment breakdown
- [x] Health dashboard with gym log, diet tracker, weekly check-in
- [x] Career dashboard with projects, skills, milestones
- [x] Goals dashboard with quarterly OKRs
- [x] Unified home screen

### Phase 3 — Automations ✅
- [x] CSV importer for Zerodha and Groww
- [x] AI-powered weekly review (Claude API)

### Phase 4 — Persistent app ✅
- [x] localStorage persistence
- [x] Standalone HTML file
- [x] GitHub repository

### Phase 5 — Future (contributions welcome)
- [ ] CSV import for Zerodha Console holdings
- [ ] MyFitnessPal / Cronometer diet CSV import
- [ ] Chart.js net worth trend graph
- [ ] PWA support (install as desktop app)
- [ ] Multi-device sync via a simple backend (Supabase / Firebase)
- [ ] Automated bank data via Account Aggregator (Finvu)
- [ ] Notion / Google Sheets sync

---

## Daily Usage Guide

| When | What to do | Time |
|---|---|---|
| Morning | Check home dashboard, log yesterday's diet if missed | 1 min |
| After gym | Log gym session (group, exercises, sets, duration) | 2 min |
| Evening | Log today's diet (calories, protein, water) | 1 min |
| Month end | Log finances (income, expenses, investment values) | 5 min |
| Sunday | Weekly check-in (weight, sessions, sleep, energy) | 3 min |

---

## Contributing

Pull requests welcome. For major changes, open an issue first.

```bash
git clone https://github.com/YOUR_USERNAME/life-os.git
cd life-os
# make your changes to index.html
git add .
git commit -m "feat: add X"
git push
```

---

## License

MIT — use it, modify it, share it.

---

*Built with Claude · Inspired by the idea that your life deserves a dashboard*
