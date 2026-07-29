---
name: log-environment-gaps
description: Record confirmed, reusable tool, runtime, package, skill, connector, permission, source, or platform gaps in the central local Markdown log. MUST use after yiming-systematic-debugging confirms a reusable external limitation or workaround, and when the user explicitly asks to record, review, update, resolve, or ignore environment gaps. Do not use merely because a tool was called or an ordinary implementation defect was fixed.
---

# Log Environment Gaps

Maintain the central log at:

`C:\Users\Terence Zhang\Documents\Codex技能和环境工具\environment-gaps.md`

## Entry Contract

Use this Skill through exactly two entry paths:

1. `yiming-systematic-debugging` confirmed a reusable external limitation or workaround and handed off evidence.
2. The user explicitly requested recording, reviewing, updating, resolving, or ignoring an environment gap.

Do not activate merely because a tool was called, a command failed transiently, or an ordinary code defect was fixed.

For a debugging handoff, show this message before reading or changing the central log:

`Environment Gap Log 已触发：systematic-debugging 确认了 [category] 缺口；原因是 [root cause or reusable workaround].`

For a direct user request, show this message before reading or changing the central log:

`Environment Gap Log 已触发：用户明确要求管理环境缺口；范围是 [requested scope].`

Accept the debugger's confirmed evidence; do not repeat root-cause investigation when the handoff already establishes the limitation. The handoff should include the category candidate, component and version when known, root symptom, evidence, workaround, proposed durable fix, and nearby ordinary defects to exclude.

## Qualify the Gap

Record a gap only after confirming that it is persistent or reusable:

- `tool`: a required executable or command is unavailable.
- `runtime`: a language runtime or environment is missing or unusable.
- `package`: a reusable dependency is absent or incompatible.
- `skill`: a needed Codex skill is missing or unsuitable.
- `connector`: an application, MCP server, plugin, or authenticated connection is unavailable.
- `permission`: sandbox, filesystem, network, or authorization restrictions prevent the normal path.
- `source`: a recurring authoritative file, dataset, schema, or documentation source is unavailable.
- `platform`: the current product surface cannot perform a needed capability.

Do not record ordinary code defects, immediately corrected command mistakes, one-time missing uploads, clarification questions, optional enhancements, or transient failures with no reuse value.

## Continue the Main Task

Use a safe in-scope workaround when possible. Do not install software, change permissions, broaden scope, or stop useful work merely because a gap should be logged.

## Update the Log

1. Read the log immediately before editing it.
2. Create it with the standard schema below when it does not exist.
3. Summarize evidence concisely. Replace passwords, tokens, cookies, and credentials with `[REDACTED]`.
4. Replace line breaks inside fields with spaces and escape Markdown pipe characters.
5. Search existing rows for the same category, missing capability, and root symptom.
6. Update a matching row's `last_seen`, increment `count`, and improve its workaround or proposed fix when new evidence is better.
7. Otherwise append a row with the next available daily ID in the form `GAP-YYYYMMDD-NNN` and status `open`.
8. Patch only the matching row or append point. Never overwrite the file from stale content.
9. Re-read and retry once when a concurrent edit causes a conflict.
10. Tell the user briefly: `已记录环境缺口 GAP-...。` If an existing row was updated, identify that Gap ID and state that its count or evidence was updated.

Use only these statuses: `open`, `resolved`, and `ignored`. Leave status changes for manual or future automated management.

## Standard Schema

```markdown
# Environment and Capability Gaps

| ID | first_seen | last_seen | count | category | gap | evidence | workaround | proposed_fix | status |
|---|---|---|---:|---|---|---|---|---|---|
```

## Failure Handling

If the log is malformed, avoid destructive repair. Preserve existing content and append a clearly marked recovery section only when that is safe. If the path is unavailable or an edit still conflicts after one retry, continue the original task and tell the user that the gap could not be recorded.
