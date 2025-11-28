---
hide:
  - navigation
---

# Phoenix

## Install
In a separate non-project folder, install and run phoenix as a local instance:
```bash
uv init phoenix-local
cd phoenix-local
uv add phoenix
uv add openai
```
Run:
```bash
uv run phoenix serve
```
Phoenix would now be available at http://127.0.0.1:6006

## Quick Start
### Tracing
Install and register tracer in the project.
Reference: https://arize.com/docs/phoenix/get-started/get-started-tracing#local-self-hosted
```bash
uv add arize-phoenix-otel
uv add openinference-instrumentation-openai
```
Example code with phoenix tracing:
```python
import os
from phoenix.otel import register
import openai
from getpass import getpass

# Register Tracer
tracer_provider = register(
    project_name="my-llm-app",
    auto_instrument=True,
)

tracer = tracer_provider.get_tracer(__name__)

# OpenAI Example
if not (openai_api_key := os.getenv("OPENAI_API_KEY")):
    openai_api_key = getpass("🔑 Enter your OpenAI API key: ")

os.environ["OPENAI_API_KEY"] = openai_api_key

client = openai.OpenAI()
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Why is the sky blue?"}],
)
print(response.choices[0].message.content)
```
