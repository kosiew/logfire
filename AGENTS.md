# Logfire Repository Guidelines

## Scope
These instructions apply to the entire repository unless a subdirectory overrides them with its own `AGENTS.md`.

## General expectations
- Prefer incremental, well-focused changes. Update documentation and tests whenever behaviour changes.
- Add or update tests alongside code changes when practical.
- Keep commit messages and PR descriptions descriptive and concise.

## Python code style
- Format Python with `ruff` (line length 120, single quotes for strings, double quotes for multi-line docstrings). Run `make format` before committing.
- Keep imports sorted; the `ruff` configuration treats `logfire` and `logfire_api` as first-party packages.
- Use type hints and maintain `pyright`-clean code where feasible.
- Follow Google-style docstrings when adding docstrings.

## Commenting guidelines

When writing comments in the codebase, prefer clear, purposeful comments that help future contributors understand why something is implemented a certain way. Use three distinct kinds of comments when appropriate:

- Implementation Comments
  - Explains non-obvious choices and tricky implementations.
  - Serves as breadcrumbs for future developers to understand complex control flow, algorithmic decisions, or workarounds.
  - Keep them concise and focused on the intent — not a line-by-line narration.

- Documentation Comments
  - Describes functions, classes, and modules (public API surface).
  - Act as the public interface documentation; prefer docstrings following the repository's docstring conventions.
  - Include parameter and return value descriptions for public functions, and note side effects or important usage examples when helpful.

- Contextual Comments
  - Documents assumptions, preconditions, and non-obvious requirements (for example: why a specific external quirk is handled, or why a value must be non-empty).
  - Use for temporary notes (TODOs) only when accompanied by a brief plan and an owner if possible.

General rules:
- Favor code clarity first: refactor or extract helpers rather than over-commenting convoluted code.
- Keep comments up to date; outdated comments are worse than none — update or remove them when changing behavior.
- Avoid restating what the code does — explain why it does it that way.


## Tooling & commands
- Use the `uv`-based helpers in the `Makefile` for common tasks:
  - `make format` – format and autofix lint issues.
  - `make lint` – run lint checks.
  - `make typecheck` – run `pyright`.
  - `make test` – run the pytest suite with coverage.
- For documentation updates in `docs/`, build locally with `make docs` (or `make docs-serve` for a live preview).

## Documentation
- When modifying docs, ensure code snippets stay consistent with the implementation and build cleanly with `make docs`.
- Prefer Markdown tables and admonitions already used in the existing docs.
