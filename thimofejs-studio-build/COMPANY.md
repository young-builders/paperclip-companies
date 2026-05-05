# thimofejs-studio-build

Builds approved game ideas into playable Roblox experiences.

## Pipeline Role

**Input:** `$PIPELINE_PATH/ideas/approved/<idea-slug>.md`
**Output:** `$PIPELINE_PATH/builds/pending-qa/<idea-slug>/` — full build artifact folder

## Workflow

1. `technical-director` reads approved idea, creates build plan
2. `game-designer` + `viral-mechanic-designer` define core loop + hook mechanics
3. `map-designer` + `world-builder` design level layout
4. `lead-luau-programmer` coordinates programming work, sets architecture
5. `luau-programmer` + `network-programmer` + `ui-programmer` implement
6. `ui-ux-designer` + `audio-designer` + `asset-specialist` polish
7. `onboarding-designer` designs first-time user experience
8. `economy-designer` wires in gamepass + currency systems
9. `data-architect` sets up DataStore schema
10. `roblox-studio-builder` assembles final Studio file
11. `technical-director` writes build report → drops artifact in `builds/pending-qa/`

## Build Artifact Format

```
$PIPELINE_PATH/builds/pending-qa/<idea-slug>/
  BUILD.md          — build summary, known issues, test checklist
  game.rbxl         — Roblox Studio file (or Rojo project)
  src/              — Luau source files
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

- Only pick up ideas from `ideas/approved/` — never from `pending/` or `rejected/`
- QA failures return build to `builds/failed/` with bug report — technical-director triages and restarts
