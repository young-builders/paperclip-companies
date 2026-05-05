---
name: heartbeat
description: Daily system health check — verify last pipeline-cycle ran, check for failed GitHub Actions workflows, confirm kpi-tracker is active on all deployed games
---

Daily health check. Verify: (1) last pipeline-cycle GitHub Actions run status (pass/fail), (2) all active games have kpi-tracker monitoring running, (3) no agent errored in last 24h, (4) Open Cloud API key still valid (test call). Report: GREEN (all good) / YELLOW (non-critical issue) / RED (pipeline blocked, escalate to CEO immediately).
