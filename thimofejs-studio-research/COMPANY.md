# thimofejs-studio-research

Finds viral Roblox game ideas. Scans trends, analyzes competitors, builds player personas.

## Pipeline Role

**Input:** Nothing (entry point of pipeline)
**Output:** `$PIPELINE_PATH/ideas/pending/<idea-slug>.md`

## Workflow

1. `trend-scout` scans Reddit (r/roblox, r/gaming) + YouTube for trending game types
2. `trend-forecaster` predicts which trends have 2-4 week runway
3. `competitor-analyst` checks existing Roblox games in same niche
4. `market-researcher` estimates audience size + monetization potential
5. `player-persona-builder` defines target player profile
6. `research-lead` synthesizes into idea file → drops in `ideas/pending/`

## Idea File Format

```
$PIPELINE_PATH/ideas/pending/<idea-slug>.md
```

```markdown
# [Game Title Concept]

## Trend Signal
- Source, date, engagement metrics

## Competitor Gap
- Existing games, what they miss

## Target Persona
- Age, play style, motivation

## Monetization Potential
- Estimated DAU range, gamepass hooks

## Verdict
- Why this is worth building now
```

## Agents

| Agent | Role |
|-------|------|
| research-lead | Orchestrates, writes final idea file |
| trend-scout | Reddit + YouTube scanning (needs API keys) |
| trend-forecaster | Trend runway analysis |
| market-researcher | Audience + revenue estimation |
| competitor-analyst | Existing game gap analysis |
| player-persona-builder | Target player profile |

## Secrets Required

- `REDDIT_CLIENT_ID` + `REDDIT_CLIENT_SECRET` — Reddit API
- `YOUTUBE_API_KEY` — YouTube Data API
