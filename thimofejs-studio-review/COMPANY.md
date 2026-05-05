---
name: thimofejs-studio-review
description: Idea gate for Thimofej's Game Studio — every game concept passes through here before a single line of Luau is written
slug: thimofejs-studio-review
schema: agentcompanies/v1
version: 1.1.0
---

# Studio Review — Idea Gate

Six agents evaluate every pending game idea before it reaches the build pipeline. Nothing enters build without a GO from the Review Director.

## Pipeline Role

**Input:** Issues with label `idea/pending` in `young-builders/pipeline`
**Output:**
- GO → relabels issue to `idea/approved`, posts full verdict comment
- NO-GO → relabels issue to `idea/rejected`, posts rejection reason with revision suggestions

## Workflow

```
idea/pending issue
       │
       ├─── [wave 1 — parallel] ──────────────────────────┐
       │    tos-guard           → CLEAR / WARN / BLOCK     │
       │    competitor-analyst  → clone risk + gap         │
       │    sentiment-analyst   → POSITIVE/NEUTRAL/NEG     │
       │                                                   │
       ├─── [hard veto check] ─────────────────────────────┤
       │    BLOCK or clone_risk > 0.70 → immediate NO-GO   │
       │                                                   │
       └─── [wave 2 — parallel, only if no hard veto] ────►│
            strategy-agent         → 30-point scorecard    │
            viral-mechanic-designer → viral hook score     │
                                                           │
                             review-director synthesizes ◄─┘
                             → GO or NO-GO verdict posted
```

**Hard vetoes (immediate NO-GO, cannot be overridden):**
- `tos-guard` returns BLOCK
- `competitor-analyst` returns `clone_risk_score > 0.70`

## Verdict Comment Format

```markdown
## Review Verdict

**Decision:** GO / NO-GO
**Date:** YYYY-MM-DD
**Reviewer:** review-director

### Sub-Agent Summary
- **tos-guard:** CLEAR / WARN / BLOCK — <finding>
- **competitor-analyst:** <score> clone risk — <top gap found>
- **sentiment-analyst:** POSITIVE / NEUTRAL / NEGATIVE — <signal>
- **strategy-agent:** <total>/30 (PASS/FAIL) — <key factor>
- **viral-mechanic-designer:** HOOK FOUND / NO HOOK — <hook or gap>

### Reasons
- ...

### Conditions (if GO)
- ...
```

## Agents

| Agent | Role | Model |
|-------|------|-------|
| review-director | Final GO/NO-GO authority, orchestrates all sub-agents | Opus |
| tos-guard | Roblox ToS compliance — 5 hard checks | Sonnet |
| competitor-analyst | Clone risk score (0–1.0) + mechanic gap | Sonnet |
| sentiment-analyst | r/roblox genre fatigue scan — POSITIVE/NEUTRAL/NEGATIVE | Sonnet |
| strategy-agent | 30-point scorecard (Trend / Differentiation / Feasibility) | Sonnet |
| viral-mechanic-designer | Viral hook assessment — does idea have a TikTok moment? | Sonnet |

## Rules

- `tos-guard` BLOCK = unconditional NO-GO, no override
- `competitor-analyst` clone_risk_score > 0.70 = unconditional NO-GO
- `review-director` is the only agent that relabels issues and posts the verdict comment
- All wave-1 reports must arrive before wave-2 agents are dispatched
- All 5 sub-agent reports must be present before verdict is rendered (unless a hard veto ends early)
- Rejected ideas get full written reasons + revision suggestions — no silent drops

## Secrets Required

- `GH_TOKEN` — GitHub token (repo + issues scope) for `young-builders/pipeline`
- `REDDIT_CLIENT_ID` / `REDDIT_CLIENT_SECRET` — for sentiment-analyst's r/roblox scanning
