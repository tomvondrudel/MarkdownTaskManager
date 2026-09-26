# Area is a dedicated, optional, single-valued task field

Boards covering a monorepo need a one-click way to see only the tasks for one part of the project. We added a new `**Area**:` task field, on its own line after the Priority/Category line, with the allowed values declared per Board in the configuration block (`**Areas**: …`). Each task has at most one Area. The field is optional so that Boards without Areas keep working unchanged, and a value missing from the declared list is shown as an Undeclared Area instead of being silently accepted.

## Considered Options

- **Reuse Category.** Category already means the kind of work (Frontend, Tests, …), which is independent of Area. Merging the two would either lose that information or produce combined values like "Scraper / Backend / Tests".
- **A Tag convention (`#area:scraper`).** Tags have many values and no fixed list, so typos pass unnoticed. A task could also end up in several Areas, which doesn't work with a switch that shows one Area at a time.
- **Put it on the Priority/Category line.** The parser's pattern for that line is strict about field order, and AI agents often write fields in a different order. A separate line is more robust.

## Consequences

The Markdown format changes, so the AI instruction files (`*.md.exemple`) and the markdown-task-manager skill must describe the new field for agents to write it.
