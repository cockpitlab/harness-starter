# harness-starter

Starter template for **Harness Engineering + Symphony** agentic development in Cursor.

## What This Is
A clean, reusable foundation that gives any new project a safe, controlled, and auditable agentic environment from day one.

## What's Included
- `.cursor/rules/harness-engineering.mdc` — Core governing rules (always active)
- `AGENTS.md` — Central contract and table of contents
- `autonomy-levels.md` — Autonomy framework (L0–L4)
- `docs/checklists/` — Pre-plan and post-execution checklists
- `docs/autonomy-grants/` — For L4 supervised autonomy grants
- `devops-rules.mdc` & `testing-rules.mdc` — Specialized rule extensions

## How to Use This Template
1. Click **"Use this template"** on GitHub to create a new repository
2. Open the new repo in Cursor using the **Harness-Agentic** (or your custom) profile
3. Add project-specific rules in `.cursor/rules/[project-name]-rules.mdc` when needed
4. Update `AGENTS.md` with your project name, tech stack, and constraints
5. Begin every session with a Plan — the harness rules are already enforced

## Core Principles
- Progressive disclosure: Plan → Approve → Execute → Review
- Repository is the single source of truth
- Humans provide intent. Agents propose plans and wait for approval
- Cloud Agents only for heavy tasks, with explicit approval

Last updated: March 2026