# Decisions Log

**Purpose:** Permanent record of significant decisions — why they were made, what the alternatives were, who decided. Prevents re-litigating old decisions after chat loss.

**Convention:** newest first. Never delete — superseded decisions get marked `Superseded` with a link to the replacement.

---

## Template

```markdown
### D-001 — [Short decision title]

**Date:** YYYY-MM-DD
**Decided by:** [Founder / PM / PO / etc.]
**Status:** Adopted | Proposed | Superseded by D-XXX

**Decision:** [one sentence — what was decided]

**Context:** [2-3 sentences — what problem were we solving?]

**Options considered:**
1. [Option A] — [pros / cons]
2. [Option B] — [pros / cons]
3. [Option C] — [pros / cons]

**Rationale:** [why this option, why not the others]

**Consequences:**
- Positive: […]
- Negative / trade-offs: […]
- Reversible? [Yes / No / Costly]

**Related:** [links to issues, PRs, docs]
```

---

## Example Decisions

### D-001 — Use Markdown Files for AI Memory (not a database)

**Date:** 2025-01-15
**Decided by:** Founder
**Status:** Adopted

**Decision:** Store all AI organisational memory as markdown files in the git repo, not in a database or external SaaS.

**Context:** AI chat sessions kept losing context. Needed persistent memory that survives provider switches (Claude → ChatGPT → Gemini).

**Options considered:**
1. **Markdown in git** — version controlled, human readable, zero dependencies, AI-native
2. **Vector database** — better semantic search, but adds infrastructure + cost + lock-in
3. **Notion / external wiki** — nice UI, but another account to manage, API rate limits

**Rationale:** Markdown files are the simplest thing that works. LLMs read markdown natively better than JSON. Git gives us version history free. Zero vendor lock-in. Can migrate to a database later if we outgrow files — but we probably won't for <100k tokens of memory.

**Consequences:**
- Positive: works across every LLM provider, zero cost, full audit trail
- Negative: no semantic search, manual curation needed
- Reversible? Yes — can export to DB anytime

---

### D-002 — Revenue > Features

**Date:** 2025-01-20
**Decided by:** Founder
**Status:** Adopted

**Decision:** Revenue-generating work always outranks feature work in the backlog. No exceptions without founder override.

**Context:** Early versions kept adding dashboard polish and new agents while having zero customers. Feature sprawl without revenue is existential risk for a solo founder.

**Rationale:** A business with ugly software and paying customers survives. A business with beautiful software and zero customers dies.

**Consequences:**
- Positive: forces ruthless prioritisation
- Negative: some quality-of-life features get deferred longer than comfortable
- Reversible? Yes — founder can override per item

---

### D-003 — [Your decision here]

Copy the template above.

---

*Add decisions as they happen. The cost of NOT recording a decision is re-having the same argument 3 weeks later with zero memory of why you chose what you chose.*
