# rdl-python-pipfile

Test fixture for the `remove_duplicate_lockfiles` maintenance task.

## Scenario

Python conflict at repo root — `Pipfile` present (no `pyproject.toml`).

Lockfiles:
- `Pipfile.lock` (pipenv)
- `poetry.lock` (poetry)

## Expected MT behaviour

- **Auto-detects** pipenv via the `Pipfile` fallback — no user question.
- **Deletes** `poetry.lock`, keeps `Pipfile.lock`.
- **Appends** `poetry.lock` to `.gitignore`.
