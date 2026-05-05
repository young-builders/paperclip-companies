---
name: daily-kpi-check
description: Daily KPI snapshot for all active games — poll Roblox Analytics API, calculate trajectory, fire Day-7 and Day-14 alerts if needed
---

Poll Roblox Analytics API for every game in the active monitoring window. For each game: record Visits + Robux snapshot, calculate 30-day trajectory, compare to targets (≥10K visits, ≥5K Robux). Fire alert to producer if: Day 7 trajectory < 50% of target OR Day 14 trajectory < 70% of target. Mark game SUCCESS if both thresholds hit. Mark FAILED after day 30. Deliver final 30-day report to learning-agent on close.
