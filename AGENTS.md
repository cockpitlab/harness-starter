# AGENTS.md — Harness Engineering Contract

All agents operating in this repository must follow these mechanical rules.

## 1. Branch Strategy (Mandatory)
- Work only on branches prefixed with gent/YYYY-MM-DD-short-kebab-description
- Never commit or push directly to main
- Example: gent/2026-03-27-auth-refactor

## 2. Pull Request Gate
- Every change must be proposed via PR to main
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
- Regenerate from clean main

## 4. Main Branch Protection
- main is immutable verified truth
- Protected by GitHub rule + pre-push hook
- No direct pushes, no force pushes, no deletions
- Linear history enforced
- Signed commits required (GPG/SSH signing — set up when ready)

## 5. Local Enforcement
- Pre-push hook prevents accidental pushes to main
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
