# Python Debian Poetry Template

- Python 3.10.5
- Poetry dependency management  
- Base Docker image: python:3.10.5-bullseye (debian)
- Authored by Kyle Clark - [kyleaclark.com](https://kyleaclark.com)

### Local Environment

Note: Instructions are specific to macOS. Steps may vary.

#### Prerequisites

1. Install pyenv for python version management - https://github.com/pyenv/pyenv
2. Update pyenv if previously installed e.g. via brew `brew upgrade pyenv`
3. Install poetry for python dependency management - https://python-poetry.org/docs/#installation
4. Update poetry if necessary (optional): `poetry self update`
4. Add pyenv path to profile e.g. add `export PYENV_ROOT="$HOME/.pyenv` + `export PATH="$PYENV_ROOT/bin:$PATH"`
5. Add poetry path to profile e.g. add `export PATH="$HOME/.poetry/bin/:PATH`
6. Install python version: `pyenv install 3.10.5`

#### Python Environment

1. Set python version within the repo directory: `pyenv local 3.10.5`
2. Set the poetry env version of python: `poetry env use ~/.pyenv/versions/3.10.5/bin/python`
3. Install python application dependencies: `poetry install`

#### Optional: PyCharm Setup

1. Open PyCharm Preferences
2. Open Project Interpeter
3. Add existing Virtualenv Environment e.g. `/Users/<username>/Library/Caches/pypoetry/virtualenvs/<poetry-name>/bin/python`
4. Run `app/main.py`

___

### Docker Build

#### Docker Build & Run App

```
docker build --target application -f Dockerfile -t py-debian-poetry .
docker run --user=appuser --env APP_ENV=DEV py-debian-poetry
```

#### Docker Build & Run Tests

```
docker build --target testing -f Dockerfile -t py-debian-poetry .
docker run --user=appuser --env APP_ENV=DEV py-debian-poetry
```

___

### Poetry Commands

- Poetry documentation - https://python-poetry.org/docs/
- `poetry install` - Install dependencies from poetry.lock - https://python-poetry.org/docs/cli/#install
- `poetry update` - Update poetry.lock from pyproject.toml - https://python-poetry.org/docs/cli/#update
- `poetry add` - Add a dependency into pyproject.toml - https://python-poetry.org/docs/cli/#add
- `poetry remove` - Remove a dependency in pyproject.toml and update poetry.lock - https://python-poetry.org/docs/cli/#remove
