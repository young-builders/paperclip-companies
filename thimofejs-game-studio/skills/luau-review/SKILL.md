---
name: luau-review
description: Code review for Luau scripts — checks strict typing, no deprecated APIs, server/client boundary safety, RemoteEvent validation, DataStore patterns, performance
---

Review Luau code for: --!strict typing, no deprecated APIs (wait/game.Workspace/etc.), server/client boundary violations, RemoteEvent input validation, DataStore pcall + retry, no hardcoded values, frame-rate independence (delta time), no connection leaks. Output: severity-tiered findings with file:line references.
