# thimofejs-studio-review

Gatekeeper. Reviews every idea before it reaches build. Nothing passes without approval.

## Pipeline Role

**Input:** `$PIPELINE_PATH/ideas/pending/<idea-slug>.md`
**Output:**
- Approved → moves file to `$PIPELINE_PATH/ideas/approved/<idea-slug>.md`
- Rejected → moves file to `$PIPELINE_PATH/ideas/rejected/<idea-slug>.md` with rejection reason appended

## Workflow

1. `tos-guard` checks idea against Roblox ToS — hard block if violation
2. `sentiment-analyst` checks public sentiment around this game type
3. `strategy-agent` evaluates strategic fit: market timing, differentiation, effort vs. reward
4. `review-director` makes final GO / NO-GO decision, appends verdict, moves file

## Verdict Format (appended to idea file)

```markdown
## Review Verdict

**Decision:** GO / NO-GO
**Date:** YYYY-MM-DD
**Reviewer:** review-director

### Reasons
- ...

### Conditions (if GO)
- Any constraints for build team
```

## Agents

| Agent | Role | Model |
|-------|------|-------|
| review-director | Final GO/NO-GO authority | Opus |
| strategy-agent | Strategic fit evaluation | Sonnet |
| tos-guard | Roblox ToS compliance check | Sonnet |
| sentiment-analyst | Public sentiment check | Sonnet |

## Rules

- `tos-guard` veto = automatic NO-GO, no override
- `review-director` is the only agent that moves files between folders
- Rejected ideas get a full written reason — no silent drops
