# setup-poetry
[![Test action](https://github.com/ZashIn/setup-poetry/actions/workflows/test-action.yml/badge.svg)](https://github.com/ZashIn/setup-poetry/actions/workflows/test-action.yml)

GitHub action to:
- setup python: `actions/setup-python`
- install poetry: via `pipx` (cached)
- install project dependencies: via `poetry install` (cached venv)

## Usage
See [action.yml](action.yml)

```yaml
#-uses: actions/checkout@v5  # checkout before to link pyproject.toml / poetry.lock changes with cache.
-uses: zashin/setup-poetry@1
  with:
    # From actions/setup-python: Version range or exact version of Python or PyPy to use, using
    # SemVer's version range syntax. Reads from .python-version if unset.
    python-version: ''
    # The version (1.0) or specifier (==1.0) of poetry to install via pipx. Use 'latest' to
    # force latest version on every run (slower). By default no version is specified.
    poetry-version: ''
    # Options passed to poetry install, like '--no-root'.
    poetry-install-options: ''
    # Working directory for "poetry install".
    working-directory: '.'
    # If pipx and poetry installation should be cached
    use-cache: 'true'
```