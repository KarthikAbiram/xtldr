---
hide:
  - navigation
---
# Pydantic

## Install
Install using [uv](/uv)
```
uv add pydantic
```

## Quick Start
```python
from typing import List, Dict, Optional
from datetime import datetime
import json

from pydantic import BaseModel, Field

class User(BaseModel):
    id: int
    name: str
    email_address: str = Field(
        alias="emailAddress", default=""
    )  # Field alias for mapping non-exact matches to variables
    age: int = 18  # Variables with default values are also optional
    marks: List[float] = []
    created_at: datetime = Field(default_factory=datetime.now)


# Instantiate object
user = User(id=1, name="Alice", emailAddress="alice@example.com")  # Use alias name
print(user)

# Model → dict
user_dict = user.model_dump()
# Model → JSON
user_json = user.model_dump_json()

# JSON → Model
json_data = '{"id": 2, "name": "John", "emailAddress": "john@example.com"}'
user = User.model_validate_json(json_data)
```
