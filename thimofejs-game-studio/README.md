# Thimofej's Game Studio

> Fully autonomous Roblox game studio — 24 coordinated AI agents, zero human intervention between trend detection and deployment

## What This Does

Detects Roblox and social media trends. Converts them into playable Roblox experiences. Deploys live. Tracks KPIs (≥10,000 Visits AND ≥5,000 Robux within 30 days). Learns and improves cycle over cycle.

## Import

```bash
npx paperclipai company import https://github.com/young-builders/paperclip-companies/tree/main/thimofejs-game-studio
```

## Setup (after import)

### 1. Set Secrets in Paperclip

Go to your Paperclip company settings and add these secrets:

| Secret | Where to get it |
|--------|----------------|
| `ROBLOX_OPS_KEY` | Roblox Creator Hub → Open Cloud → API Keys |
| `ROBLOX_UNIVERSE_ID` | Roblox Creator Hub → your game's Universe ID |
| `REDDIT_CLIENT_ID` | reddit.com/prefs/apps → create app |
| `REDDIT_CLIENT_SECRET` | same as above |
| `YOUTUBE_API_KEY` | console.cloud.google.com → YouTube Data API v3 |
| `GH_TOKEN` | github.com/settings/tokens (optional, for devops-engineer) |
| `REPLICATE_API_KEY` | replicate.com/account/api-tokens (for thumbnail-designer) |

### 2. Routines (Auto-configured)

Routines are pre-configured in `.paperclip.yaml` — no manual setup needed after import:

| Routine | Agent | Cron | What it does |
|---------|-------|------|-------------|
| `heartbeat` | `ceo` | `0 6 * * *` | Daily system health check |
| `pipeline-cycle` | `producer` | `0 8 * * 1` | Full trend→deploy pipeline every Monday |
| `daily-kpi-check` | `kpi-tracker` | `0 9 * * *` | Daily KPI snapshot for active games |

### 3. Configure Roblox Groups

Set up 3–5 Roblox Groups for risk isolation (see [Multi-Group Setup](COMPANY.md#multi-group-account-setup) in COMPANY.md).

### 4. Run Paperclip Server

```bash
npx paperclipai run
```

That's it. The pipeline runs fully autonomously from here.

## Pipeline

```
trend-scout → strategy-agent → game-designer → roblox-studio-builder
  → qa-lead + qa-tester → tos-guard → deploy-engineer → kpi-tracker → learning-agent
```

## Agents (24)

| Agent | Role | Model |
|-------|------|-------|
| CEO | Studio Head | Opus |
| Technical Director | Architecture | Opus |
| Producer | Pipeline coordination | Opus |
| Trend Scout | Roblox/Reddit/YouTube trend scanning | Sonnet |
| Strategy Agent | Mechanic approach selection | Sonnet |
| Game Designer | GDD authoring | Sonnet |
| Lead Luau Programmer | Code architecture | Sonnet |
| Roblox Studio Builder | Build orchestration | Sonnet |
| TOS Guard | Compliance gate | Sonnet |
| Deploy Engineer | Open Cloud publish | Sonnet |
| KPI Tracker | 30-day monitoring | Sonnet |
| Learning Agent | Pattern capture | Sonnet |
| Luau Programmer | Gameplay code | Sonnet |
| Network Programmer | RemoteEvents/replication | Sonnet |
| UI Programmer | ScreenGui/BillboardGui | Sonnet |
| Economy Designer | Gamepasses/Dev Products | Sonnet |
| Asset Specialist | Marketplace licensing | Sonnet |
| Obby Designer | Level design | Sonnet |
| World Builder | 3D environment | Sonnet |
| Performance Analyst | Heartbeat/FPS profiling | Sonnet |
| QA Lead | Test strategy + sign-off | Sonnet |
| QA Tester | Bug execution + verification | Sonnet |
| DevOps Engineer | Rojo/CI toolchain | Sonnet |
| Community Manager | Group shouts + feedback | Sonnet |

## Hard Constraints

- Roblox Studio only — no Unity, Unreal, Godot
- Mechanic similarity to trend source < 70% (hard block in TOS Guard)
- Only Roblox Marketplace free-distribute assets
- No TikTok/YouTube audio imports
- Multi-group distribution across 3–5 Roblox Groups

## KPI Targets

Both must hit within 30 days of deploy:
- **Visits ≥ 10,000**
- **Robux ≥ 5,000**

---

Built on [Paperclip](https://paperclip.ing)
