# Yiming Codex Skills

Public personal collection of customized Codex Skills maintained by Yiming.

## Included Skills

| Skill | Purpose | Repository path |
|---|---|---|
| `yiming-brainstorming` | Explore requirements and approve a design before implementation | `skills/yiming-brainstorming` |
| `yiming-verification-before-completion` | Require fresh evidence before completion claims | `skills/yiming-verification-before-completion` |
| `yiming-systematic-debugging` | Find root causes before applying fixes and hand off reusable environment gaps | `skills/yiming-systematic-debugging` |
| `yiming-receiving-code-review` | Evaluate review feedback before implementing it | `skills/yiming-receiving-code-review` |
| `yiming-writing-plans` | Turn approved specifications into implementation plans | `skills/yiming-writing-plans` |
| `yiming-executing-plans` | Execute written plans with review checkpoints | `skills/yiming-executing-plans` |
| `yiming-dispatching-parallel-agents` | Split independent work across parallel agents | `skills/yiming-dispatching-parallel-agents` |
| `log-environment-gaps` | Record confirmed reusable environment and capability gaps | `skills/log-environment-gaps` |

## Installation

Install one or more Skill directories from GitHub:

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-installer\scripts\install-skill-from-github.py" `
  --repo Yimzhang/yiming-codex-skills `
  --path `
    skills/yiming-brainstorming `
    skills/yiming-verification-before-completion `
    skills/yiming-systematic-debugging `
    skills/yiming-receiving-code-review `
    skills/yiming-writing-plans `
    skills/yiming-executing-plans `
    skills/yiming-dispatching-parallel-agents `
    skills/log-environment-gaps
```

Restart Codex after installation so the new Skill metadata is reloaded.

## Validation

Run the system validator in UTF-8 mode on Windows:

```powershell
$validator = "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py"

Get-ChildItem -LiteralPath .\skills -Directory | ForEach-Object {
  python -X utf8 $validator $_.FullName
}
```

Each directory should return `Skill is valid!`.

## Maintenance and Privacy

- Review and validate changes before publishing them.
- Keep credentials, access tokens, company data, and unrelated machine-specific paths out of this repository.
- Preserve each Skill directory as a self-contained installable unit.
- `log-environment-gaps` intentionally contains the configured local path of Yiming's central environment-gap log.

## Attribution

The seven `yiming-*` Skills were adapted from Superpowers 6.2.0 by Jesse Vincent and customized for Yiming's personal workflow. The upstream MIT License and copyright notice are preserved in [LICENSE](LICENSE). `log-environment-gaps` is Yiming's personal Skill.
