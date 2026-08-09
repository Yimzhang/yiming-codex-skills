# Changelog

This file records user-facing workflow changes to the published Skill collection.

## 2026-08-09 — Creative Life Zine Pair v1.3

### Added

- Added `scenes-gathered-zine-v1-3` and `scene-distillation-zine-v1-3` together as the Creative Life Zine Pair, authored by `Zeejay0`.
- **Gathered Scenes / 实景拼贴** preserves truthful photography while extending source-derived forms into a spacious tactile illustration field with structural color and a visible fibrous torn-paper handoff.
- **Scene Distillation / 影像蒸馏** uses the supplied photo only as semantic evidence and creates original illustration, paper, typography, and color without retaining photographic pixels.

### Packaging and attribution

- Published exactly four runtime files: one `SKILL.md` and one `agents/openai.yaml` for each Skill.
- Published no source photographs, generated images, binary assets, project history, or other `生活创意` files.
- Preserved the embedded `Zeejay0` author and sharing-credit statements.
- The pair includes no separate license file; the repository's preserved Jesse Vincent MIT notice is retained for upstream Superpowers-derived material and does not replace the pair's authorship statement.

## 2026-08-07 — Brainstorming gate reflection update

### Changed

- `brainstorming-gate` now briefly reflects the intended outcome and primary deliverable before routing an independent creative request.
- When the user has not already selected a route, the gate presents three explicit choices: direct execution, full brainstorming, or correction of the reflected understanding.
- The gate now excludes read-only explanation, review, diagnosis, research, factual answers, translation, formatting, and status reporting from its trigger scope.
- The gate may state at most one material uncertainty and must not research, inspect extra sources, invent requirements, expose hidden reasoning, or propose solutions during reflection.
- UI metadata now describes the reflection-first routing behavior.

### Compatibility

- The Skill name, installation path, `yiming-brainstorming` handoff, and per-request route boundary remain unchanged.
- No new runtime dependency was added.

## 2026-08-07 — Brainstorming routing update

### Added

- Added `brainstorming-gate`, which routes each independent creative request according to the user's explicit choice to use or skip the full brainstorming workflow.
- When no choice is present, the gate asks exactly once and does not perform brainstorming itself.

### Changed

- `yiming-brainstorming` now triggers only after the user explicitly chooses brainstorming or explicitly invokes the Skill.
- The brainstorming workflow asks clarification questions one at a time and requires explicit user approval for design sections and the written specification.
- The former standing-authorization path was removed from `yiming-brainstorming`; direct execution is handled by choosing to skip brainstorming at the routing gate.

### Compatibility

- The existing `yiming-brainstorming` name and installation path remain unchanged.
- `brainstorming-gate` is additive and introduces no new runtime dependency.

## 2026-08-07 — Environment gap lookup update

### Changed

- `yiming-systematic-debugging` now performs a read-only Environment Gap preflight after an external capability failure has been reproduced consistently and before a new workaround is proposed.
- `log-environment-gaps` now separates `lookup`, `update`, and `direct management` modes. Lookup mode cannot mutate the central log.
- A previous gap or workaround is treated as a hypothesis until it is revalidated in the current environment. A historical `resolved` status no longer implies that the present case is fixed.
- Gap counts and evidence may be updated only after debugging confirms the same reusable root cause; searches and related matches are not counted as recurrences.
- The `log-environment-gaps` UI metadata now advertises both read-only lookup and confirmed-gap recording.

### Compatibility

- Existing Skill names, directory paths, central log location, Markdown table schema, and allowed statuses remain unchanged.
- No new runtime dependency was added.

### Validation

- Both updated Skill directories are validated with the official `quick_validate.py` validator in UTF-8 mode.
- Canonical, global-installation, publication-package, and remote copies are compared using normalized UTF-8 content.
