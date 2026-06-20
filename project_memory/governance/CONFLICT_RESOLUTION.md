# Conflict Resolution — Your Project

**Purpose:** Define what to do when project memory, code, tests, deployments, or user claims conflict.

---

## Required Conflict Hierarchy

If documents or claims conflict:

1. Live evidence wins.
2. Tests/deployment evidence wins over claims.
3. Latest root canonical docs win over stale docs.
4. `project_memory/active/FEATURE_VERIFICATION_REGISTER.md` controls completion/verification status.
5. Founder instruction wins over AI preference.
6. Unresolved conflicts must be reported.

Founder instruction can override product priority, but not security, credential safety, payment safety, legal/trust constraints, or verified technical impossibility.

## Evidence Hierarchy

1. Live verified behaviour, when safely checked.
2. Local tests and reproducible commands.
3. Current repository code at HEAD.
4. Latest canonical root docs.
5. Feature Verification Register for lifecycle/completion status.
6. Project-memory specialist docs.
7. Session logs and historical summaries.
8. Chat history and unaudited claims.

## Root vs Project Memory

- Root active docs are canonical for current project state.
- `project_memory/active/*` files are compressed pointers.
- Specialist docs may be older than root docs unless explicitly marked as current strategic memory.

## Decision Log Conflicts

Use this hierarchy:

1. root `DECISIONS.md` = canonical active decision log.
2. `project_memory/DECISIONS_LOG.md` = governance-format structured index / future migration target.
3. `project_memory/DECISION_LOG.md` = legacy detailed decision log retained for history.

Do not delete or overwrite decision history just to remove confusion. Mark superseded decisions clearly.

## Implementation Claim Rules

- "Implemented" means files/code/docs changed.
- "Tested" means specific tests/validation were run and results recorded.
- "Pushed" means a Git commit was pushed to the remote branch.
- "Deployed" means the hosting platform built/released the commit.
- "Verified live" means a live route/system was checked after deployment.
- "Founder confirmed" means the founder explicitly reported PASS/approval.

Do not collapse these into one status.

## When Conflict Is Found

1. State the conflicting sources.
2. State which source currently wins and why.
3. Update docs only if instructed or if the session scope includes memory maintenance.
4. If unresolved, report uncertainty in the final response and, when appropriate, in `KNOWN_ISSUES.md` or the session log.

## Safety Override

If a requested action conflicts with security, credential safety, payment safety, privacy, or legal/trust claims, pause and escalate rather than guessing.
