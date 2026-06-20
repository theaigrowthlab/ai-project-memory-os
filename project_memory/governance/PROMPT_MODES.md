# Prompt Modes — Your Project

**Purpose:** Define short prompt modes so future AI sessions can recover safely without the user pasting long startup sequences.

---

## Core Recovery-Depth Modes

### Mode=MINIMAL

Use for small, focused tasks.

Read only:

- `project_memory/00_BOOTSTRAP.md`
- relevant `project_memory/roles/ROLE_*.md`
- current priority/task such as root `TASK_QUEUE.md`
- directly relevant files

### Mode=STANDARD

Use by default.

Read:

- `project_memory/00_BOOTSTRAP.md`
- `project_memory/FOUNDER_OS.md` (mandatory; founder working style: mobile-first, copy-paste-ready, plain English, no overclaiming)
- `project_memory/AI_OPERATING_SYSTEM.md`
- relevant `project_memory/roles/ROLE_*.md`
- compressed current state, if useful
- root `PROJECT_CONTEXT.md`
- root `TASK_QUEUE.md`
- root `KNOWN_ISSUES.md`
- relevant docs/files

### Mode=DETAILED

Use for audits, strategic decisions, security reviews, financial reviews, major implementation, deployment-sensitive work, or crash recovery.

Read all STANDARD context plus:

- root `STATE_OF_BUILD.md`
- root `ROADMAP.md`
- root `DECISIONS.md`
- `project_memory/active/FEATURE_VERIFICATION_REGISTER.md`
- relevant recent commits/deployments/tests if available
- live routes only when live claims require verification and it is safe to check

---

## Topical Operating Modes

Topical modes can be combined with MINIMAL/STANDARD/DETAILED depth. If no depth is specified, use STANDARD unless the task is high-risk.

### Mode=RECOVERY

Use after context crash, provider switch, or uncertain memory. Follow `project_memory/RECOVERY_PROTOCOL.md`, then the relevant startup file.

### Mode=DEPLOYMENT AUDIT

Review commits, deployment status, live route evidence, test status, and verification claims. Use Auditor by default and usually DETAILED depth.

### Mode=SECURITY REVIEW

Review auth, CSRF, CORS, XSS, path traversal, secrets, webhooks, data exposure, and deployment safety. Use Security Reviewer by default and usually DETAILED depth.

### Mode=REVENUE FIRST

Prioritise revenue generation, lead generation, conversion, retention, product proof, customer proof, and offer readiness over feature polish.

### Mode=FOUNDER VIEW

Optimise for founder clarity, time savings, non-technical usability, weekly workflow, and plain-English decisions.

### Mode=WEBSITE AUDIT

Review public website positioning, navigation, CTAs, lead magnet path, checkout safety, legal/trust pages, mobile UX, and conversion path.

### Mode=ENGINE AUDIT

Review app code, dashboard, tests, architecture, integrations, project memory, risks, and false-completion issues.

---

## Role Startup Map

| Alias | Role | Startup file |
|---|---|---|
| `Role=B` | Builder AI | `project_memory/startup/STARTUP_BUILDER.md` |
| `Role=A` | Auditor AI | `project_memory/startup/STARTUP_AUDITOR.md` |
| `Role=RB` | Review Board | `project_memory/startup/STARTUP_REVIEW_BOARD.md` |
| `Role=FRB` | Financial Review Board | `project_memory/startup/STARTUP_FINANCIAL_BOARD.md` |
| `Role=PO` | Product Owner | `project_memory/startup/STARTUP_PRODUCT_OWNER.md` |
| `Role=SR` | Security Reviewer | `project_memory/startup/STARTUP_SECURITY_REVIEWER.md` |
| `Role=UX` | UX Reviewer | `project_memory/startup/STARTUP_UX_REVIEWER.md` |
| `Role=PM` | Project Manager | `project_memory/startup/STARTUP_PROJECT_MANAGER.md` |

---

## Example Prompts

```text
Role=A. Mode=STANDARD. Audit latest deployment and generate next Builder prompt.
```

```text
Role=B. Mode=STANDARD. Continue top TASK_QUEUE priority.
```

```text
Role=FRB. Mode=DETAILED. Update valuation.
```

```text
Role=UX. Mode=Website Audit. Review navigation and conversion.
```

```text
Role=SR. Mode=SECURITY REVIEW. Review checkout/webhook readiness before payments go live.
```

```text
Role=A. Mode=DEPLOYMENT AUDIT. Verify what is implemented, tested, deployed, and live.
```

## Fallback Rule

If no mode is specified, use `Mode=STANDARD`. If a request affects security, payments, deployment, architecture, valuation, or major state recovery, upgrade to `Mode=DETAILED` and state why.
