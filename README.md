# harness-starter

A governance template for safe, controlled **agentic development** using **Harness Engineering + Symphony** in Cursor.

## Purpose
This template provides the mechanical rules, guardrails, and structure needed to build reliable multi-agent systems while maintaining strong human oversight.

It establishes:
- **Harness Engineering** — strict branch protection, PR gates, full harness validation (lint + tests + simulations), and safe rollback procedures.
- **Symphony readiness** — a clean, machine-legible foundation for safe multi-agent orchestration.

## What's Included
- `.githooks/pre-push` — prevents direct pushes to `main`
- `.github/workflows/` — CI harness (lint, tests, simulations)
- `AGENTS.md` — mechanical contract and central table of contents for the repo
- `docs/rollback-playbook.md` — safe recovery procedures
- `docs/` — documentation, plans, and task handoff context
- `.cursor/rules/` and `.cursor/skills/` — specialized agent guidance
- `SOUL.md` — agent persona and behavioral boundaries

## Core Harness Principles
- `main` must always remain **clean, verified truth** (passing lint, tests, and simulations).
- All changes go through `agent/YYYY-MM-DD-...` or `fix/YYYY-MM-DD-...` branches + PR + full harness validation.
- Bad branches are deleted — never fixed in place.
- Pre-push hook + GitHub branch protection + required reviews enforce the rules mechanically.
- Progressive disclosure: Human intent → Agent proposal → Harness validation → Human approval.

## Symphony Readiness
This repository is fully prepared for Symphony multi-agent orchestration:
- Agents can propose changes safely on isolated branches.
- Every proposal is independently validated by the full harness.
- Clear mechanical handoff via `AGENTS.md`, `docs/`, and `docs/rollback-playbook.md`.

When ready, the Symphony orchestrator can be layered on top of this guarded foundation.

## How to Use
1. Use this repo as a GitHub template for new agentic projects.
2. Open the project in Cursor.
3. Always start by reading `SOUL.md` and `AGENTS.md`.
4. All development happens via `agent/` or `fix/` branches + Pull Request + full harness.
5. Follow `docs/rollback-playbook.md` for any recovery needs.

Last updated: March 2026
