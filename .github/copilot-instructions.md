# GitHub Copilot Workspace Instructions

This file provides workspace-level context to GitHub Copilot.
It is read automatically by the Copilot extension in VS Code.

## Project type

Platform engineering — infrastructure-as-code and automation.
Primary languages and tools: Terraform, Ansible, Puppet, Helm/Kubernetes, Python, PowerShell.

## Coding standards

- **Terraform**: Follow HashiCorp style guide. Use 2-space indentation. Never hardcode secrets — use variables with `sensitive = true` or reference a secrets manager.
- **Ansible**: Write idempotent tasks. Use `ansible-lint` conventions. Store sensitive values in Ansible Vault, never plaintext.
- **Puppet**: Follow the Puppet style guide. Use 2-space indentation. Declare resources, do not exec where a native type exists.
- **Helm**: Use 2-space YAML indentation. Template values via `values.yaml`; never hardcode environment-specific values in templates.
- **Python**: PEP 8. Type hints on public functions. No secrets in code.
- **PowerShell**: Use approved verbs for function names. `Set-StrictMode -Version Latest`. CRLF line endings.

## What to avoid

- Do not suggest hardcoded credentials, API keys, or passwords anywhere.
- Do not suggest `*.tfstate` or `*.tfvars` files being committed — these are blocked by `.gitignore`.
- Do not suggest `eval`, `exec`, or dynamic `invoke-expression` unless unavoidable.
- Do not suggest disabling SSL/TLS certificate verification.

## Line endings

- All files: LF (Unix), except PowerShell (`.ps1`, `.psm1`, `.psd1`) which use CRLF.
- Enforced via `.editorconfig` and `.gitattributes`.

## Secrets

Never suggest committing secrets. The `.gitignore` blocks `*.pem`, `*.key`, `*.tfvars`, `.env*`, and `vault_pass*` files. Use references to secret managers (AWS Secrets Manager, HashiCorp Vault, Azure Key Vault) instead.
