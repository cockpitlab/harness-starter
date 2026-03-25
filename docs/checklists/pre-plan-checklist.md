# Pre-Plan Checklist — Harness Engineering

Before presenting any plan to the user, the agent must verify:

## Context Verification
- [ ] I have read the latest `AGENTS.md`
- [ ] I have read the governing `harness-engineering.mdc`
- [ ] I have read `autonomy-levels.md` and know the current project autonomy level
- [ ] I understand the task intent and constraints

## Autonomy Classification
- [ ] I have classified this action (L0–L4)
- [ ] If L2 or higher, I will explicitly state the level and request approval
- [ ] If Cloud Agent is considered, I will include estimated credit usage and risk

## Safety & Compliance
- [ ] No destructive commands are proposed without approval
- [ ] No direct commits to main
- [ ] No automatic dependency changes or API calls
- [ ] All outputs will be placed in `docs/`

## Plan Quality
- [ ] The plan is small, clear, and incremental
- [ ] The plan includes verification steps
- [ ] The plan respects progressive disclosure

Only after completing this checklist may the plan be presented to the user.