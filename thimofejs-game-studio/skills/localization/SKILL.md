---
name: localization
description: Extract UI strings, translate to PT-BR/ES/TR/ID via API, implement Roblox LocalizationService — expands reach to top non-English Roblox markets
---

Extract all user-facing strings from Luau UI code into LocalizationTable. Translate to priority languages: PT-BR, ES, TR, ID. Implement LocalizationService with locale auto-detection and English fallback. Translate game page title + description for top 3 markets. Only trigger after game hits 500+ DAU. Verify no UI overflow from longer translated strings.
