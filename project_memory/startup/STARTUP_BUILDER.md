# STARTUP_BUILDER — Your Project

**Purpose:** Recovery/read sequence for Builder AI implementation sessions.

---

## When to Use This Role

Use when the user asks to implement, fix, refactor, update docs, run a scoped build task, close out a task, or continue the highest-priority `TASK_QUEUE.md` item.

## MINIMAL Mode Read Sequence

Use for small, focused tasks.

1. `project_memory/00_BOOTSTRAP.md`
2. `project_memory/FOUNDER_OS.md` (Mandatory Founder Context & Tone Calibration)
3. `project_memory/roles/ROLE_BUILDER.md`
3. root `TASK_QUEUE.md`
4. `project_memory/active/FEATURE_VERIFICATION_REGISTER.md` (Mandatory check before claiming completion)
5. `project_memory/active/AI_MESSAGE_BOARD_DIGEST.md` (Mandatory check for open cross-AI handoffs)
6. directly relevant files for the requested change

## Standardized Handoff & Completion Contracts

All Builder tasks must be executed from a prompt matching `project_memory/governance/BUILDER_PROMPT_TEMPLATE.md`.
All Builder closeouts must deliver an exact 8-part report matching `project_memory/governance/COMPLETION_REPORT_SCHEMA.md` and adhere strictly to completion-label discipline (`Implemented`, `Tested locally`, `Deployed`, `Verified live`, `Founder confirmed`).

## STANDARD Mode Read Sequence

Use by default.

1. `project_memory/00_BOOTSTRAP.md`
2. `project_memory/FOUNDER_OS.md` (Mandatory Founder Context & Tone Calibration)
3. `project_memory/AI_OPERATING_SYSTEM.md`
3. `project_memory/roles/ROLE_BUILDER.md`
4. `project_memory/active/CURRENT_STATE.md`
5. root `PROJECT_CONTEXT.md`
6. root `TASK_QUEUE.md`
7. root `KNOWN_ISSUES.md`
8. relevant specialist docs/files
9. `project_memory/active/AI_MESSAGE_BOARD.md` (check for handoffs addressed to Builder)
10. `project_memory/active/ACTIVE_ROLE_PROMPTS.md` (current ready-to-execute Builder prompts)

## DETAILED Mode Read Sequence

Use for audits, strategic decisions, security reviews, financial reviews, major implementation, or crash recovery.

1. all STANDARD files
2. `project_memory/DEVELOPMENT_RULES.md`
3. `project_memory/active/FEATURE_VERIFICATION_REGISTER.md`
4. root `STATE_OF_BUILD.md`
5. root `ROADMAP.md`
6. root `DECISIONS.md`
7. relevant tests
8. recent commits/deployments if available and relevant

## Required Outputs

- scope understood
- files changed
- tests/validation run with exact results
- docs/memory updated where needed
- risks/blockers
- recommended next action

## Non-Goals

- no strategy pivot without instruction
- no product feature sprawl
- no production code when the sprint is docs-only
- no live/deployed/founder-confirmed claims without evidence

## Escalation Rules

Escalate or pause when:

- credentials/secrets needed
- payment platform/live external platform action needed
- requirements conflict with security or project memory
- task scope is unclear or would require feature expansion

## Universal Rules

- Repository memory beats chat history.
- Root active docs remain canonical for current state.
- `project_memory/active/*` files are compressed pointers only.
- Use `project_memory/governance/PROMPT_MODES.md` for mode definitions.
- Use `project_memory/active/FEATURE_VERIFICATION_REGISTER.md` before claiming completion/verification.
- Distinguish implemented, tested, pushed, deployed, verified live, and founder confirmed.
- State uncertainty and blockers.
