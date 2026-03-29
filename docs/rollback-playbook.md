# Rollback Playbook (Harness Engineering)

## Never

- Force push to `main` (or any protected branch)
- Push or commit directly to `main`
- Hotfix or rollback without a full PR + full harness validation
- Rewrite history on `main`

## Core Principles

- `main` must always remain **clean, verified truth** (passing lint, tests, and simulations).
- Bad changes are **never fixed in place** on `main`.
- All recovery must go through the **same gated process** as normal changes: branch → PR → full harness → human approval → squash merge.
- Bad branches are deleted after successful recovery.

## Safe Rollback Process

1. Inspect history

   ```bash
   git log --oneline --graph --decorate --all
   git reflog
   ```

2. Start from clean `main`

   ```bash
   git checkout main
   git pull origin main
   ```

3. Create rescue branch (snapshot of incident state)

   ```bash
   git checkout -b rescue/$(date +%Y-%m-%d)-incident
   ```

4. Create fix branch from known-good state

   ```bash
   git checkout <known-good-commit-hash>
   git checkout -b fix/$(date +%Y-%m-%d)-rollback
   ```

5. Apply fix or revert

   ```bash
   # Option A: Simple revert (recommended when possible)
   git revert <bad-commit-hash> --no-edit

   # Option B: Manual fixes (for complex issues)
   # ... make your changes here
   ```

6. Push and open PR

   ```bash
   git push -u origin fix/$(date +%Y-%m-%d)-rollback
   ```

   - Open PR targeting `main`
   - Let the full Harness (lint + tests + simulations) validate the PR
   - Get required human approval
   - Merge via Squash and merge only

7. Cleanup

   - Delete the fix branch (local and remote)
   - Delete the rescue branch if no longer needed
   - Confirm `main` branch is green again via Harness

## Quick One-Liner Sequence (most common case)

```bash
git checkout main && git pull origin main
git checkout -b fix/$(date +%Y-%m-%d)-rollback <known-good-commit-hash>
git revert <bad-commit-hash> --no-edit
git push -u origin fix/$(date +%Y-%m-%d)-rollback
```

Then open the PR in GitHub and complete the harness + approval flow.
