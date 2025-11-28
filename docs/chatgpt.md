---
hide:
  - navigation
---

# ChatGPT
## Install
```
uv add openai
```

## Quick Start
```python
import asyncio
from openai import AsyncOpenAI

client = AsyncOpenAI()

async def main():
    resp = await client.responses.create(
        model="gpt-4.1",
        input=[
            {"role": "user", "content": "Hello!"}
        ]
    )

    print(resp.output_text)

asyncio.run(main())
```