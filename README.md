# {{PROJECT_NAME}}

> **📋 Template** : voir [TEMPLATE.md](TEMPLATE.md) pour les instructions d'utilisation.

[![Python](https://img.shields.io/badge/python-3.13-blue.svg)](https://www.python.org/downloads/)
[![Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json)](https://github.com/astral-sh/ruff)

{{PROJECT_DESCRIPTION}}

## Installation

**Prérequis** : [uv](https://docs.astral.sh/uv/) — installateur standalone, gère aussi Python :

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### Stack

| Outil | Rôle |
|-------|------|
| [uv](https://github.com/astral-sh/uv) | Gestionnaire de dépendances (remplace pip) |
| [ruff](https://github.com/astral-sh/ruff) | Linter + formatter (remplace flake8/black/isort) |
| [pytest](https://pytest.org) | Tests |
| [pre-commit](https://pre-commit.com) | Hooks Git automatiques |
| [GitHub Actions](https://github.com/features/actions) | CI/CD (désactivé par défaut) |

### Setup

```bash
uv sync --group dev                # crée .venv + installe Python 3.13 si absent
.venv\Scripts\activate             # Windows (Linux/Mac : source .venv/bin/activate)
uv run pre-commit install          # hooks run automatically on git commit
cp .env.example .env  # Puis renseigner les valeurs
```

## Structure

```
├── scripts/          # CLI / production scripts
├── src/              # Source code
├── notebooks/        # Exploration & analysis
├── data/
│   ├── raw/          # Raw data (not versioned)
│   └── processed/    # Processed data (not versioned)
├── tests/            # Tests
└── docs/             # Documentation
```

## Usage

```bash
# Run tests
pytest

# Lint & format
uv run ruff check . --fix
uv run ruff format .
```
