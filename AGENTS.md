# Repository Guidelines

## Project Structure & Module Organization

This repository is currently minimal and has no committed source tree. When adding code, keep the layout predictable:

- `src/` for application or library source code.
- `tests/` for automated tests that mirror `src/` paths.
- `assets/` for static files such as images, fixtures, or sample data.
- `docs/` for design notes, API notes, and contributor documentation.

Keep generated outputs, build artifacts, dependency folders, and local environment files out of version control.

## Development

- Prefer project-local configuration, tools, and dependencies.
- Run build, test, lint, and development commands from the repository root unless the project requires otherwise.

## Coding Style & Naming Conventions

Follow the style conventions of the language and framework added to the repository. Prefer small modules with clear responsibility and descriptive names.

- Use `camelCase` for JavaScript or TypeScript variables and functions.
- Use `PascalCase` for classes, React components, and exported types.
- Use `snake_case` for Python files, functions, and variables.
- Use lowercase, hyphenated names for scripts and documentation files, such as `setup-dev.md`.

Add a formatter or linter configuration before relying on style conventions in review.

## Testing Guidelines

Place tests under `tests/` or next to implementation files using the ecosystem’s common pattern. Name tests after the behavior they validate, for example `parser.test.ts`, `test_parser.py`, or `user-service.spec.ts`.

New behavior should include focused tests for success cases and important edge cases. If a change cannot be tested automatically, describe the manual verification steps in the pull request.

## Commit & Pull Request Guidelines

There is no Git history in this checkout, so no repository-specific commit convention can be inferred. Use concise, imperative commit messages, for example `Add input validation` or `Document setup commands`.

Pull requests should include a short summary, the reason for the change, tests or checks performed, and screenshots for UI changes. Link related issues when available and call out follow-up work explicitly.

## Agent-Specific Instructions

Keep changes narrowly scoped to the request.
Do not introduce new dependencies, build tools, or directory structures unless they are needed for the task.
Preserve user changes and avoid modifying unrelated files.

### Implementation Workflow

Before creating files, modifying files, deleting files, or writing code, confirm the intended specification with the user.

1. Clarify the goal, target files, and scope of changes.
2. Ask questions when requirements or expected behavior are ambiguous.
3. Present a concise implementation plan.
4. Wait for explicit user approval before making changes.

Read-only inspection within the repository may be performed as needed, but implementation must not begin until the workflow above is complete.

### File Access Restrictions

- Work only within the current repository root and its descendants.
- Do not read, list, search, inspect, create, modify, or delete files outside the repository root.
- Do not traverse above the repository root using `..` or equivalent paths.
- Do not access paths under the user's home directory unless they are inside this repository.
- Do not run recursive searches whose scope extends outside the repository.
- Do not use absolute paths that point outside the repository.
- If completing a task appears to require access outside the repository, stop and ask the user for permission before accessing it.

### Sensitive Information

- Do not add secrets, credentials, passwords, API keys, access tokens, private keys, or other authentication material to the repository.
- Do not copy sensitive information from the local environment into repository files, logs, documentation, tests, fixtures, or examples.
- Use placeholders or environment-variable references instead of real secret values.

### Change Approval

- Do not modify, create, rename, or delete any file without explicit user approval.
- Before making changes, explain which files you intend to change and summarize the planned modifications.
- Wait for the user's approval before applying any changes.
- Once approval is granted for a stated set of file changes, do not request approval again for individual file modifications within that approved scope.
- Approval applies only to the specific change set described immediately before approval and does not carry over to later tasks.
- Approval for file changes does not imply approval for dependency changes, Git operations, or other separately restricted actions.

### Git Operation Restrictions

- Do not run `git add`, `git commit`, `git push`, `git pull`, `git fetch`, `git merge`, `git rebase`, `git reset`, `git checkout`, `git switch`, `git branch -D`, `git tag`, or any other Git command that changes repository state or communicates with a remote unless the user explicitly approves that specific operation.
- Read-only Git commands such as `git status`, `git diff`, `git log`, and `git show` are allowed without approval.
- Never stage files automatically as part of another task.
- Never create, amend, squash, reword, or delete commits without explicit user approval.
- Never push to a remote repository without explicit user approval immediately before the push.
- Approval for file changes does not grant approval for staging, committing, pushing, or any other Git operation.

### Command Execution Restrictions

- Do not install, update, or remove dependencies without explicit user approval.
- Do not run commands that may modify the repository, project environment, or generated files unless they are within an explicitly approved change scope.
- Read-only inspection commands and test, lint, or build commands that do not intentionally modify source files may be run without approval.

