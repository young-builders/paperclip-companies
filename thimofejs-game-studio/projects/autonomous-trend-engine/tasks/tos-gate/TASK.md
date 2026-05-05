---
name: TOS Gate Implementation
description: Implement tos-guard automated checks — title, thumbnail, similarity score, asset licensing, monetization — block deploy on any failure
owner: tos-guard
---

Implement automated TOS gate: (1) title trademark check (blocklist of known IP), (2) thumbnail content check, (3) mechanic similarity score calculation and ≥70% hard block, (4) asset license API verification for every asset ID in AssetConfig.lua, (5) monetization policy validation. Gate must be hard — no deploy-engineer call without APPROVED output.
