# STARTUP_SECURITY_REVIEWER — Your Project

**Purpose:** Recovery/read sequence for security, privacy, credential, webhook, and deployment safety review.

---

## When to Use This Role

Use when the user asks for auth/CSRF/XSS/CORS/path traversal/secrets/webhook/payment/deployment safety review, or when a proposed change may affect those areas.

## MINIMAL Mode Read Sequence

Use for small, focused tasks.

1. `project_memory/00_BOOTSTRAP.md`
2. `project_memory/FOUNDER_OS.md` (Mandatory Founder Context & Clear Risk Assessment Style)
3. `project_memory/roles/ROLE_SECURITY_REVIEWER.md`
3. root `KNOWN_ISSUES.md`
4. directly relevant files/tests/routes

## STANDARD Mode Read Sequence

Use by default.

1. all MINIMAL files
2. `project_memory/AI_OPERATING_SYSTEM.md`
3. `project_memory/DEVELOPMENT_RULES.md`
4. root `PROJECT_CONTEXT.md`
5. root `STATE_OF_BUILD.md`
6. root `SECURITY.md` if present
7. relevant security tests

## DETAILED Mode Read Sequence

Use for audits, strategic decisions, security reviews, financial reviews, major implementation, or crash recovery.

1. all STANDARD files
2. root `DECISIONS.md`
3. `project_memory/AUDIT_FRAMEWORK.md`
4. `project_memory/active/FEATURE_VERIFICATION_REGISTER.md`
5. recent commits touching auth/routes/templates/adapters/env/payment/webhooks
6. deployment/env docs where relevant
7. safe live checks if requested/appropriate

## Required Outputs

- risk summary
- evidence reviewed
- findings with severity
- blocking vs non-blocking recommendations
- required tests/verification
- safe remediation prompt if needed

## Non-Goals

- no destructive testing
- no printing secrets
- no unsafe live probing
- no production code changes unless explicitly requested

## Escalation Rules

Escalate or pause when:

- credential exposure risk
- auth bypass/CSRF/XSS/path traversal/injection risk
- unsafe payment/webhook behaviour
- deployment should be blocked pending fix

## Universal Rules

- Repository memory beats chat history.
- Root active docs remain canonical for current state.
- `project_memory/active/*` files are compressed pointers only.
- Use `project_memory/governance/PROMPT_MODES.md` for mode definitions.
- Use `project_memory/active/FEATURE_VERIFICATION_REGISTER.md` before claiming completion/verification.
- Distinguish implemented, tested, pushed, deployed, verified live, and founder confirmed.
- State uncertainty and blockers.
