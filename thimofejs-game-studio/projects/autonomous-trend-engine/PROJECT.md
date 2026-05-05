---
name: Autonomous Roblox Trend Engine
description: Implement and run the fully autonomous pipeline — trend detection to live deployment — until 3 consecutive games hit both KPI thresholds
slug: autonomous-trend-engine
assignee: producer
---

Build and operate the fully autonomous Roblox Trend Engine. The pipeline must run from trend detection to deployed live game with zero human intervention. Success is defined as 3 consecutive games hitting both KPIs (≥10,000 Visits AND ≥5,000 Robux) within 30 days of deploy.

## Milestones

1. **Pipeline Scaffolding** — All 24 agents configured, Rojo toolchain working, Open Cloud API connected, multi-group accounts set up
2. **First Game Deployed** — Full pipeline runs end-to-end: trend → strategy → GDD → build → QA → TOS → deploy → monitoring active
3. **First KPI Hit** — At least 1 game hits both thresholds (≥10K visits + ≥5K Robux)
4. **3 Consecutive Successes** — 3 games in a row hit both KPIs → Phase 1 Definition of Done
5. **90-Day Stability** — Pipeline runs autonomously for 90 days: TOS strike rate < 1/10, 0 account terminations, learning system measurably improving success rate
