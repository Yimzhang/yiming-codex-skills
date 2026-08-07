---
name: log-environment-gaps
description: Look up known environment gaps read-only after yiming-systematic-debugging stably reproduces an external capability failure; update the central log only after the same reusable root cause is confirmed; and manage gaps when the user explicitly asks to record, review, update, resolve, or ignore them. Covers tool, runtime, package, skill, connector, permission, source, and platform gaps. Do not use merely because a tool was called or an ordinary implementation defect was fixed.
---

# Log Environment Gaps

Maintain the central log at:

`C:\Users\Terence Zhang\Documents\Codex技能和环境工具\environment-gaps.md`

## Operating Modes

Use exactly one mode for each invocation:

1. `lookup`: `yiming-systematic-debugging` stably reproduced an external capability failure and requests a read-only search before proposing a new workaround.
2. `update`: `yiming-systematic-debugging` confirmed that the current case has the same reusable root cause as an existing gap, or confirmed a new reusable external limitation or workaround.
3. `direct management`: the user explicitly requested recording, reviewing, updating, resolving, or ignoring an environment gap.

Do not activate merely because a tool was called, a command failed transiently, or an ordinary code defect was fixed.

For lookup mode, show this exact message before reading the central log:

`Environment Gap Lookup 已触发：外部能力故障已复现；正在检查既有 Gap 和已验证 workaround，避免重复调查。`

For update mode, show this message before reading or changing the central log:

`Environment Gap Log 已触发：systematic-debugging 确认了 [category] 缺口；原因是 [root cause or reusable workaround].`

For direct-management mode, show this message before reading or changing the central log:

`Environment Gap Log 已触发：用户明确要求管理环境缺口；范围是 [requested scope].`

In lookup mode, accept the component, exact version when known, root symptom, stable error signature, and category candidate. In update mode, accept the debugger's confirmed evidence; do not repeat root-cause investigation when the handoff already establishes the limitation. The update handoff should include the category candidate, component and version when known, confirmed root symptom, evidence, validated workaround, proposed durable fix, and nearby ordinary defects to exclude.

## Lookup Existing Gaps

Lookup mode is strictly read-only:

1. Read the current log without changing it.
2. Search exact root-cause matches first using category, component, version when known, root symptom, and stable error signature.
3. Then return useful related matches when they could guide investigation, clearly labeling them as related rather than exact.
4. Report each matched Gap ID and status. Explain that `open` is unresolved, `resolved` records a prior resolution but does not prove the current environment is fixed, and `ignored` is retained history that is not an active remediation target.
5. Present a recorded workaround only as a hypothesis. Require revalidation in the current environment before relying on it or reporting success.
6. If there is no match, state that explicitly and return control to systematic debugging.

Never update `last_seen`, increment `count`, improve evidence, change a workaround or proposed fix, append a row, or change status during lookup. A search, exact match, related match, or no-match result is not a recurrence and is not permission to mutate the log.

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

## Update the Log After Confirmation

1. Read the log immediately before editing it.
2. Create it with the standard schema below when it does not exist.
3. Summarize evidence concisely. Replace passwords, tokens, cookies, and credentials with `[REDACTED]`.
4. Replace line breaks inside fields with spaces and escape Markdown pipe characters.
5. Confirm from debugging evidence that the current case has the same root cause as an existing row before treating it as a recurrence.
6. Search existing rows for the same category, missing capability, and root symptom.
7. Update only the matching row's `last_seen`, increment `count` exactly once for the confirmed recurrence, and improve its evidence, workaround, or proposed fix only when the new evidence is better.
8. Append a row with the next available daily ID in the form `GAP-YYYYMMDD-NNN` and status `open` only when no existing root-cause match exists and the new reusable gap has been confirmed.
9. Patch only the matching row or append point. Never overwrite the file from stale content.
10. Re-read and retry once when a concurrent edit causes a conflict.
11. Tell the user briefly: `已记录环境缺口 GAP-...。` If an existing row was updated, identify that Gap ID and state that its count or evidence was updated.

Use only these statuses: `open`, `resolved`, and `ignored`. Leave status changes for manual or future automated management.

## Standard Schema

```markdown
# Environment and Capability Gaps

| ID | first_seen | last_seen | count | category | gap | evidence | workaround | proposed_fix | status |
|---|---|---|---:|---|---|---|---|---|---|
```

## Failure Handling

If the log is malformed, avoid destructive repair. Preserve existing content and append a clearly marked recovery section only when that is safe. If the path is unavailable or an edit still conflicts after one retry, continue the original task and tell the user that the gap could not be recorded.
