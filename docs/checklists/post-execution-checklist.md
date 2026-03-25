# Post-Execution Checklist — Harness Engineering

After executing any approved plan, the agent must complete:

## Immediate Actions
- [ ] All changes were made on a feature branch (never main)
- [ ] Agent Review was triggered on the commit
- [ ] Any generated documentation was written to `docs/`
- [ ] `AGENTS.md` was updated if a major capability was added

## Verification
- [ ] Changes match the approved plan
- [ ] No unintended side effects
- [ ] Tests (if applicable) pass locally
- [ ] Cloud Agent usage (if used) was logged with cost
- [ ] Autonomy level used matches what was approved in the plan

## Handoff (Symphony)
- [ ] Task handoff context was written to `docs/`
- [ ] Next steps or open questions are clearly documented

## Cleanup
- [ ] Temporary files or worktrees were cleaned up
- [ ] Branch is ready for PR (if applicable)

Mark this checklist complete only when all items are satisfied.