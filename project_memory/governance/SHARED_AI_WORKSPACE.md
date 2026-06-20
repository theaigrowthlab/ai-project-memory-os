# Shared AI Workspace — Persistent Organisational Memory

**Purpose:** A persistent communication + memory layer so Your Project's AI roles can leave structured notes, recommendations, and hand-offs for each other — **organisational memory, not chat memory.** Survives session loss and provider switches.

**Owner:** Project Manager (`Role=PM`). PM maintains the workspace; all roles read it; update rights are file-specific (below).
**Status:** Implemented (docs-only) — decision D-047.

---

## 1. Design Principle: Files, Not a New System

The workspace is **a governed set of existing + new repository files**, not a separate database or app. It rides on the recovery layer that already exists (`00_BOOTSTRAP.md`, `RECOVERY_PROTOCOL.md`, startup files), so recovery after chat loss is free.

This also means it must obey `project_memory/governance/MEMORY_OWNERSHIP_RULES.md`: **no duplicate active-state files.**

---

## 2. File Mapping — Proposed vs Actual

The audit proposed five files. Three already exist under other names; only two are genuinely new. Mapping (to avoid duplication):

| Audit proposed | Actual repo file | Status | Notes |
|---|---|---|---|
| `AI_MESSAGE_BOARD.md` | `project_memory/active/AI_MESSAGE_BOARD.md` | **NEW** | Cross-role handoffs/blockers/recommendations. Genuinely missing. |
| `PRIORITY_REGISTER.md` | `project_memory/active/PRIORITY_REGISTER.md` | **NEW** | Scored, rankable backlog (complements, does not replace, canonical `TASK_QUEUE.md`). |
| `AI_DECISIONS.md` | `DECISIONS.md` + `project_memory/DECISIONS_LOG.md` | **MAPPED — no new file** | 3-tier decision hierarchy already exists (root canonical → governance index → legacy). AI-raised decisions use the AI-decision convention below. |
| `ACTIVE_SPRINT.md` | `project_memory/CURRENT_SPRINT.md` | **MAPPED — no new file** | Already the sprint board; now includes the PM Sprint Plan. |
| `ROADMAP.md` | `ROADMAP.md` (root) + `project_memory/active/ROADMAP_ACTIVE.md` | **MAPPED — no new file** | Root is canonical; pointer is for AI recovery. All roles already read it. |

> **Why not create the three "mapped" files:** creating `project_memory/ROADMAP.md`, `AI_DECISIONS.md`, or a second sprint file would directly violate `MEMORY_OWNERSHIP_RULES.md → "No Duplicate Active-State Files"` and recreate the exact drift problem the audit is meant to solve.

---

## 3. Permissions

**Read:** Every role may read every workspace file. (Recovery already mandates this.)

**Update (write) by file:**

| File | Who may write | Convention |
|---|---|---|
| `AI_MESSAGE_BOARD.md` | Any role (append a structured entry) | PM curates/archives. See §4. |
| `PRIORITY_REGISTER.md` | PM maintains scores; PO/Founder may re-rank; roles may request a re-score | PM keeps scores honest; score ≠ final order (Founder/PO decide). |
| `DECISIONS.md` / `DECISIONS_LOG.md` | PM/Auditor/Builder log decisions; Founder adopts/reverses | AI-raised decisions are **Proposed** until Founder marks **Adopted**. |
| `CURRENT_SPRINT.md` | PM owns the execution view; roles update only their routed item's status label | Precise completion labels only. |
| `ROADMAP.md` | Founder/PO/Review Board | PM reflects approved changes into sprint/register. |

**Governance control:** No role may *unilaterally* change strategy, enable payments/publishing, override a security verdict, or mark something "complete" without evidence. PM enforces this; unresolved disputes escalate per `project_memory/governance/CONFLICT_RESOLUTION.md`.

---

## 4. How a Role Leaves a Message (AI_MESSAGE_BOARD convention)

Append one entry per handoff, using this block:

```text
### [YYYY-MM-DD HH:MM] From: <Role> · To: <Role or ALL> · Type: handoff|blocker|decision-needed|recommendation|info
- Context: one line.
- Finding / recommendation: one line.
- Action requested + owner: one line.
- Links: file/commit/route if any.
- Status: open|in-progress|resolved|blocked
```

**Rules:**
- Messages are **evidence-based** (link a file/commit/route) — not opinions without basis.
- `decision-needed` entries must also be reflected in `DECISIONS.md` as **Proposed**.
- PM resolves/archives threads at session close or weekly (move to `project_memory/session_logs/`).
- No secrets, no live-verification claims without a checked route.

---

## 5. Archival

- Resolved/closed message-board threads: PM moves them into `project_memory/session_logs/AI_MESSAGE_BOARD_ARCHIVE_<YYYY-MM>.md` at month end (or when the board exceeds ~25 open threads).
- Decisions are **never deleted** — superseded decisions are marked `Superseded` and linked to the replacement (per `DECISIONS_LOG.md` rule).
- Sprint/register history: keep a rolling current view; prior detail lives in `STATE_OF_BUILD.md` session notes and session logs.

---

## 6. Governance Controls (anti-sprawl / anti-drift)

1. **Single source of truth per concern** — one roadmap, one backlog, one decision log. The two new files *add capability* (cross-role memory + scoring), they do not fork state.
2. **PM owns consistency** — detects drift between register/queue/sprint/roadmap and reconciles per `RECOVERY_PROTOCOL.md → Step 4` (prefer latest evidence → root active docs → tests).
3. **Scores are advisory** — `PRIORITY_REGISTER.md` informs, never overrides, Founder/PO product authority.
4. **Recovery-checked** — every startup file's read sequence must include the files its role needs from this workspace.
5. **No app, no migration debt** — pure markdown; survives provider switches with zero engineering.

---

## 7. Success-Criteria Check (vs the audit)

| Audit success criterion | How this workspace meets it |
|---|---|
| Reduced prompt size | Roles post to the board instead of re-explaining context. |
| Improved continuity | Org memory survives chat loss; new sessions read the board in recovery. |
| Better roadmap governance | Priority register + PM roadmap ownership + roadmap→sprint reflection. |
| Reduced feature creep | Priority scoring + anti-sprawl controls + PM triage gate. |
| Persistent organisational memory | `AI_MESSAGE_BOARD.md` is exactly this. |
| Faster recovery after AI session loss | Files ride the existing recovery protocol. |
| Improved multi-AI collaboration | Structured handoffs + role-interaction matrix in `ROLE_PROJECT_MANAGER.md`. |
