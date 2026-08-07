---
name: brainstorming-gate
description: "You MUST use this before any creative work - creating features, building components, adding functionality, or modifying behavior. For each independent creative request, determine whether the user already chose to use or skip yiming-brainstorming; ask once when no choice is present, then route accordingly. Do not perform brainstorming itself."
---

# Brainstorming Gate

Route each independent creative request before work begins. Do not brainstorm, explore requirements, compare approaches, present a design, write a spec or plan, or impose an approval process inside this Skill.

## Decide the Route

1. Treat an explicit request to brainstorm, discuss first, explore ideas or requirements, compare directions, or obtain design approval as **yes**. Do not ask again. Invoke `yiming-brainstorming` before implementation.
2. Treat an explicit request to proceed directly, skip brainstorming, or avoid discussion as **no**. Do not ask again. Continue directly and ask only for information genuinely required to complete the request.
3. If the user has not expressed a choice, ask exactly once:

   > 这项任务是否使用 brainstorming？使用会先讨论方案并获得设计批准；不使用则直接执行。

4. After **yes**, invoke `yiming-brainstorming` and follow its complete workflow. After **no**, exit this Gate and continue without invoking it.

## Request Boundary

- Keep the choice for follow-ups that refine the same unfinished artifact or deliverable.
- Make a new decision when the user starts a materially separate deliverable or goal.
- When uncertain, treat the follow-up as part of the current request unless the goal or deliverable materially changes.
- Never carry a choice automatically to a later independent request or treat it as a Project-wide default.

## Exclusions

Do not use this Gate when the primary task is read-only explanation, review, diagnosis, research, factual answering, or status reporting rather than creating or materially modifying an artifact, content, design, workflow, software, or behavior.
