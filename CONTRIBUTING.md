# Contributing

## Branch naming

| Type | Pattern | Example |
|------|---------|---------|
| Feature | `feat/<short-description>` | `feat/add-s3-module` |
| Bug fix | `fix/<short-description>` | `fix/ansible-retry-logic` |
| Chore / refactor | `chore/<short-description>` | `chore/bump-terraform-providers` |
| Hotfix | `hotfix/<short-description>` | `hotfix/vault-path-typo` |

## Commit messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <short summary>

[optional body]
[optional footer: Refs #123]
```

Common types: `feat`, `fix`, `chore`, `refactor`, `docs`, `test`, `ci`

Examples:
```
feat(terraform): add S3 backend module with versioning
fix(ansible): correct vault path for prod inventory
chore: bump hashicorp/terraform to 1.8.0
```

## Pull requests

- Fill in all sections of the PR template — especially impact and rollback.
- Keep PRs focused. One logical change per PR.
- Link to a ticket or issue in every PR.
- CODEOWNERS will be automatically requested for review — don't skip it.

## Secrets

Never commit credentials, passwords, API keys, or certificates. The `.gitignore`,
`.aiignore`, and `.copilotignore` files block the most common patterns, but they
are not exhaustive. When in doubt, use a secret manager reference instead.

## Using this template

1. Click **"Use this template"** on GitHub and create a new repository.
2. Update `.github/CODEOWNERS` with your team or GitHub usernames.
3. Update `.github/copilot-instructions.md` if the tech stack differs.
4. Remove optional sections from `.gitignore` that don't apply (Terraform,
   Ansible, Puppet, Docker each have clearly marked `OPTIONAL` blocks).
5. Remove `.dockerignore`, `.aiignore`, or `.copilotignore` if not needed.
