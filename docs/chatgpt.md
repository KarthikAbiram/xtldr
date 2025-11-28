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
    resp = await client.chat.completions.create(
        model="gpt-4.1",
        messages=[{"role": "user", "content": "Hello!"}]
    )
    print(resp.choices[0].message["content"])

asyncio.run(main())
```