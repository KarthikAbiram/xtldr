---
hide:
  - navigation
---
# FastAPI

## Install

```
pip install "fastapi[standard]"
```

## Quick Start

Create a file main.py with:

```
from typing import Union

from fastapi import FastAPI

app = FastAPI()


@app.get("/")
def read_root():
    return {"Hello": "World"}


@app.get("/items/{item_id}")
def read_item(item_id: int, q: Union[str, None] = None):
    return {"item_id": item_id, "q": q}
```

To run,
```
fastapi dev main.py
```

For more details, please refer to [FastAPI Example](https://fastapi.tiangolo.com/#example).