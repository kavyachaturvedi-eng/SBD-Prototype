# SBD Module — Skill-Based Deployment

Full 6-phase prototype of the factory operator deployment system. Single-page React application built to match the provided HTML wireframes.

## Quick deploy to Vercel

### Option 1 — drag-and-drop (easiest)
1. Go to https://vercel.com/new
2. Drag the entire `sbd-app` folder onto the page
3. Click Deploy
4. Done — you'll get a live URL in ~30 seconds

### Option 2 — Vercel CLI
```
npm install -g vercel
cd sbd-app
vercel
```
Accept all defaults. The output URL is your live app.

### Option 3 — GitHub → Vercel
1. Push this folder to a GitHub repo
2. On Vercel: New Project → Import Git Repository
3. Framework Preset: leave as **Other**
4. Build settings: leave all blank
5. Deploy

## What's included

### All 6 phases
| Phase | Screens |
|-------|---------|
| **1 — Masters** | Home, Division, Factory, Line, Machine, Operation, Employee Skill, Integration Health |
| **2 — Operation Bulletins** | OB list, Create mode chooser (Fresh / Copy / Template), OB builder |
| **3 — Line Design** | LD list, Builder with scenario generation, comparison panel, bottleneck identification |
| **4 — Deployment Planning** | Assignment Dashboard, split-layout Deployment Planning screen with manpower panel |
| **5 — Daily Balancing** | Tablet-responsive, urgency countdown, operator chips, save & lock |
| **6 — Cycle Time Capture** | CT modal, Skill % preview, history view with trend sparklines |

### 4 DevX differentiators (marked ✦)
1. **OB Templates** (Phase 2) — Formal Shirt, Casual Shirt, 5-Pocket Jean — always load current SMVs
2. **SMV Health Check** (Phase 2) — Compares planned SMV vs floor median CT on save
3. **Bottleneck Relief Suggestion** (Phase 3) — Single best operator reallocation calculation
4. **Training Flag → Training Register** (Phase 4) — One-click flag, auto-closes when CT improves
5. **Auto-Fill All Gaps** (Phase 5) — Pre-assigns operators on HRMS sync, review-and-approve flow
6. **AI Capture Prioritisation** (Phase 6) — Ranked list of who to observe today
7. **Learning Milestone Alert** (Phase 6) — Toast when operator crosses 70/85/90% Skill across 3 obs

(Skill Coverage Map also visible — accessible from Employee Skill Master)

### Role switching
Use the dropdown in the top-right to switch between:
- **Admin** — sees Phase 1 (all masters)
- **IE** (Industrial Engineer) — sees Phases 2, 3, 4, 6 history
- **Supervisor** — sees Phases 5, 6 (tablet-optimised)

The sidebar updates automatically based on selected role.

## Technical notes

- **No build step** — uses React 18 + Babel Standalone via CDN
- **No backend** — all data is in-memory React state
- **No environment variables** required
- **Refresh page = reset to seed data** (intentional for prototype)
- **Responsive** — works on tablet (Phase 5/6) and desktop

## File structure
```
sbd-app/
├── index.html      ← Entire app (one file)
├── vercel.json     ← Vercel config (clean URLs)
└── README.md       ← This file
```
