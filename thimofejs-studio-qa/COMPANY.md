# thimofejs-studio-qa

Tests builds before release. Finds bugs, exploits, performance issues, ToS violations.

## Pipeline Role

**Input:** `$PIPELINE_PATH/builds/pending-qa/<idea-slug>/`
**Output:**
- Pass → moves to `$PIPELINE_PATH/builds/passed/<idea-slug>/` with QA report
- Fail → moves to `$PIPELINE_PATH/builds/failed/<idea-slug>/` with bug report

## Workflow

1. `qa-lead` reads `BUILD.md`, plans test scope
2. `qa-tester` executes test checklist (gameplay, edge cases, DataStore, UI)
3. `performance-analyst` checks server fps, memory, load times
4. `anti-exploit-engineer` probes for RemoteEvent abuse, client authority bugs
5. `system-auditor` checks code quality, DataStore safety, error handling
6. `qa-lead` compiles results → PASS or FAIL → moves folder

## QA Report Format (appended to BUILD.md)

```markdown
## QA Report

**Decision:** PASS / FAIL
**Date:** YYYY-MM-DD

### Test Results
| Area | Status | Notes |
|------|--------|-------|
| Gameplay | ✅/❌ | ... |
| Performance | ✅/❌ | ... |
| Anti-exploit | ✅/❌ | ... |
| DataStore | ✅/❌ | ... |
| UI/UX | ✅/❌ | ... |

### Bugs Found
- [CRITICAL/HIGH/LOW] Description

### Conditions for Release (if PASS)
- Any known minor issues ops should monitor
```

## Agents

| Agent | Role |
|-------|------|
| qa-lead | Test planning + final verdict |
| qa-tester | Functional + regression testing |
| performance-analyst | Server FPS, memory, latency |
| anti-exploit-engineer | Exploit probing, RemoteEvent security |
| system-auditor | Code quality, DataStore integrity |

## Rules

- CRITICAL bug = automatic FAIL, no exceptions
- Failed builds go back to studio-build with full bug report
- qa-lead is the only agent that moves folders
