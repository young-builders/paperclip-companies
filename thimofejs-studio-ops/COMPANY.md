# thimofejs-studio-ops

Executive layer + post-launch operations. CEO orchestrates the full pipeline. Everything after QA pass lives here.

## Pipeline Role

**Input:** `$PIPELINE_PATH/builds/passed/<idea-slug>/`
**Output:** Live Roblox game + ongoing ops

## Workflow

### Pre-Launch
1. `producer` reviews QA-passed build, gives final green light
2. `thumbnail-designer` generates game icon + thumbnails
3. `localization-agent` prepares EN/DE/ES/PT descriptions
4. `deploy-engineer` publishes to Roblox via API
5. `devops-engineer` sets up monitoring

### Post-Launch (ongoing)
6. `kpi-tracker` monitors DAU, CCU, revenue daily
7. `player-behavior-analyst` analyzes retention + drop-off points
8. `a-b-test-coordinator` runs gamepass + UI experiments
9. `growth-hacker` + `influencer-agent` + `content-creator` drive traffic
10. `community-manager` + `sentiment-analyst` watch player feedback
11. `live-ops-designer` + `patch-designer` plan updates
12. `retention-engineer` addresses churn signals
13. `monetization-optimizer` tunes economy + gamepass pricing
14. `learning-agent` documents what worked → feeds back to research

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
| deploy-engineer | Roblox publish via API | Sonnet |
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

- `ROBLOX_API_KEY` + `ROBLOX_UNIVERSE_ID` — deploy + analytics
- `REPLICATE_API_KEY` — thumbnail generation
