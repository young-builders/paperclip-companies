# thimofejs-studio-review

Gatekeeper. Reviews every idea before it reaches build. Nothing passes without approval.

## Pipeline Role

**Input:** Issues with label `idea/pending` in `young-builders/pipeline`
**Output:**
- Approved → relabels Issue to `idea/approved`, posts verdict as comment
- Rejected → relabels Issue to `idea/rejected`, posts rejection reason as comment

## Workflow

1. `tos-guard` checks idea against Roblox ToS — hard block if violation
2. `sentiment-analyst` checks public sentiment around this game type
3. `strategy-agent` evaluates strategic fit: market timing, differentiation, effort vs. reward
4. `review-director` makes final GO / NO-GO decision, posts verdict comment, relabels Issue

## Verdict Comment Format (posted on the Issue)

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
- `review-director` is the only agent that relabels Issues and posts the verdict comment
- Rejected ideas get a full written reason as a comment — no silent drops

## Secrets Required

- `GH_TOKEN` — GitHub token (repo + issues scope) for reading and relabeling Issues in young-builders/pipeline
