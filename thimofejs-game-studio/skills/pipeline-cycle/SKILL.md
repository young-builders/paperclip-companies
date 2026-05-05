---
name: pipeline-cycle
description: Run one full autonomous pipeline cycle — trend-scan → strategy → GDD → build → QA → TOS gate → deploy → start KPI monitoring
---

Execute one full pipeline cycle. Sequential stages with hard gates:

1. **trend-scout** runs `trend-scan` → outputs ranked top-5 trends
2. **strategy-agent** runs `strategy-decision` → selects approach (similarity < 70% required)
3. **game-designer** runs `design-system` → produces locked GDD
4. **roblox-studio-builder** dispatches parallel: `luau-programmer` + `network-programmer` + `ui-programmer` + `world-builder` + `economy-designer` + `asset-specialist`
5. **performance-analyst** runs `perf-profile` → must pass before QA
6. **qa-lead** runs `playtest-report` → must sign off (0 P0/P1 bugs)
7. **tos-guard** runs `tos-check` → APPROVED required (hard block if REJECTED → loop back to step 4)
8. **deploy-engineer** runs `deploy-game` → publishes via Open Cloud API
9. **community-manager** posts Group shout
10. **kpi-tracker** starts 30-day monitoring window

Abort cycle and notify CEO if: strategy-agent rejects all 5 trends, tos-guard rejects twice, deploy fails.
