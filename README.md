# Platform Engineering Repository Template

A production-ready repository template for platform engineering teams working with
**Terraform, Ansible, Puppet, Helm/Kubernetes, Python, and PowerShell**.

Designed for Mac and Windows (WSL2) developers. Use it as a GitHub template to
bootstrap new repos, or cherry-pick individual files to retrofit existing ones.

---

## Quick start

1. Click **"Use this template"** on GitHub and create a new repository.
2. Open the repo in VS Code — install the recommended extensions when prompted.
3. Update `.github/CODEOWNERS` with your team or GitHub usernames.
4. Remove any optional sections that don't apply to your project (see [Optional files](#optional-files)).
5. Start building.

---

## What's included

### Guardrails

| File | Purpose |
|------|---------|
| [`.gitignore`](.gitignore) | Blocks OS clutter, secrets, build artefacts, and tool-specific generated files for all supported stacks |
| [`.gitattributes`](.gitattributes) | Enforces LF line endings everywhere except PowerShell (CRLF) |
| [`.dockerignore`](.dockerignore) | Mirrors `.gitignore` to keep Docker build context clean and secret-free |
| [`.aiignore`](.aiignore) | Excludes secrets and large generated artefacts from Claude, ChatGPT, Gemini, and other AI tools |
| [`.copilotignore`](.copilotignore) | Same content as `.aiignore` — GitHub Copilot reads this file specifically |

### Editor config

| File | Purpose |
|------|---------|
| [`.editorconfig`](.editorconfig) | Consistent indentation and line endings per language. **Requires the [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) extension** — VS Code will prompt you to install it. |
| [`.vscode/extensions.json`](.vscode/extensions.json) | Recommended VS Code extensions for the full platform engineering stack |
| [`.vscode/settings.json`](.vscode/settings.json) | Workspace settings that mirror `.editorconfig` as a fallback |

### GitHub

| File | Purpose |
|------|---------|
| [`.github/CODEOWNERS`](.github/CODEOWNERS) | Auto-assigns reviewers by path/file type. **Update before first merge.** |
| [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md) | PR template: ticket, what/why, test evidence, impact, rollback plan |
| [`.github/ISSUE_TEMPLATE/bug_report.md`](.github/ISSUE_TEMPLATE/bug_report.md) | Structured bug reports |
| [`.github/ISSUE_TEMPLATE/feature_request.md`](.github/ISSUE_TEMPLATE/feature_request.md) | Structured feature requests |
| [`.github/copilot-instructions.md`](.github/copilot-instructions.md) | Workspace-level coding standards fed to GitHub Copilot automatically |

### Standards and documentation

| File | Purpose |
|------|---------|
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Branch naming, commit message style, PR guidance, and how to use this template |
| [`SECURITY.md`](SECURITY.md) | What to never commit, how to report vulnerabilities, secret manager references |

### Directory structure

```
.
├── .github/
│   ├── CODEOWNERS
│   ├── PULL_REQUEST_TEMPLATE.md
│   ├── copilot-instructions.md
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.md
│       └── feature_request.md
├── .vscode/
│   ├── extensions.json
│   └── settings.json
├── docs/          # Project documentation
├── logs/          # Runtime logs (gitignored)
├── scripts/       # Utility and automation scripts
└── tests/         # Tests
```

Project-specific directories (`terraform/`, `ansible/`, `helm/`, `puppet/`, `src/`)
are intentionally not created — add them as your project takes shape.

---

## Stack support

| Stack | .gitignore | .editorconfig | .gitattributes | AI ignores | VS Code ext |
|-------|:----------:|:-------------:|:--------------:|:----------:|:-----------:|
| Terraform | yes | 2-space HCL | yes | yes | HashiCorp Terraform |
| Ansible | yes | 2-space YAML | yes (.j2) | yes | Red Hat Ansible |
| Puppet | yes | 2-space .pp | yes | yes | Puppet |
| Helm / K8s | yes | 2-space YAML | yes | yes | Kubernetes Tools |
| Python | yes | 4-space PEP 8 | yes | yes | ms-python |
| PowerShell | yes | 4-space CRLF | yes | yes | ms-vscode.powershell |

---

## AI tools

| Tool | Config file | Notes |
|------|-------------|-------|
| GitHub Copilot | [`.copilotignore`](.copilotignore) + [`.github/copilot-instructions.md`](.github/copilot-instructions.md) | Instructions file is read automatically in VS Code |
| Gemini Code Assist | [`.aiignore`](.aiignore) | Respects `.gitignore` natively; `.aiignore` as general fallback |
| Claude | [`.aiignore`](.aiignore) | No per-repo config file; `.aiignore` limits context scanning |
| ChatGPT | [`.aiignore`](.aiignore) | No standard per-repo config file |

---

## Optional files

Some files only make sense for certain project types. Remove them if they don't apply —
each has a comment at the top explaining what it covers.

| File | Remove if... |
|------|-------------|
| [`.dockerignore`](.dockerignore) | Project does not use Docker |
| [`.copilotignore`](.copilotignore) | Team does not use GitHub Copilot |
| [`.aiignore`](.aiignore) | Team uses no AI coding tools |
| Terraform block in `.gitignore` | Project does not use Terraform |
| Ansible block in `.gitignore` | Project does not use Ansible |
| Puppet block in `.gitignore` | Project does not use Puppet |

---

## Security

Never bypass the guardrails. All certificates, private keys, `.env*` files,
Terraform state, and Ansible vault passwords are blocked from source control and
AI context across **all** configuration layers. See [`SECURITY.md`](SECURITY.md).
