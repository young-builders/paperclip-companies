# thimofejs-studio-ops

Executive layer + post-launch operations. CEO orchestrates the full pipeline. Everything after QA pass lives here.

## Pipeline Role

**Input:** Issues with label `qa/passed` in `young-builders/pipeline`
**Output:** Merges PR in `young-builders/games`, deploys to Roblox, relabels Issue to `released`, closes Issue

## Workflow

### Pre-Launch
1. `producer` reviews the QA-passed PR + QA report comment, gives final green light
2. `thumbnail-designer` generates game icon + thumbnails
3. `localization-agent` prepares EN/DE/ES/PT descriptions
4. `deploy-engineer` merges PR in `young-builders/games`, publishes to Roblox via API
5. `devops-engineer` sets up monitoring
6. `ceo` relabels pipeline Issue to `released` and closes it

### Post-Launch (ongoing)
7. `kpi-tracker` monitors DAU, CCU, revenue daily
8. `player-behavior-analyst` analyzes retention + drop-off points
9. `a-b-test-coordinator` runs gamepass + UI experiments
10. `growth-hacker` + `influencer-agent` + `content-creator` drive traffic
11. `community-manager` + `sentiment-analyst` watch player feedback
12. `live-ops-designer` + `patch-designer` plan updates
13. `retention-engineer` addresses churn signals
14. `monetization-optimizer` tunes economy + gamepass pricing
15. `learning-agent` documents what worked → feeds back to research

### Portfolio Management
- `portfolio-manager` tracks all live games, flags underperformers
- `cross-game-economy-architect` manages shared Robux economy across games
- `ceo` makes decisions on sunset, pivot, or double-down

## Agents

| Agent | Role | Model |
|-------|------|-------|
| ceo | Pipeline orchestration, strategic decisions | Opus |
| producer | Pre-launch sign-off | Opus |
| learning-agent | Post-mortem, feeds learnings back to research | Opus |
| deploy-engineer | Merge PR + Roblox publish via API | Sonnet |
| devops-engineer | Monitoring setup | Sonnet |
| kpi-tracker | Daily metrics | Sonnet |
| player-behavior-analyst | Retention analysis | Sonnet |
| thumbnail-designer | Icon + thumbnails (Replicate) | Sonnet |
| growth-hacker | Traffic growth | Sonnet |
| a-b-test-coordinator | Experiments | Sonnet |
| monetization-optimizer | Economy tuning | Sonnet |
| vip-server-specialist | VIP server setup | Sonnet |
| premium-benefits-designer | Gamepass benefits | Sonnet |
| cross-game-economy-architect | Cross-game economy | Sonnet |
| live-ops-designer | Event + update planning | Sonnet |
| retention-engineer | Churn reduction | Sonnet |
| patch-designer | Update content | Sonnet |
| content-creator | Social + dev content | Sonnet |
| influencer-agent | Influencer outreach | Sonnet |
| community-manager | Player community | Sonnet |
| localization-agent | Multi-language descriptions | Sonnet |
| portfolio-manager | Cross-game oversight | Sonnet |
| memory-manager | Institutional knowledge | Sonnet |
| prompt-engineer | Agent prompt optimization | Sonnet |

## Secrets Required

- `GH_TOKEN` — GitHub token (repo + issues + pull_requests scope) for merging PRs in young-builders/games and relabeling/closing Issues in young-builders/pipeline
- `ROBLOX_API_KEY` — deploy + analytics (Universe ID is created dynamically per game, stored in `game-meta.json`)
- `REPLICATE_API_KEY` — thumbnail generation
