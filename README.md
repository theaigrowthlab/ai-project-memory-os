# AI Project Memory OS

**Stop losing context between AI sessions.**

A markdown-based organisational memory system for teams (human or AI) building with Claude, ChatGPT, Gemini, and other LLMs.

Every new AI session goes from "who are you? what's this project?" to productive in 60 seconds — no chat history needed, works across every provider, survives crashes, provider switches, and token limits.

---

## What's inside

| File | Purpose |
|---|---|
| `00_BOOTSTRAP.md` | First file every AI reads — project mission, recovery order, critical rules |
| `FOUNDER_OS_TEMPLATE.md` | How *you* decide, what you value — fill in once, every AI instantly knows how to work with you |
| `AI_OPERATING_SYSTEM.md` | Behavioural constitution — mission, principles, communication standards |
| `AI_ROLES.md` | Role definitions — Builder, Auditor, PM, Product Owner, Security, UX — with authority boundaries |
| `RECOVERY_PROTOCOL.md` | Chat-loss recovery in 7 steps |
| `DEVELOPMENT_RULES.md` | Definition of done, QA workflow, completion labels |
| `MASTER_STARTUP_PROMPTS.md` | Copy-paste recovery prompts per role |
| `DECISIONS_LOG_TEMPLATE.md` | Why you did things — stops re-litigating old decisions |
| `roles/` | Full role playbooks |
| `startup/` | Role-specific recovery read sequences |
| `governance/` | Memory ownership rules, conflict resolution |

Plus templates for: `CURRENT_STATE.md`, `CURRENT_PRIORITIES.md`, `ROADMAP_ACTIVE.md`, `OPEN_ISSUES.md`, `AI_MESSAGE_BOARD.md`, `PRIORITY_REGISTER.md`

---

## Quick start

```bash
# 1. Clone
git clone https://github.com/theaigrowthlab/ai-project-memory-os.git

# 2. Copy into your project
cp -r ai-project-memory-os/project_memory /your-project/

# 3. Fill in YOUR context
# - Copy FOUNDER_OS_TEMPLATE.md → FOUNDER_OS.md and fill it in
# - Edit 00_BOOTSTRAP.md with your mission
# - Add your first 3 decisions to DECISIONS_LOG.md

# 4. Next AI session:
# Role=PM · Mode=STANDARD
# Read project_memory/00_BOOTSTRAP.md and recover state.
```

Done. Your AI now has persistent memory.

---

## How it works

```
New AI session
  ↓
Read 00_BOOTSTRAP.md (30 sec)
  ↓
Read FOUNDER_OS.md (60 sec)
  ↓
Read your role startup file
  ↓
Productive. No "what's this project?" loop.
```

Works with Claude, ChatGPT, Gemini, Grok, Qwen, Kimi — any LLM with file access.

---

## Why markdown files, not a database?

- Survives provider switches — zero migration
- Version controlled in git
- Human readable
- Zero dependencies, zero hosting cost, zero lock-in
- AI-native — LLMs read markdown better than JSON

---
---

## Want the full AI workforce that runs on this memory OS?

This repo is the **memory layer** — the brain.

**The AI Workforce OS Starter Kit** is the full body — 23 AI agents, approval workflows, content pipeline, A/B testing, LLM router, dashboard, 509 tests — everything that actually generates revenue, built on top of this exact memory system.

→ **[Get the AI Workforce OS — £29](https://theaigrowthlab.co.uk/workforce-os)**

Built in public at [The AI Growth Lab](https://theaigrowthlab.co.uk) · MIT licensed · 30-day refund
## License

MIT — use it commercially, modify it, ship it. No attribution required (appreciated).

---

Built originally for a production AI business operating system managing 23 specialised agents. Extracted and generalised after proving it eliminates context loss across 50+ AI sessions and 6 providers.

https://github.com/theaigrowthlab/ai-project-memory-os
