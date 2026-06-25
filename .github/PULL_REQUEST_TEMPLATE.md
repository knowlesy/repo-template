## Ticket

<!-- Link to the ticket, issue, or change request this PR addresses -->
Resolves: #<!-- issue number --> | [JIRA-XXX](https://your-jira.atlassian.net/browse/JIRA-XXX)

---

## What does this PR do?

<!-- A concise description of the change. What problem does it solve? What is the expected outcome? -->

---

## How was it tested?

<!-- Describe how you validated this change. Tick all that apply and add notes. -->

- [ ] Tested locally
- [ ] Tested in dev/staging environment
- [ ] Pipeline/CI passed
- [ ] Peer tested / pair reviewed
- [ ] Not testable — reason: <!-- explain -->

**Test details:**
<!-- Commands run, environments used, outputs observed -->

---

## Impact

| Area | Detail |
|------|--------|
| Scope | <!-- e.g. single service / platform-wide / all environments --> |
| Blast radius | <!-- What breaks if this goes wrong? --> |
| Dependencies | <!-- PRs, deployments, or config changes that must land first --> |
| Downstream effects | <!-- Does this change affect other teams, services, or pipelines? --> |

---

## Is this rollbackable?

- [ ] Yes — rollback steps: <!-- describe how to revert --> 
- [ ] No — reason: <!-- explain, e.g. data migration, schema change -->
- [ ] Partial — notes: <!-- explain -->

---

## Checklist

- [ ] Code follows the style guide / passes linting
- [ ] Tests added or updated where applicable
- [ ] Documentation updated (`docs/`, READMEs, runbooks)
- [ ] `CODEOWNERS` updated if new directories or file types introduced
- [ ] Secrets are **not** hardcoded (checked `.gitignore` guardrails apply)
- [ ] `*.tfvars` and state files are **not** included in this PR
- [ ] Change has been communicated to relevant stakeholders (if applicable)
