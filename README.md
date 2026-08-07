# Yiming Codex Skills

Public personal collection of customized Codex Skills maintained by Yiming.

## Included Skills

| Skill | Purpose | Repository path |
|---|---|---|
| `brainstorming-gate` | Ask once whether a creative request should use or skip the full brainstorming workflow | `skills/brainstorming-gate` |
| `yiming-brainstorming` | Explore requirements and obtain explicit design approval after the user chooses brainstorming | `skills/yiming-brainstorming` |
| `yiming-verification-before-completion` | Require fresh evidence before completion claims | `skills/yiming-verification-before-completion` |
| `yiming-systematic-debugging` | Find root causes, check known environment gaps read-only, and record only confirmed recurrences | `skills/yiming-systematic-debugging` |
| `yiming-receiving-code-review` | Evaluate review feedback before implementing it | `skills/yiming-receiving-code-review` |
| `yiming-writing-plans` | Turn approved specifications into implementation plans | `skills/yiming-writing-plans` |
| `yiming-executing-plans` | Execute written plans with review checkpoints | `skills/yiming-executing-plans` |
| `yiming-dispatching-parallel-agents` | Split independent work across parallel agents | `skills/yiming-dispatching-parallel-agents` |
| `log-environment-gaps` | Look up known gaps read-only and record confirmed reusable environment limitations | `skills/log-environment-gaps` |

## Installation

Install one or more Skill directories from GitHub:

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-installer\scripts\install-skill-from-github.py" `
  --repo Yimzhang/yiming-codex-skills `
  --path `
    skills/brainstorming-gate `
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

## Change History

See [CHANGELOG.md](CHANGELOG.md) for published workflow changes.

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

The seven `yiming-*` Skills were adapted from Superpowers 6.2.0 by Jesse Vincent and customized for Yiming's personal workflow. The upstream MIT License and copyright notice are preserved in [LICENSE](LICENSE). `brainstorming-gate` and `log-environment-gaps` are Yiming's personal Skills.
