# Studio Pipeline

5-company pipeline for Roblox game development. Coordination via shared filesystem.

## Architecture

```
studio-research → studio-review → studio-build → studio-qa → studio-ops
```

Each company reads from its input folder, writes to the next company's input folder.

## Shared Folder Structure

Set `PIPELINE_PATH` env var pointing to a shared directory accessible by all companies.

```
$PIPELINE_PATH/
  ideas/
    pending/          ← research writes here
    approved/         ← review moves approved ideas here
    rejected/         ← review moves rejected ideas here (with reason)
  builds/
    pending-qa/       ← build writes here
    passed/           ← qa moves passed builds here
    failed/           ← qa moves failed builds here (with bug report)
  releases/
    live/             ← ops marks deployed games here
```

## Companies

| Company | Input | Output | Opus Agents |
|---------|-------|--------|-------------|
| studio-research | — | ideas/pending | — |
| studio-review | ideas/pending | ideas/approved or rejected | review-director |
| studio-build | ideas/approved | builds/pending-qa | technical-director |
| studio-qa | builds/pending-qa | builds/passed or failed | — |
| studio-ops | builds/passed | live release | ceo, producer, learning-agent |

## Failure Loops

- `review` rejects idea → `research` can rework and resubmit
- `qa` fails build → `build` fixes and resubmits to `builds/pending-qa`

## Setup

Pipeline folder: `/Users/thimofejzapko/game-studio-pipeline` (already initialized)

```bash
export PIPELINE_PATH=/Users/thimofejzapko/game-studio-pipeline
```

Add to `~/.zshrc` to persist. Then configure secrets per company (see each COMPANY.md) and start with `studio-research`.
