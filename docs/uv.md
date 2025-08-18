---
hide:
  - navigation
---

# uv

## Install
Install via [pipx](/pipx)
```
pipx install uv
```
or directly using powershell script
```
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

There are also other [alternate installation options](https://docs.astral.sh/uv/getting-started/installation/)

## Getting Started
```
uv init - Create a new uv project
uv pin python 3.11 - Specify the python version to use for the project
uv add grpc - Install package
uv run main.py - Run the starter script
uv python list - Lists all python versions available + can be downloaded
uv python install 3.12 - Download and install python
```

## Project Templates
1. uvinit
```
uvx uvinit
```
2. [cookiecutter-uv](https://github.com/fpgmaas/cookiecutter-uv)

## References
- [uv for Virtual Environments](https://docs.astral.sh/uv/guides/projects/)
- [uv for Python Installations](https://docs.astral.sh/uv/guides/install-python/)