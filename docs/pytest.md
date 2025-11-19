---
hide:
  - navigation
---
# Pytest

## Install
Create project using --package in uv:
```
uv init my-project --package
```
Install pytest as a dev dependency:
```
uv add pytest --dev
```
## Directory Structure
- Create a 'tests' folder parallel to 'src' folder
- Mirror your src folder structure
- Pytest automatically discovers files that match `test_*.py`
- Test function names should start with `test_`
```
my_app/
├── pyproject.toml
├── src/
│   └── my_app/
│       ├── __init__.py
│       ├── core/
│       │   ├── __init__.py
│       │   └── engine.py
│       ├── utils/
│       │   ├── __init__.py
│       │   └── math_utils.py
│       └── main.py
└── tests/
    ├── __init__.py
    ├── core/
    │   ├── __init__.py    # optional
    │   └── test_engine.py
    ├── utils/
    │   ├── __init__.py    # optional
    │   └── test_math_utils.py
    └── test_main.py
```
## Example
```python
# tests/test_math_utils.py
from my_app.utils.math_utils import add

def test_add():
    assert add(2, 3) == 5
```
## Run Tests
Run tests using
```
uv run pytest
```
Show more detailed output
```
uv run pytest -v 
```
Run only tests in a specific file
```
uv run pytest test_app.py
```
