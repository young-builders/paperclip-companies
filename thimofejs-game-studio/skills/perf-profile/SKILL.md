---
name: perf-profile
description: Profile a Roblox game for server Heartbeat, client FPS, memory usage, instance count, script time — identify bottlenecks with line references
---

Profile a Roblox game with MicroProfiler and output. Check: server Heartbeat (target < 16ms), client FPS (target ≥ 30 on mobile), memory growth over 10 minutes (flag if growing), instance count (target < 5,000), script execution time (target < 5ms per frame). Output: findings with specific script/line references and fix recommendations.
