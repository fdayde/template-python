# Utilisation du template

## Setup initial (une seule fois)

1. Créer un repo GitHub avec ce contenu
2. Dans **Settings > General** : cocher **"Template repository"**

## Pour chaque nouveau projet

1. Sur GitHub : **"Use this template"** → **"Create a new repository"**
2. Cloner le nouveau repo localement
3. Rechercher-remplacer (VSCode : `Ctrl+Shift+H`) :
   - `{{PROJECT_NAME}}` → nom du projet
   - `{{PROJECT_DESCRIPTION}}` → description
   - `{{YEAR}}` → année en cours
   - `{{AUTHOR_NAME}}` → ton nom
4. LICENSE : mettre à jour ou supprimer selon le type de projet (client = supprimer, open source = garder)
5. Adapter `CLAUDE.md` (contexte, lien Notion) — ou le supprimer si pas d'usage agent
6. Activer la CI : renommer `.github/workflows/ci.yml.disabled` → `ci.yml`
7. Supprimer ce fichier `TEMPLATE.md`
8. Setup :

**Prérequis** : [uv](https://docs.astral.sh/uv/) (installateur standalone, gère aussi Python) :

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

```bash
uv sync --group dev                # crée .venv + installe Python 3.13 si absent
.venv\Scripts\activate             # Windows (Linux/Mac : source .venv/bin/activate)
uv run pre-commit install
cp .env.example .env
```

9. Ajouter les dépendances spécifiques au projet :

```bash
uv add pandas duckdb  # etc.
```

10. Premier commit :

```bash
git add .
git commit -m "Initial setup from template"
git push
```
