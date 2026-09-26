# Markdown Task Manager

A single-file Kanban board whose tasks live in a project's `kanban.md` and `archive.md`, readable and writable by both humans and AI agents.

## Language

**Board**:
The set of tasks and configuration held in one project's `kanban.md`.
_Avoid_: Backlog

**Area**:
The one part of a project a task belongs to, chosen from the list the Board declares; what that list means is up to each Board.
_Avoid_: Part, component, module, package, scope

**Category**:
The kind of work a task is (e.g. Frontend, Tests, Documentation); independent of Area.
_Avoid_: Type, layer

**Tag**:
A free-form, multi-valued label on a task, not constrained by the Board's configuration.
_Avoid_: Label

**Undeclared Area**:
An Area value on a task that is missing from the Board's declared list, typically a typo; treated as having no Area.

**Area switch**:
The board-level control that narrows the visible tasks to exactly one Area, or to all.
_Avoid_: Area filter, tabs

**Filter**:
A narrowing condition (Tag, Category, User, Priority, family) added on top of the Area switch.
