---
name: heartbeat
description: Daily system health check — verify last pipeline-cycle ran, check for failed GitHub Actions workflows, confirm kpi-tracker is active on all deployed games
---

Daily health check. Verify: (1) last `pipeline-cycle` Paperclip routine ran without error (check routine run history), (2) `young-builders/games` GitHub Actions CI status — Rojo build + Selene lint must be green on latest commit, (3) all active games have kpi-tracker monitoring running, (4) no agent errored in last 24h, (5) Open Cloud API key still valid (test call with `GET /v1/universes/{universeId}`). Report: GREEN (all good) / YELLOW (non-critical issue, document) / RED (pipeline blocked, escalate to CEO immediately with specific failure).
