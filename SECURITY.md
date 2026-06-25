# Security Policy

## Reporting a vulnerability

Do **not** open a public GitHub issue for security vulnerabilities.

Report privately via one of:
- GitHub's [private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing/privately-reporting-a-security-vulnerability) (enable it in repo Settings → Security)
- Email: <!-- security@your-org.com -->

Include: description of the issue, steps to reproduce, potential impact, and any suggested fix.

## What never to commit

The `.gitignore` in this repository blocks common patterns, but the following are
explicitly prohibited in all circumstances:

| Category | Examples |
|----------|---------|
| Private keys & certificates | `*.pem`, `*.key`, `*.crt`, `*.pfx`, `*.p12` |
| Credentials & passwords | Hardcoded in any file; `*.tfvars`; `.env*` |
| Terraform state | `*.tfstate`, `*.tfstate.backup` — contains live infrastructure data |
| Ansible Vault passwords | `vault_pass*`, `.vault_pass`, `*.vault_password` |
| Cloud provider tokens | AWS access keys, Azure SP credentials, GCP service account JSON |

If you have accidentally committed a secret, treat it as compromised immediately:
rotate it, then use `git filter-repo` or contact GitHub support to purge the history.

## Secret management

Prefer referencing a secret manager over storing values locally:
- **AWS**: Secrets Manager / Parameter Store
- **Azure**: Key Vault
- **GCP**: Secret Manager
- **HashiCorp**: Vault
- **Kubernetes**: External Secrets Operator

## AI tools

Sensitive files are excluded from AI context via `.aiignore` and `.copilotignore`.
Review those files and extend them if your project introduces new secret patterns.
