---
name: Daily System Heartbeat
description: Verify pipeline health, check for failed runs, confirm kpi-tracker active on all deployed games, validate Open Cloud API key
assignee: ceo
recurring: true
---

Daily health check. Verify: (1) last pipeline-cycle GitHub Actions run status (pass/fail), (2) all active games have kpi-tracker monitoring running, (3) no agent errored in last 24h, (4) Open Cloud API key still valid (test call). Report: GREEN (all good) / YELLOW (non-critical issue) / RED (pipeline blocked, escalate immediately).
