# Development Rules — Your Project

**Purpose:** Define when work can be marked complete and how Builder AI should work safely.

---

## Definition of Done

A task is complete only when:

1. implementation exists,
2. relevant tests pass,
3. UI renders if UI changed,
4. route/function works if behaviour changed,
5. docs/memory are updated,
6. no security regression was introduced,
7. deployment is verified if claiming live,
8. founder action is clearly identified if external setup is needed.

---

## QA Workflow

### Before Work

- Read recovery docs.
- Confirm scope.
- Identify tests.
- Identify non-goals.
- Search existing implementation first.

### During Work

- Keep changes minimal.
- Avoid unrelated refactors.
- Add tests for bug fixes.
- Preserve security protections.
- Preserve backward compatibility where practical.

### After Work

For engine code changes, run relevant tests. For core changes, run:

```bash
python -m pytest -ra -q
```

If UI changed:

- render dashboard/page,
- verify labels/buttons,
- verify forms/routes,
- verify mobile if relevant.

If website static pages changed:

```bash
npm run build
node --check shared/layout.js
```

If [Your Frontend Hosting]-connected repo changed, commit with:

```bash
git config user.name "your-project"
git config user.email "info@your-project.co.uk"
```

If security changed:

- run targeted security tests,
- verify public routes,
- verify auth/CSRF behaviour.

If deployment claimed:

- check deployment status,
- check live route,
- record exact evidence.

---

## Completion Labels

Use only:

- Designed, not implemented
- Implemented, not tested
- Tested locally
- Pushed
- Deployed, not verified
- Verified live
- Founder confirmed
- Blocked

---

## Trust & Verification Register Rules

The feature lifecycle source of truth is:

```text
project_memory/active/FEATURE_VERIFICATION_REGISTER.md
```

No feature may be described as “complete” unless its verification register entry shows the appropriate completion level. Use precise lifecycle language:

- **Implemented** means code/docs/assets exist.
- **Tested** means tests or manual local verification were run.
- **Deployed** means a deployment exists or code was pushed to the deployment branch/service.
- **Verified live** means the deployed feature was checked on the live URL/service.
- **Founder confirmed** is useful but distinct from independent verification.
- **Blocked/Regressed** must be recorded when a deployment, route, or behaviour fails.

When a feature changes, update or add its register entry with evidence. If evidence is missing, write “Unknown” or “Pending verification” rather than guessing.
