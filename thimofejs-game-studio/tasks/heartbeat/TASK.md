---
name: Daily System Heartbeat
description: Verify pipeline health, check for failed runs, confirm kpi-tracker active on all deployed games, validate Open Cloud API key
assignee: ceo
recurring: true
---

Daily health check. Verify: (1) last `pipeline-cycle` Paperclip routine ran without error (check routine run history), (2) `young-builders/games` GitHub Actions CI status — Rojo build + Selene lint must be green on latest commit, (3) all active games have kpi-tracker monitoring running, (4) no agent errored in last 24h, (5) Open Cloud API key still valid (test call with `GET /v1/universes/{universeId}`). Report: GREEN (all good) / YELLOW (non-critical issue, document) / RED (pipeline blocked, escalate to CEO immediately with specific failure).
