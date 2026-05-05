---
name: Daily KPI Check
description: Pull current Visits and Robux for all active games, flag games approaching or past 30-day window, escalate to CEO on threshold hits
assignee: kpi-tracker
recurring: true
---

For every deployed game in active monitoring window: fetch Visits and Robux via Roblox Open Cloud API. Compare against thresholds (≥10,000 Visits AND ≥5,000 Robux within 30 days). Flag: HIT (both thresholds met), PARTIAL (one met), MISS (30-day window expired, neither met). Deliver daily snapshot report to learning-agent and CEO.
