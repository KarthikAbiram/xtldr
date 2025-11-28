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
### Getting a Structured Response
```python
from openai import OpenAI
from pydantic import BaseModel

client = OpenAI()

class CalendarEvent(BaseModel):
    name: str
    date: str
    participants: list[str]

response = client.responses.parse(
    model="gpt-4o-2024-08-06",
    input=[
        {"role": "system", "content": "Extract the event information."},
        {
            "role": "user",
            "content": "Alice and Bob are going to a science fair on Friday.",
        },
    ],
    text_format=CalendarEvent,
)

event = response.output_parsed
```