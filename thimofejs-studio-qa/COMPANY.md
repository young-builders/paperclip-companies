# thimofejs-studio-qa

Tests builds before release. Finds bugs, exploits, performance issues, ToS violations.

## Pipeline Role

**Input:** PRs with linked pipeline Issue labeled `build/pending-qa` in `young-builders/games`
**Output:**
- Pass → approves PR in young-builders/games, relabels pipeline Issue to `qa/passed`, posts QA report as PR comment
- Fail → requests-changes on PR in young-builders/games, relabels pipeline Issue to `build/in-progress`, posts bug report as PR comment

## Workflow

1. `qa-lead` reads PR description + `BUILD.md`, plans test scope
2. `qa-tester` executes test checklist (gameplay, edge cases, DataStore, UI)
3. `performance-analyst` checks server fps, memory, load times
4. `anti-exploit-engineer` probes for RemoteEvent abuse, client authority bugs
5. `system-auditor` checks code quality, DataStore safety, error handling
6. `qa-lead` compiles results → PASS or FAIL → approves or requests-changes on PR, relabels pipeline Issue accordingly

## QA Report Format (posted as PR comment)

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
- Failed builds: `qa-lead` requests-changes on the PR and relabels pipeline Issue to `build/in-progress` — `studio-build` fixes on the same PR branch
- `qa-lead` is the only agent that approves/requests-changes on PRs and relabels pipeline Issues

## Secrets Required

- `GH_TOKEN` — GitHub token (repo + pull_requests + issues scope) for reviewing PRs in young-builders/games and relabeling Issues in young-builders/pipeline
