# Agent Registry

**Purpose:** Index of all AI roles / agents in your project and where to find them.

---

## AI Contributor Roles

| Role | Alias | Purpose | Detailed spec |
|---|---|---|---|
| Project Manager | `PM` | Coordinates delivery, maintains status memory, routes work | `roles/ROLE_PROJECT_MANAGER.md` |
| Builder | `B` | Implements approved features | `roles/ROLE_BUILDER.md` |
| Auditor | `A` | Verifies claims with evidence | `roles/ROLE_AUDITOR.md` |
| Product Owner | `PO` | Product direction, user value | `roles/ROLE_PRODUCT_OWNER.md` |
| Security Reviewer | `SR` | Security, auth, data safety | `roles/ROLE_SECURITY_REVIEWER.md` |
| UX Reviewer | `UX` | Accessibility, conversion, mobile | `roles/ROLE_UX_REVIEWER.md` |

Add more roles as your project grows. Each role needs:
- A file in `roles/ROLE_*.md` (authority, boundaries, outputs)
- A file in `startup/STARTUP_*.md` (recovery read order)
- An entry in `AI_ROLES.md`

---

## Role Interaction

The **Project Manager (PM)** is the coordinator — sequences work, maintains status memory, routes tasks.

Handoffs go through `project_memory/active/AI_MESSAGE_BOARD.md`.

See `governance/SHARED_AI_WORKSPACE.md` for the full interaction matrix.

---

## Adding a New Role

1. Create `project_memory/roles/ROLE_<NAME>.md`
2. Create `project_memory/startup/STARTUP_<NAME>.md`
3. Add to `AI_ROLES.md` alias table
4. Add to this registry
5. Update `MASTER_STARTUP_PROMPTS.md` if the role needs a recovery prompt
