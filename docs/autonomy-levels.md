# Autonomy Levels — Harness Engineering + Symphony

This file defines the autonomy framework for all agents operating in this repository.
Agents must classify every proposed action before executing it.

## Level Definitions

| Level | Name                  | Description                                      | Approval Required                  |
|-------|-----------------------|--------------------------------------------------|------------------------------------|
| L0    | Read-Only             | Reading files, searching, analyzing, summarizing | None                               |
| L1    | Suggest               | Drafting plans, proposing changes, generating docs | None — present to human            |
| L2    | Controlled Execute    | Writing files, creating branches, running local scripts | Explicit user approval             |
| L3    | High-Risk Execute     | Committing, deploying, API calls, dependency changes, Cloud Agents | Explicit approval + risk disclosure |
| L4    | Supervised Autonomous | Multi-step execution within a pre-approved, time-boxed scope | Written Autonomy Grant required    |

## Rules
- Agents must **explicitly state the autonomy level** (e.g., "This action is L2") in every plan.
- L0 and L1 can proceed without approval. L2 and above **never proceed without explicit user approval**.
- When in doubt, classify one level higher and ask.
- Any action touching external services, production systems, or main branch is **always L3 minimum**.
- Cloud Agent usage is always **L3** — must state estimated credit usage and risk.
- No agent may self-upgrade its autonomy level. Only the human can modify the Project Autonomy Setting.

## Symphony Context
In multi-agent Symphony orchestration, agents must include their autonomy level in all task handoff context written to `docs/`. Receiving agents cannot exceed the granted autonomy level.

## Project Autonomy Setting
**Current project autonomy level: L2 (Default)**

This is the safe default. Agents may not exceed L2 without explicit human override in this file.

### To raise autonomy:
1. Change `L2` to desired level.
2. Document reason below.
3. Commit on a feature branch with explicit approval.

**Current override:** None

## Quick Reference

| Action                              | Level |
|-------------------------------------|-------|
| Reading code, searching, summarizing| L0    |
| Writing plans, drafting docs        | L1    |
| Creating files, creating branches   | L2    |
| Committing, API calls, installs, Cloud Agents | L3 |
| Multi-step autonomous execution     | L4    |