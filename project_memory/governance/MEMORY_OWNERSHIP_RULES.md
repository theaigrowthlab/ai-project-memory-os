# Memory Ownership Rules — Your Project

**Purpose:** Prevent duplicate state files, drift, stale AI memory, and unclear update authority.

---

## Canonical Root Docs

Root docs are canonical for active human-readable project state:

- `PROJECT_CONTEXT.md` — concise current project overview
- `STATE_OF_BUILD.md` — live build/session memory
- `TASK_QUEUE.md` — active backlog and priorities
- `KNOWN_ISSUES.md` — blockers, bugs, risks
- `ROADMAP.md` — roadmap and sequencing
- `DECISIONS.md` — canonical active decision log
- `ARCHITECTURE.md` — active architecture overview
- `GO_LIVE_RUNBOOK.md` — deployment/go-live guide
- `PC_TODO_LOG.md` — founder tasks

## Project Memory Purpose

`project_memory/` is for:

- AI recovery instructions and startup routing
- role definitions
- governance rules and prompt modes
- compressed active pointers
- specialist reference docs
- verification/experiment registers
- session logs and rollups
- audit/strategy/architecture/operations references

It must not become a duplicate active-state system.

## No Duplicate Active-State Files

Do not create duplicate active files such as:

- `project_memory/STATE_OF_BUILD.md`
- `project_memory/TASK_QUEUE.md`
- `project_memory/KNOWN_ISSUES.md`
- `project_memory/ROADMAP.md`
- `project_memory/PROJECT_CONTEXT.md`
- multiple dated weekly rollups
- alternate root context files with overlapping authority
- a second sprint file, second roadmap, or second decision log (the Shared AI Workspace reuses the existing `CURRENT_SPRINT.md`, `ROADMAP.md`, and `DECISIONS.md` — see `governance/SHARED_AI_WORKSPACE.md`)

## When to Update Which Files

| Change type | Update |
|---|---|
| Current status/session result changed | root `STATE_OF_BUILD.md` |
| Backlog priority/status changed | root `TASK_QUEUE.md` |
| Bug/risk/blocker changed | root `KNOWN_ISSUES.md` |
| Strategic/architectural/product decision made | root `DECISIONS.md`; optionally `project_memory/DECISIONS_LOG.md` for governance index |
| Completion/verification status changed | `project_memory/active/FEATURE_VERIFICATION_REGISTER.md` |
| Experiment status changed | `project_memory/active/EXPERIMENT_REGISTRY.md` |
| Compressed recovery pointer changed | relevant `project_memory/active/*` file |
| Cross-role handoff/blocker/recommendation | `project_memory/active/AI_MESSAGE_BOARD.md` |
| Priority score / ranking changed | `project_memory/active/PRIORITY_REGISTER.md` (advisory; `TASK_QUEUE.md` remains canonical) |
| Session summary/rollup needed | `project_memory/session_logs/*` and/or `project_memory/history/MONTHLY_ROLLUP.md` |
| Role, startup, authority, prompt mode changed | `project_memory/startup/*`, `project_memory/roles/*`, or `project_memory/governance/*` plus README/index |

## Ownership by Role

| Role | Memory ownership |
|---|---|
| Builder | Updates docs/registers for implemented scoped work and closeout evidence. |
| Auditor | May create/update audit reports and recommend corrections; should not alter production code unless explicitly asked. |
| Review Board | May recommend strategy/roadmap updates; founder/product owner approval needed for major pivots. |
| Financial Board | May update valuation/revenue analysis docs when asked; must label assumptions. |
| Product Owner | May prioritise backlog and clarify product decisions; founder remains final authority. |
| Security Reviewer | May update security findings/risks and block unsafe deployment recommendations. |
| UX Reviewer | May recommend UX/copy/conversion updates; implementation requires Builder or explicit instruction. |
| Project Manager | Maintains sprint/priority/status memory, the AI message board, priority register, routing, scope discipline, and session closeout. |

## Decision Logs

Authority hierarchy:

1. root `DECISIONS.md` = canonical active decision log.
2. `project_memory/DECISIONS_LOG.md` = governance-format structured decision log / future migration target.
3. `project_memory/DECISION_LOG.md` = legacy detailed decision log, retained for history unless carefully migrated.

Prefer clarification over deletion. Preserve all decision content.

## Close Session Rule

At session close, update only files whose facts changed. Prefer concise entries over copying large sections between files.
