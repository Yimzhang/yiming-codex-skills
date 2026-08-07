# Changelog

This file records user-facing workflow changes to the published Skill collection.

## 2026-08-07

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
