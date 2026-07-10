# Python SDK

```python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_AI_ROUTER_KEY",
    base_url="https://api.ai-router.dev/v1",
)

resp = client.chat.completions.create(
    model="gpt-4.1-mini",
    messages=[{"role": "user", "content": "hello"}],
)

print(resp.choices[0].message.content)
```

Notes:

- Keep the `/v1` suffix in `base_url`.
- Use your AI Router API key, not an OpenAI platform key.
- If model discovery is disabled in your client, manually enter a model id that your account can access.
