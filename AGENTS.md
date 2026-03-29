# AGENTS.md — Harness Engineering Contract

All agents operating in this repository must follow these mechanical rules. This file is the **central table of contents** for the repo (per `.cursor/rules/harness-engineering.mdc`); `README.md` is the human-facing overview.

## Repository structure

- `.cursor/rules/harness-engineering.mdc` — Governing Harness rules (always applied; priority 100)
- `.cursor/rules/` — Additional rules (`devops-rules.mdc`, `testing-rules.mdc`, `example-project-rules.mdc`, …)
- `.cursor/skills/` — Reusable agent skills (e.g. `research-landscape`)
- `.cursor/hooks/` — Optional Cursor hooks (checklists, agent review on commit)
- `.githooks/pre-push` — Local guard against accidental push to `main`
- `.github/workflows/` — CI harness (`ci/lint`, `ci/tests`, `ci/simulations`)
- `SOUL.md` — Agent persona, tone, and behavioral boundaries
- `docs/` — Machine-readable plans, handoffs, and generated artifacts (structured markdown or JSON)
  - `docs/rollback-playbook.md` — Recovery and rollback procedures
  - `docs/symphony-integration.md` — Symphony orchestration integration
  - `docs/hooks.md` — Configuring hooks in Cursor
  - `docs/checklists/` — Pre-plan and post-execution checklists
  - `docs/autonomy-grants/` — Written autonomy approvals (when used)
  - `docs/autonomy-levels.md` — L0–L4 autonomy reference
  - Add under `docs/` as the project grows (e.g. `design-docs/`, `exec-plans/`, `references/`, `runbooks/`)
- `AGENTS.md` — This file: mechanical contract + repository map (update after major changes)

## 1. Branch Strategy (Mandatory)
- Work only on branches prefixed with `agent/YYYY-MM-DD-short-kebab-description` (normal changes) or `fix/YYYY-MM-DD-short-kebab-description` (recovery and rollback — see `docs/rollback-playbook.md`).
- Never commit or push directly to `main`
- Example: `agent/2026-03-27-auth-refactor`

## 2. Pull Request Gate
- Every change must be proposed via PR to `main`
- PR must include:
  - Clear intent summary
  - What changed
  - Expected behavior
- Full harness (ci/lint + ci/tests + ci/simulations) must pass
- At least 1 human approval required
- All conversations must be resolved

## 3. Failure Policy (Critical)
- If any check fails (test, simulation, lint, human review): delete the branch entirely
- Never "fix in place" on a failing branch
- Regenerate from clean `main`
- Use the §1 prefixes (`agent/...` or `fix/...`); deleting a branch under this policy is for **failed** checks on that branch, not for a naming typo by itself.

## 4. Main Branch Protection
- `main` is immutable verified truth
- Protected by GitHub rule + pre-push hook
- No direct pushes, no force pushes, no deletions
- Linear history enforced
- Signed commits required (GPG/SSH signing — set up when ready)

## 5. Local Enforcement
- Pre-push hook prevents accidental pushes to `main`
- Use ALLOW_MASTER_PUSH=true git push only in true emergencies

## 6. Symphony Readiness
- This repo is now fully machine-legible
- Parallel agents can propose changes safely
- All proposals are independently validated by the harness before any orchestration

## 7. General Rules
- Terminal output shared with agents should be copied as clean text (screenshots are acceptable fallback)
- All agent actions must respect the controlled execution surface
- Bad branches are deleted, never accumulated
- Read SOUL.md before every session — it defines agent persona and behavioral boundaries

Violating this contract results in immediate branch deletion.
