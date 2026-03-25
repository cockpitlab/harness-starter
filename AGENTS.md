# AGENTS.md — Harness Engineering + Symphony Starter Template

This is the central contract and table of contents for all agents working in this repository.

## Core Contract
- Follow `.cursor/rules/harness-engineering.mdc` at all times. It is the governing rule file with priority 100.
- Repository is the single source of truth.
- Progressive disclosure: Plan → Approve → Execute → Review.
- Never commit directly to main. Always use a feature branch + PR.
- Never auto-execute API calls, install dependencies, or modify pinned packages without explicit user approval.
- Use Cloud Agents only for heavy tasks and only after explicit user confirmation.

## Symphony Contract (Summary)
- One agent, one concern. Modular task boundaries only.
- All outputs must be machine-readable: structured markdown or JSON in `docs/`.
- Hermetic tests only — no shared state, no external dependencies in unit tests.
- Write task handoff context to `docs/` before considering any task complete.
- Read `docs/` and this file as ground truth. Never assume another agent's state.

## Repository Structure
- `.cursor/rules/harness-engineering.mdc` → Governing agent rules (always active)
- `.cursor/rules/[project-name]-rules.mdc` → Project-specific rules (add when needed)
- `.cursor/skills/` → Reusable agent skills (e.g., research-landscape)
- `SOUL.md` → Defines the agent's personality, tone, and important behavioral guidelines
- `docs/` → All generated documentation, plans, and task handoff context
  - `design-docs/` → High-level architecture and design decisions
  - `exec-plans/` → Detailed execution plans and approved agent plans
  - `generated/` → AI-generated artifacts and outputs
  - `product-specs/` → Product requirements, PRDs, and user stories
  - `references/` → Landscape reviews, research, trends, and exploration
  - `runbooks/` → Operational how-to guides and procedures
  - `autonomy-grants/` → Written approvals for L4 supervised autonomous actions
  - `checklists/` → Pre-plan and post-execution checklists
- `AGENTS.md` → This file — update after any major change or new capability

## How to Use This Template
1. Use this repo as a GitHub template or clone it to start a new project.
2. Create `.cursor/rules/[project-name]-rules.mdc` for project-specific rules (stack, pinned dependencies, etc.).
3. Update this `AGENTS.md` with the project name, tech stack, and any additional constraints.
4. Open in Cursor with the Harness-Agentic profile active.
5. Begin every session with a Plan in Cursor — the harness rules are already active.

## Current Template Version
- Harness Engineering + Symphony v1.0
- Last updated: March 2026