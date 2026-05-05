---
name: Thimofej's Game Studio
description: Autonomous Roblox game studio with 24 coordinated AI agents — fully autonomous pipeline from trend detection to live deployment, optimizing Visits and Robux jointly
slug: thimofejs-game-studio
schema: agentcompanies/v1
version: 1.0.0
license: MIT
authors:
  - name: Thimofej Zapko
goals:
  - Detect Roblox and social media trends autonomously and convert them into live Roblox experiences
  - Jointly optimize for ≥10,000 Visits AND ≥5,000 Robux within 30 days per deployed game
  - Run the full pipeline — trend → strategy → build → test → TOS gate → deploy → track — with zero human intervention
  - Never clone 1-to-1; always mash-up or add an original twist (mechanic similarity to trend source < 70%)
  - Maintain 0 account terminations, TOS strike rate < 1 per 10 deployed games
tags:
  - roblox
  - roblox-studio
  - luau
  - autonomous-pipeline
  - trend-engine
  - game-studio
---

Thimofej's Game Studio is a fully autonomous Roblox-only game development operation powered by 24 specialized AI agents. The studio detects trends, designs games, builds them in Roblox Studio, validates TOS compliance, deploys via Open Cloud API, and monitors KPIs — all without human intervention between trend detection and deployment.

## Mission

**Autonomous Roblox Trend Engine** — detect trends, ship games, optimize KPIs, learn from results.

A game counts as a success only when BOTH thresholds are hit within 30 days of deploy:
- **Visits:** ≥ 10,000
- **Robux:** ≥ 5,000

## Pipeline (Fully Autonomous)

| Stage | Agent | Output |
|-------|-------|--------|
| 1. Trend Scout | `trend-scout` | Ranked trend list with growth rates |
| 2. Strategy Decision | `strategy-agent` | Mechanic approach + rationale |
| 3. Game Design | `game-designer` | Full GDD (8-section) |
| 4. Build | `roblox-studio-builder` + `luau-programmer` | Working Roblox game |
| 5. Test + Fix | `qa-lead` + `qa-tester` | Bug-free build |
| 6. TOS Gate | `tos-guard` | Compliance sign-off |
| 7. Deploy | `deploy-engineer` | Live on Roblox |
| 8. Track + Learn | `kpi-tracker` + `learning-agent` | 30-day report + updated pattern library |

## Hard Constraints

- No 1-to-1 clones — mash-up or original twist mandatory (mechanic similarity < 70%)
- No copyrighted assets — only Roblox Marketplace free-distribute assets + own AI-generated decals/audio
- No trend audio — TikTok/YouTube music never imported
- Multi-group architecture — games distributed across 3–5 Roblox Groups for risk isolation
- Platform: **Roblox Studio only** — no Unity, no Unreal, no Godot

## How the Studio Works

The studio runs on a **sequential autonomous pipeline** — each stage hands off to the next automatically. Within the build stage, the Producer dispatches work to specialists in parallel.

### Organizational Tiers

- **CEO** (Opus-tier): Thimofej's autonomous proxy — strategy, greenlight, kill decisions
- **Directors** (Opus-tier): Technical Director and Producer set architecture and schedule
- **Pipeline Agents** (Sonnet-tier): Trend Scout, Strategy Agent, Game Designer, Roblox Studio Builder, TOS Guard, Deploy Engineer, KPI Tracker, Learning Agent
- **Specialists** (Sonnet-tier): Luau Programmer, Network Programmer, UI Programmer, Economy Designer, Asset Specialist, Obby Designer, World Builder, Performance Analyst, QA Lead, QA Tester, DevOps Engineer, Community Manager

### Engine

**Roblox Studio only.** All code in Luau. Server/client architecture via RemoteEvents and RemoteFunctions. Assets from Roblox Marketplace (free-distribute license only). Deploy via Roblox Open Cloud API.

## Multi-Group Account Setup

Games are distributed across 3–5 Roblox Groups for risk isolation. A TOS strike on one group does not affect the others.

| Group | Purpose | Max active games |
|-------|---------|-----------------|
| Group A | Flagship releases — highest-confidence games | 3 |
| Group B | Trend tests — unproven mechanics, experimental | 3 |
| Group C | Evergreen — older games kept live for passive income | 5 |
| Group D (optional) | Overflow or regional focus | 3 |

**Configuration steps:**
1. Create groups in Roblox Creator Hub — each needs its own `UNIVERSE_ID`
2. CEO assigns each new game to a group before deploy (based on confidence score from strategy-agent)
3. `ROBLOX_API_KEY` must have Open Cloud permissions scoped to all groups
4. If a group receives a TOS strike: pause all new deployments to that group, escalate to CEO

**Risk rule:** No group takes more than 3 new games per 30-day cycle.

### Definition of Done (Phase 1)

- 3 consecutive games hit both KPI thresholds
- Pipeline runs 90 days stable, fully autonomous
- 0 account terminations, TOS strike rate < 1 per 10 deployed games
- Learning system measurably improves success rate cycle over cycle
