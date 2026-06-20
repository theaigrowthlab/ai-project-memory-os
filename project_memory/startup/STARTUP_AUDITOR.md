# STARTUP_AUDITOR — Your Project

**Purpose:** Recovery/read sequence for Independent Auditor sessions.

---

## When to Use This Role

Use when the user asks to review, audit, verify, challenge completion, inspect deployment, find risks, score work, or generate a Builder handoff prompt.

## MINIMAL Mode Read Sequence

Use for small, focused tasks.

1. `project_memory/00_BOOTSTRAP.md`
2. `project_memory/FOUNDER_OS.md` (Mandatory Founder Context & Scannable Reporting Style)
3. `project_memory/roles/ROLE_AUDITOR.md`
3. root `PROJECT_CONTEXT.md`
4. root `TASK_QUEUE.md`
5. directly relevant files/docs/routes

## STANDARD Mode Read Sequence

Use by default.

1. all MINIMAL files
2. `project_memory/AI_OPERATING_SYSTEM.md`
3. root `STATE_OF_BUILD.md`
4. root `KNOWN_ISSUES.md`
5. root `ROADMAP.md`
6. `project_memory/active/FEATURE_VERIFICATION_REGISTER.md`
7. relevant implementation files/tests
8. `project_memory/active/AI_MESSAGE_BOARD.md` (check for handoffs addressed to Auditor)
9. `project_memory/active/ACTIVE_ROLE_PROMPTS.md` (current ready-to-execute Auditor prompts)

## DETAILED Mode Read Sequence

Use for audits, strategic decisions, security reviews, financial reviews, major implementation, or crash recovery.

1. all STANDARD files
2. `project_memory/AUDIT_FRAMEWORK.md`
3. root `DECISIONS.md`
4. `project_memory/DECISIONS_LOG.md`
5. `project_memory/governance/CONFLICT_RESOLUTION.md`
6. recent commits
7. deployment evidence
8. test output
9. live routes if checking live claims

## Required Outputs

- executive summary
- evidence reviewed and evidence missing
- what works
- findings/problems
- risks/severity
- priority order
- Builder prompt when requested

## Non-Goals

- no production code changes unless explicitly authorised
- no accepting claims without evidence
- no live verification claims without live checks
- no overclaiming revenue/product maturity

## Escalation Rules

Escalate or pause when:

- critical/high security or deployment risk
- claim cannot be verified
- docs/code/deployment conflict
- founder decision or external platform action required

## Universal Rules

- Repository memory beats chat history.
- Root active docs remain canonical for current state.
- `project_memory/active/*` files are compressed pointers only.
- Use `project_memory/governance/PROMPT_MODES.md` for mode definitions.
- Use `project_memory/active/FEATURE_VERIFICATION_REGISTER.md` before claiming completion/verification.
- Distinguish implemented, tested, pushed, deployed, verified live, and founder confirmed.
- State uncertainty and blockers.
