---
name: brainstorming-gate
description: "You MUST use this before any independent creative work - creating or materially modifying content, designs, artifacts, workflows, software, features, or behavior. Briefly reflect what you understand, then route the request to direct execution or yiming-brainstorming. Do not use for read-only explanation, review, diagnosis, research, factual answering, translation, formatting, or status reporting."
---

# Brainstorming Gate

Help the user decide whether the current creative request needs the full `yiming-brainstorming` workflow. Do not perform brainstorming inside this Gate.

## Reflect Understanding

Briefly state:

- the intended outcome and primary deliverable in no more than two sentences;
- at most one material uncertainty or assumption, omitted when none exists.

Use only the user's instructions and established context. Do not research, inspect additional sources, invent requirements, expose hidden reasoning, or propose solutions.

## Route the Request

If the user explicitly requests brainstorming, reflect the understanding briefly and invoke `yiming-brainstorming` without asking again.

If the user explicitly requests direct execution or rejects brainstorming, reflect the understanding briefly and continue directly without asking again.

Otherwise, respond:

```text
我的理解：
[一到两句话复述结果、交付物和明确限制。]

可能存在的偏差：
[最多一个重要的不确定点；没有则省略。]

请选择：
A. 理解正确，直接执行
B. 使用 brainstorming，先深入讨论
C. 理解有偏差，我先纠正
```

- **A:** Continue directly without invoking `yiming-brainstorming`.
- **B:** Invoke `yiming-brainstorming` and follow its complete workflow.
- **C:** Accept the correction, reflect the updated understanding once, then offer A and B again unless the correction already selects a route.

## Request Boundary

Keep the selected route for follow-ups that refine the same unfinished deliverable. Make a new decision when the user starts a materially separate deliverable or goal.

Do not carry the choice to later independent requests or treat it as a Project-wide default.

Do not ask exploratory questions, compare approaches, create a design, write a spec or plan, or begin implementation before the route is settled.
