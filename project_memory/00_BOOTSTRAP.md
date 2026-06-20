# 00_BOOTSTRAP — Your Project AI Recovery Entry Point

**Last updated:** 2026-06-19 (PM hygiene pass per PM_MEMORY_SYSTEM_AUDIT_2026-06-19)
**Purpose:** First file every AI contributor reads before acting. This file is a short pointer, not a replacement for root active docs.

---

## Current Mission

Your Project exists to [describe your mission in one sentence].

**Current priority order:** [define your priority stack — e.g. Ship → Measure → Iterate]

---

## Mandatory Recovery Order

For future AI tasks, **read the relevant role startup file instead of asking the user to repeat a long startup sequence in the prompt**.

1. Read `project_memory/00_BOOTSTRAP.md` — this file.
2. Read `project_memory/FOUNDER_OS.md` — Mandatory single most critical personalization layer (Communication style, tone, decision preferences, and values).
3. Identify `Role=` from the prompt or infer carefully.
4. Read the matching startup file:
   - Builder: `project_memory/startup/STARTUP_BUILDER.md`
   - Auditor: `project_memory/startup/STARTUP_AUDITOR.md`
   - Product Owner: `project_memory/startup/STARTUP_PRODUCT_OWNER.md`
   - Security Reviewer: `project_memory/startup/STARTUP_SECURITY_REVIEWER.md`
   - UX Reviewer: `project_memory/startup/STARTUP_UX_REVIEWER.md`
   - Project Manager: `project_memory/startup/STARTUP_PROJECT_MANAGER.md`
5. Apply the requested prompt mode: `Mode=MINIMAL`, `Mode=STANDARD`, or `Mode=DETAILED`.
6. Read only the additional files required by that startup file and the task.

If no role/mode is provided, default to:

```text
Role=B if implementation is requested, otherwise infer from the task.
For coordination / sprint-planning / status / session-closeout requests, default to `Role=PM`.
Mode=STANDARD unless the task is security/payment/deployment/architecture/financial critical.
```

If tool access exists and the role/mode requires evidence, also review recent commits, deployment status, relevant tests, and live routes before making claims.

---

## Canonical Active Docs

Root active docs remain canonical for human-readable state:

- `STATE_OF_BUILD.md` — live build status and session memory
- `PROJECT_CONTEXT.md` — project overview
- `TASK_QUEUE.md` — active backlog
- `KNOWN_ISSUES.md` — blockers/risks/bugs
- `ROADMAP.md` — roadmap
- `DECISIONS.md` — decision log

`project_memory/active/*` files are AI recovery pointers/summaries and must not drift away from root docs.

## Shared AI Workspace (Organisational Memory)

Cross-role handoffs and scored priorities live in:

- `project_memory/active/AI_MESSAGE_BOARD.md` — structured notes/hand-offs between roles.
- `project_memory/active/PRIORITY_REGISTER.md` — scored backlog (advisory).

Design, permissions, and the mapping to existing canonical files: `project_memory/governance/SHARED_AI_WORKSPACE.md`. Do not duplicate ROADMAP/sprint/decision files.

---

## Current Critical Rules

1. Do not fabricate progress or live verification.
2. Do not expose secrets.
3. Revenue and lead generation come before feature sprawl.
4. Founder remains final decision maker.
5. Use tests/evidence before claiming success.
6. Do not duplicate active memory files.
7. For [Your Frontend Hosting]-connected commits, use:

```bash
git config user.name "your-name"
git config user.email "you@example.com"
```

Never use `builder@arena.ai` for [Your Frontend Hosting]-triggering commits.

---

## Current Known Focus

*Fill this in for your project. List 5-10 founder-confirmed facts that every AI session needs to know — e.g. "Checkout is live at /buy", "Email capture is working", "Database schema v3 is deployed". Keep it factual, update it when things ship.*

---

## Close Session Requirement

Every meaningful session must update, as relevant:

1. `STATE_OF_BUILD.md`
2. `TASK_QUEUE.md`
3. `KNOWN_ISSUES.md`
4. `DECISIONS.md` / `project_memory/DECISIONS_LOG.md` if a decision was made
5. `project_memory/active/*` pointer docs if current state changed
6. `project_memory/session_logs/*`
