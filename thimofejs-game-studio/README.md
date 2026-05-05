# Thimofej's Game Studio

> Fully autonomous Roblox game studio — 24 coordinated AI agents, zero human intervention between trend detection and deployment

> An [Agent Company](https://agentcompanies.io) powering the Autonomous Roblox Trend Engine — detect trends, build games, optimize Visits + Robux jointly

## Mission

Detect Roblox and social media trends. Convert them into playable Roblox experiences. Deploy live. Hit ≥10,000 Visits AND ≥5,000 Robux within 30 days. Repeat. Learn. Improve.

## Pipeline

```
Trend Scout → Strategy Decision → Game Design (GDD) → Build (Roblox Studio) → QA → TOS Gate → Deploy (Open Cloud) → Track (30d) → Learn
```

## What's Inside

| Content | Count |
|---------|-------|
| Agents | 24 |
| Skills | 25 |
| Teams | 6 |

### Agents

| Agent | Role | Reports To |
|-------|------|------------|
| CEO | Studio Head | — |
| Technical Director | Director | ceo |
| Producer | Director | ceo |
| Trend Scout | Pipeline | producer |
| Strategy Agent | Pipeline | producer |
| Game Designer | Design | producer |
| Lead Luau Programmer | Engineering | technical-director |
| Roblox Studio Builder | Pipeline | producer |
| TOS Guard | Compliance | producer |
| Deploy Engineer | Pipeline | producer |
| KPI Tracker | Growth | producer |
| Learning Agent | Growth | ceo |
| Luau Programmer | Engineering | lead-luau-programmer |
| Network Programmer | Engineering | lead-luau-programmer |
| UI Programmer | Engineering | lead-luau-programmer |
| Economy Designer | Design | game-designer |
| Asset Specialist | Design | roblox-studio-builder |
| Obby Designer | Design | game-designer |
| World Builder | Design | roblox-studio-builder |
| Performance Analyst | Engineering | technical-director |
| QA Lead | QA | technical-director |
| QA Tester | QA | qa-lead |
| DevOps Engineer | Engineering | technical-director |
| Community Manager | Growth | producer |

### Skills

| Skill | Description |
|-------|-------------|
| trend-scan | Full trend pipeline across Roblox + TikTok + YouTube + Reddit |
| strategy-decision | Select game mechanic approach with similarity score and KPI projection |
| tos-check | Full TOS compliance gate — hard block on similarity ≥ 70% |
| deploy-game | Publish via Roblox Open Cloud API |
| kpi-report | 30-day Visits + Robux tracking with trajectory projection |
| brainstorm | Roblox game ideation via MDA framework |
| prototype | Build minimal playable Roblox prototype (≤ 4 hours) |
| design-system | Write full 8-section Roblox GDD |
| design-review | Validate GDD for completeness, feasibility, TOS, monetization |
| luau-review | Code review for Luau — typing, APIs, server/client safety |
| architecture-decision | ADR for Roblox technical decisions |
| playtest-report | Playtest session analysis with priority fix list |
| balance-check | Difficulty curve + Robux economy balance verification |
| economy-design | Gamepass + Dev Product monetization model design |
| asset-audit | Asset license compliance check (free-distribute only) |
| roblox-setup | New Roblox project init — Rojo, Selene, base modules |
| sprint-plan | Build sprint with parallel agent tracks |
| milestone-review | Pipeline stage go/no-go gate |
| scope-check | GDD scope deviation detection |
| retrospective | Post-30d cycle retrospective |
| bug-report | Standardized Roblox bug documentation (P0-P3) |
| perf-profile | Roblox server/client performance profiling |
| tech-debt | Luau tech debt tracking |
| release-checklist | Pre-deploy mandatory checklist |
| launch-checklist | Post-deploy 2-hour launch validation |

### Teams

| Team | Purpose |
|------|---------|
| Leadership | Greenlight decisions, strategy, cross-agent escalation |
| Autonomous Pipeline | Trend → Strategy → Design → Build → TOS → Deploy → Track → Learn |
| Engineering | Luau code, Rojo toolchain, GitHub CI, Open Cloud automation |
| Design | GDDs, obby levels, world building, Robux economy |
| QA & Compliance | Two hard gates: QA sign-off + TOS guard approval |
| Growth & Analytics | 30-day KPI monitoring, community amplification, learning |

## Hard Constraints

- **Roblox Studio only** — no Unity, no Unreal, no Godot
- **No 1-to-1 clones** — mechanic similarity to source < 70% mandatory
- **No copyrighted assets** — Roblox Marketplace free-distribute only
- **No trend audio** — TikTok/YouTube music never imported
- **Multi-group distribution** — 3–5 Roblox Groups for risk isolation

## KPI Targets

A game is a **SUCCESS** only when BOTH hit within 30 days:
- Visits: **≥ 10,000**
- Robux: **≥ 5,000**

## Phase 1 Definition of Done

- 3 consecutive games hit both KPI thresholds
- Pipeline runs 90 days stable, fully autonomous
- 0 account terminations, TOS strike rate < 1 per 10 deployed games
- Learning system measurably improves success rate cycle over cycle

## Getting Started

```bash
npx paperclipai company import this-github-url-or-folder
```

See [Paperclip](https://paperclip.ing) for more information.

---
Built for the Autonomous Roblox Trend Engine — Thimofej's Game Studio
