# Recovery Protocol — Your Project

**Purpose:** Allow any new AI instance to recover project state quickly after a crash, provider switch, context loss, or short prompt.

---

## Critical Anti-Hallucination Rules

- If uncertain, explicitly say what is uncertain.
- Never invent completed systems.
- Never assume implementation — inspect files/code/deployments.
- Chat history is secondary; repository memory is primary.
- Never fabricate progress.
- Never claim live verification unless a live route/deployment was checked.

---

## Step 1 — Identify Role

Read the user prompt for a role alias:

- `Role=B` Builder
- `Role=A` Auditor
- `Role=PO` Product Owner
- `Role=SR` Security Reviewer
- `Role=UX` UX Reviewer
- `Role=PM` Project Manager

If no role is provided, infer carefully:

- implementation request → Builder,
- review/verify request → Auditor,
- - UX/mobile/conversion review → UX Reviewer.
- coordination / sprint planning / status / closeout request → Project Manager.

---

## Step 2 — Select Prompt Mode and Startup File

Use `project_memory/governance/PROMPT_MODES.md` and the relevant role startup file:

- `project_memory/startup/STARTUP_BUILDER.md`
- `project_memory/startup/STARTUP_AUDITOR.md`
- `project_memory/startup/STARTUP_REVIEW_BOARD.md`
- `project_memory/startup/STARTUP_FINANCIAL_BOARD.md`
- `project_memory/startup/STARTUP_PRODUCT_OWNER.md`
- `project_memory/startup/STARTUP_SECURITY_REVIEWER.md`
- `project_memory/startup/STARTUP_UX_REVIEWER.md`
- `project_memory/startup/STARTUP_PROJECT_MANAGER.md`

If no mode is specified, use `Mode=STANDARD`. Long pasted startup sequences are no longer required when a prompt includes `Role=` and `Mode=`.

Upgrade to `Mode=DETAILED` when the task affects security, payments, deployment, architecture, valuation, or major state recovery.

---

## Step 3 — Determine Current Truth

Classify:

- current repo HEAD,
- latest deployment,
- test status,
- active blockers,
- current top priority,
- current founder-confirmed facts.

---

## Step 4 — Check for Conflicts

If docs conflict:

1. prefer latest evidence,
2. prefer root active docs over archived/specialist docs,
3. prefer tests/deployments/live checks over claims,
4. flag unresolved conflicts.

---

## Step 5 — Summarise Before Acting

Every recovered AI should state:

- current phase,
- current top priority,
- known blockers,
- what it will do next,
- what it will not do.

---

## Step 6 — Execute Within Role Limits

Follow the dedicated role file in `project_memory/roles/`, the selected startup file in `project_memory/startup/`, and `project_memory/DEVELOPMENT_RULES.md` completion standards.

---

## Step 7 — Close Session

Update relevant memory files and produce evidence.

Minimum closeout for meaningful work:

- `STATE_OF_BUILD.md`,
- `TASK_QUEUE.md` if task status changed,
- `KNOWN_ISSUES.md` if issue status changed,
- `DECISIONS.md` / `project_memory/DECISIONS_LOG.md` if decision was made,
- `project_memory/session_logs/*`.
