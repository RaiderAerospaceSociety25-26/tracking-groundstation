# Issue Guide (How to Request Work)

This doc explains how to create issues using the provided templates.

## Templates Available

- **Bug report:** Something broken vs expected behavior
- **Feature request:** New capability, refactor, or enhancement
- **Docs task:** Write or update documentation
- **Research task:** Investigate options, compare solutions, or produce a summary doc

## General Rules

1. **Always use a template.** Blank issues are disabled.
2. **Title** should be short and action-oriented, e.g.:
   - `[BUG] IMU returns NaN after boot`
   - `[FEAT] Add servo boot sequence`
   - `[DOCS] Write VSCode setup guide`
   - `[RES] Compare pan/tilt options`
3. **Fill all required fields.** Scope + Acceptance Criteria are mandatory for feature/docs tasks.
4. **Link issues/PRs** if this work depends on other items.
5. **Labels & Projects:** Templates auto-apply a type label + `needs-triage`. During triage:
   - Add subsystem labels (`subsystem:firmware`, `subsystem:hardware`, `docs`, `ci`)
   - Add priority labels (`priority:P0`, `priority:P1`, `priority:P2`)
   - Add the issue to the correct org Project (SFC or TGS)
6. **Assignment:** Issues remain unassigned until someone takes ownership.
7. **Closing issues:** Issues should be closed by PRs using `Closes #<issue>` in the PR description.

## Why templates matter

Templates enforce:

- Clear scope and acceptance criteria
- Priorities and dependencies
- Consistent format across both projects

This makes it easy for others to pick up tasks and verify them at review/merge time.
