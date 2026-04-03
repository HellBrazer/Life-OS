# Roadmap

## Phase 1 — Data schema ✅
Define what data to track before building anything.
- Finances: monthly snapshots, no transaction-level tracking
- Health: gym log + daily diet + weekly check-in (manual, no wearable)
- Career: role, projects, skills, milestones
- Goals: quarterly OKRs with key results

## Phase 2 — Core dashboards ✅
Build live views for each module.
- Finance dashboard with cash flow bars and investment breakdown
- Health dashboard with bulk targets (2,900 kcal, 134g protein, 3L water)
- Career dashboard with project status and skill progress bars
- Goals dashboard with OKR progress tracking
- Unified home screen showing live data from all modules

## Phase 3 — Automations ✅
Reduce manual entry where possible.
- CSV importer for Zerodha Console and Groww portfolio exports
- AI-powered weekly review using Claude API

## Phase 4 — Standalone app ✅
Move from Claude prototype to real usable app.
- Export as single index.html
- localStorage for data persistence across sessions
- GitHub repository with docs

## Phase 5 — Planned
- [ ] Net worth trend chart (Chart.js)
- [ ] Diet CSV import from MyFitnessPal / Cronometer
- [ ] PWA manifest — install as desktop app via browser
- [ ] Data export to JSON / CSV
- [ ] Multi-device sync via Supabase or Firebase
- [ ] Automated investment data via Kuvera API
- [ ] Account Aggregator integration (Finvu) for bank balances
- [ ] Google Calendar integration for commitment tracking
- [ ] Notion sync for goals
