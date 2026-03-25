# harness-starter

A governance template for safe, controlled **agentic development** using **Harness Engineering + Symphony** in Cursor.

## Purpose
This template provides the rules, structure, and guardrails needed to build reliable multi-agent systems while maintaining strong human oversight.

It combines:
- **Harness Engineering** — the governing rules and safety layer (progressive disclosure, autonomy levels, checklists, cautious execution)
- **Symphony readiness** — the foundation for multi-agent orchestration (modular tasks, clear handoff, shared ground truth)

## What's Included
- `.cursor/rules/harness-engineering.mdc` — Core governing rules (always active)
- `AGENTS.md` — Central contract and table of contents
- `autonomy-levels.md` — L0–L4 autonomy framework with clear approval gates
- `docs/checklists/` — Pre-plan and post-execution checklists
- `docs/autonomy-grants/` — For L4 supervised autonomous actions
- Specialized rules (`devops-rules.mdc`, `testing-rules.mdc`)
- Skills system (research-landscape)

## Core Principles (Harness Engineering)
- Humans provide intent. Agents propose plans and wait for explicit approval.
- Progressive disclosure: Plan → Approve → Execute → Review.
- Repository is the single source of truth.
- Cloud Agents only for heavy tasks, with clear approval and risk disclosure.

## Symphony Readiness
This template is structured to enable Symphony (multi-agent orchestration):
- Modular task boundaries ("one agent, one concern")
- Shared ground truth via `docs/` and `AGENTS.md`
- Task handoff context written to `docs/`
- Autonomy level inheritance between agents
- Pre-plan and post-execution checklists enforced by Harness rules

When you are ready, you can bring in the Symphony orchestrator on top of this foundation for coordinated multi-agent workflows.

## How to Use
1. Use this as a GitHub template for new projects, or apply the structure to an existing one.
2. Open in Cursor with the **Harness-Agentic** (or your custom) profile.
3. Start every session with a Plan — the rules are already enforced.
4. When ready for multi-agent work, integrate Symphony orchestration.

Last updated: March 2026