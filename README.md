# harness-starter

A governance template for safe, controlled agentic development in Cursor using **Harness Engineering + Symphony** principles.

## Purpose
This repository provides the rules, structure, and guardrails needed to prevent common Cursor/agent issues:
- Agents running commands without approval
- Direct commits to main
- Uncontrolled dependency changes
- Loss of human oversight

## What's Included
- `.cursor/rules/harness-engineering.mdc` — Core governing rules (always active)
- `AGENTS.md` — Central contract and table of contents
- `autonomy-levels.md` — L0–L4 autonomy framework
- `docs/checklists/` — Pre-plan and post-execution checklists
- `docs/autonomy-grants/` — For L4 supervised actions
- Specialized rules (`devops-rules.mdc`, `testing-rules.mdc`)
- Skills system (research-landscape)

## Core Principles
- Humans provide intent. Agents propose plans and wait for explicit approval.
- Progressive disclosure: Plan → Approve → Execute → Review.
- Repository is the single source of truth.
- Cloud Agents only for heavy tasks, with clear approval and risk disclosure.

## How to Use
1. Use this as a GitHub template for new projects, or apply the structure to an existing one.
2. Open in Cursor with the **Harness-Agentic** (or your custom) profile.
3. Start every session with a Plan — the rules are already enforced.

Last updated: March 2026