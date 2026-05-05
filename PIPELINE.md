# Studio Pipeline

5-company pipeline for Roblox game development. Coordination via GitHub Issues and Pull Requests.

## Architecture

```
studio-research → studio-review → studio-build → studio-qa → studio-ops
```

Each company reads from GitHub Issues in `young-builders/pipeline`, acts on them, and advances the label to trigger the next company.

## GitHub Coordination

Two repositories:

| Repo | Purpose |
|------|---------|
| `young-builders/pipeline` | Idea tracking — Issues + Labels |
| `young-builders/games` | Game code — source files + PRs |

No shared filesystem. No `PIPELINE_PATH`. All state lives in GitHub.

## Label Flow

```
idea/pending
    ↓  (review: GO)
idea/approved
    ↓  (build: picks up, opens PR)
build/in-progress
    ↓  (build: PR ready)
build/pending-qa
    ↓  (qa: approved PR)
qa/passed
    ↓  (ops: merged + deployed)
released  [Issue closed]

idea/pending → idea/rejected  (review: NO-GO)
build/pending-qa → build/in-progress  (qa: FAIL — back to build)
```

## Companies

| Company | Input | Output | Opus Agents |
|---------|-------|--------|-------------|
| studio-research | — | Issue with `idea/pending` | — |
| studio-review | Issues with `idea/pending` | relabel to `idea/approved` or `idea/rejected` | review-director |
| studio-build | Issues with `idea/approved` | PR in young-builders/games, relabel to `build/pending-qa` | technical-director |
| studio-qa | PRs with `build/pending-qa` | approve PR + `qa/passed`, or request-changes + `build/in-progress` | — |
| studio-ops | Issues with `qa/passed` | merge PR, deploy, relabel to `released`, close issue | ceo, producer, learning-agent |

## Failure Loops

- `review` rejects idea → Issue stays open with `idea/rejected` label + rejection reason comment. `research` can open a new Issue with reworked idea.
- `qa` fails build → requests-changes on PR, relabels pipeline Issue to `build/in-progress`. `build` fixes and force-pushes to same PR branch.

## Setup

Each company needs exactly one secret:

```
GH_TOKEN  — GitHub personal access token with repo + issues scope
```

Set `GH_TOKEN` in Paperclip secrets for each company. No other environment variables required. Then start with `studio-research`.
