# CLAUDE.md — {{PROJECT_NAME}}

Règles stables du projet, chargées à chaque session agent. Garder ce fichier maigre.

## Contexte

{{PROJECT_DESCRIPTION}}

<!-- Préciser : type de projet (POC local mono-utilisateur, app, pipeline…), utilisateurs, livrable attendu. -->

## Domiciliation de l'information (un seul foyer par info)

- **CLAUDE.md** (ce fichier) : conventions et règles stables.
- **Notion** : couche stratégique vivante — statut, décisions ouvertes, roadmap. <!-- lien vers la page hub du projet -->
- **README.md** : présentation pour humains — installation, usage.
- **docs/** : documentation technique.

En cas d'écart entre Notion et le repo : le signaler explicitement, ne pas trancher seul.

## Règles de dev

- **KISS · DRY · YAGNI** — factoriser à partir de 3 occurrences ; pas d'abstraction spéculative.
- Python 3.13+, PEP 8, type hints, `pathlib`, f-strings, `logging` (pas de `print`).
- Docstrings Google style en français.
- Dépendances minimales, gérées par uv (`uv add …`, jamais pip).

## Commandes

```bash
uv sync --group dev        # installer / mettre à jour l'environnement
uv run pytest              # tests
uv run ruff check . --fix  # lint
uv run ruff format .       # format
uv lock --check            # lockfile à jour (vérifié en CI)
```

## Fin de tâche

Avant de proposer un commit : `pytest`, `ruff check . --fix`, `ruff format .`, `uv lock --check`, cohérence README/docs. Ne pas commiter soi-même — proposer un message de commit.
