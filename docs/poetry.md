---
hide:
  - navigation
---

# Poetry

## Install
Install poetry using [pipx](https://pipx.pypa.io/stable/installation/)

### Windows
Install scoop, if not already installed using Windows Powershell:
```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```
Install pipx usng scoop:
```
scoop install pipx
pipx ensurepath
```
Install poetry using pipx:
```
pipx install poetry
```

## 🖥️ Poetry Commands

| Command                            | Description                                                                          |
| ---------------------------------- | ------------------------------------------------------------------------------------ |
| poetry new [project-name]          | Creates a new starter project directory structure, including the pyproject.toml file |
| poetry init                        | Initialize poetry for an existing project, which is switching to poetry              |
| poetry install                     | Install the dependencies of the project based on the versions in poetry.lock file    |
| poetry update                      | Update dependent packages to the latest versions                                     |
| poetry shell                       | Activate the python virtual environment created by poetry                            |
| poetry add package-name            | Install a package for the project                                                    |
| poetry run python main.py          | Run your main python script using poetry                                             |
| poetry run pytest                  | Run pytest                                                                           |
| poetry version [major/minor/patch] | Increment the major/minor/patch version of the project in the pyproject.toml         |
| poetry build                       | Build package                                                                        |
| poetry publish                     | Publish package to PyPI                                                              |
| poetry export -f requirements.txt --output requirements.txt | Export to requirements.txt |

# Advanced
To use a specific version of python instead of the active python:

```
poetry env use "C:\Python38\python.exe"
```