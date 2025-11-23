---
hide:
  - navigation
---
# Python

## Install
Download and install from [python.org](https://www.python.org/downloads/)

## Quick Start
- Install [uv](/uv)
```
uv init my-project --package
uv sync
```

## Basics
- Module refers to a .py file.
- Package refers to a folder with __init__.py along with multiple *.py files.
- A package can have subpackages (which are subfolders with each having their own __init__.py file)
- Recommended to use absolute imports (imports starting from top level folder/package), instead of relative imports (which is relative to current file)

```
my_app/
└── src/
    └── my_app/
        ├── __init__.py
        ├── core/
        │   ├── __init__.py
        │   └── engine.py
        ├── utils/
        │   ├── __init__.py
        │   └── math_utils.py
        └── main.py
```
Example absolute import in main.py:
```python
from my_app.core.engine import Engine
from my_app.utils.math_utils import add
```
Example absolute import in engine.py
```python
from my_app.utils.math_utils import add
```

## Python Tools
- [uv](/uv)
- [pytest](/pytest)
- [fastapi](/fastapi)
- [pydantic](/pydantic)
- [grpc](/grpc)
- [Cookie Cutter](/Cookiecutter)
- [pipx](/pipx)
- [poetry](/poetry)

## Libraries
- [tqdm](https://github.com/tqdm/tqdm) - Progress bar in commandline like 76%|████████████████████████        | 7568/10000 [00:33<00:10, 229.00it/s]

## Project Templates
- [uvinit](https://github.com/jlevy/uvinit)
- [Cookiecutter uv](https://github.com/fpgmaas/cookiecutter-uv)

## Curated Lists
1. [Awesome Python](https://github.com/vinta/awesome-python/)