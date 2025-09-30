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
