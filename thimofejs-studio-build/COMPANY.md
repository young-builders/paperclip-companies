# thimofejs-studio-build

Builds approved game ideas into playable Roblox experiences.

## Pipeline Role

**Input:** Issues with label `idea/approved` in `young-builders/pipeline`
**Output:** Pull Request in `young-builders/games` with game code; pipeline Issue relabeled to `build/pending-qa`

## Workflow

1. `technical-director` reads approved Issue, creates build plan
2. `game-designer` + `viral-mechanic-designer` define core loop + hook mechanics
3. `map-designer` + `world-builder` design level layout
4. `lead-luau-programmer` coordinates programming work, sets architecture
5. `luau-programmer` + `network-programmer` + `ui-programmer` implement
6. `ui-ux-designer` + `audio-designer` + `asset-specialist` polish
7. `onboarding-designer` designs first-time user experience
8. `economy-designer` wires in gamepass + currency systems
9. `data-architect` sets up DataStore schema
10. `roblox-studio-builder` assembles final Studio file
11. `technical-director` opens PR in `young-builders/games`, links pipeline Issue, relabels Issue to `build/pending-qa`

## Game Repository Structure

```
young-builders/games/
  games/<game-slug>/
    BUILD.md          — build summary, known issues, test checklist
    game.rbxl         — Roblox Studio file (or Rojo project)
    src/              — Luau source files
```

## PR Description Format

```markdown
## Build Summary

**Idea Issue:** young-builders/pipeline#<issue-number>
**Game Slug:** <game-slug>

## What was built
- ...

## Known Issues
- ...

## Test Checklist
- [ ] ...
```

## Agents

| Agent | Role | Model |
|-------|------|-------|
| technical-director | Build orchestrator, architecture decisions | Opus |
| game-designer | Core game loop design | Sonnet |
| viral-mechanic-designer | Hook + shareability mechanics | Sonnet |
| map-designer | Map layout + checkpoint design | Sonnet |
| world-builder | Environment, atmosphere, theming | Sonnet |
| lead-luau-programmer | Code architecture, code review | Sonnet |
| luau-programmer | Feature implementation | Sonnet |
| network-programmer | RemoteEvents, server/client split | Sonnet |
| ui-programmer | GUI scripting | Sonnet |
| ui-ux-designer | Visual design, UX flow | Sonnet |
| audio-designer | SFX, music selection | Sonnet |
| asset-specialist | Models, meshes, textures | Sonnet |
| roblox-studio-builder | Studio assembly | Sonnet |
| onboarding-designer | First-time experience | Sonnet |
| economy-designer | Gamepass, Robux economy | Sonnet |
| data-architect | DataStore schema | Sonnet |

## Rules

- Only pick up Issues labeled `idea/approved` — never `idea/pending` or `idea/rejected`
- QA failures return the Issue to `build/in-progress` label — `technical-director` triages, fixes on the existing PR branch, and force-pushes

## Secrets Required

- `GH_TOKEN` — GitHub token (repo + issues + pull_requests scope) for reading Issues in young-builders/pipeline and opening PRs in young-builders/games
- `ROBLOX_BUILD_KEY` — Roblox Open Cloud key with `assets:write` permission — used by audio-designer and asset-specialist to upload custom audio and models
