# AI Router OpenAI-Compatible Examples

AI Router is an OpenAI-compatible ChatGPT API relay for developers.

- Website: https://ai-router.dev
- API base URL: `https://api.ai-router.dev/v1`
- Localized pages: `/cn`, `/ru`, `/fa` and other site locales
- New-user credit: `20U` total
  - `5U` available on signup
  - `15U` unlocked after top-up

Notes:

- This is not the official OpenAI API.
- Use your AI Router API key, not an OpenAI platform key.
- Keep the `/v1` suffix in the base URL.

Docs:

- Python SDK: https://github.com/airouter-dev/ai-router-openai-compatible-examples/blob/main/docs/openai-python-sdk.md
- Node.js SDK: https://github.com/airouter-dev/ai-router-openai-compatible-examples/blob/main/docs/openai-node-sdk.md
- Cursor: https://github.com/airouter-dev/ai-router-openai-compatible-examples/blob/main/docs/cursor.md
- Continue: https://github.com/airouter-dev/ai-router-openai-compatible-examples/blob/main/docs/continue.md
- LiteLLM: https://github.com/airouter-dev/ai-router-openai-compatible-examples/blob/main/docs/litellm.md
- Open WebUI: https://github.com/airouter-dev/ai-router-openai-compatible-examples/blob/main/docs/openwebui.md
- New-user credit: https://github.com/airouter-dev/ai-router-openai-compatible-examples/blob/main/docs/new-user-credit.md
- Localized landing pages: https://github.com/airouter-dev/ai-router-openai-compatible-examples/blob/main/docs/localized-landing-pages.md

## cURL

```bash
curl https://api.ai-router.dev/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $AI_ROUTER_API_KEY" \
  -d '{
    "model": "gpt-4.1-mini",
    "messages": [
      { "role": "user", "content": "hello" }
    ]
  }'
```

## Python

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

## Node.js

```javascript
import OpenAI from "openai";

const client = new OpenAI({
  apiKey: process.env.AI_ROUTER_API_KEY,
  baseURL: "https://api.ai-router.dev/v1",
});

const resp = await client.chat.completions.create({
  model: "gpt-4.1-mini",
  messages: [{ role: "user", content: "hello" }],
});

console.log(resp.choices[0].message.content);
```

## Model Discovery

```bash
curl https://api.ai-router.dev/v1/models \
  -H "Authorization: Bearer $AI_ROUTER_API_KEY"
```

## Cursor

Use the OpenAI-compatible custom provider path:

- Base URL: `https://api.ai-router.dev/v1`
- API key: your AI Router key
- Model: `gpt-4.1-mini`

## Continue

Example config:

```json
{
  "models": [
    {
      "title": "AI Router",
      "provider": "openai",
      "model": "gpt-4.1-mini",
      "apiBase": "https://api.ai-router.dev/v1",
      "apiKey": "YOUR_AI_ROUTER_KEY"
    }
  ]
}
```

## LiteLLM

```yaml
model_list:
  - model_name: ai-router-gpt41mini
    litellm_params:
      model: openai/gpt-4.1-mini
      api_base: https://api.ai-router.dev/v1
      api_key: os.environ/AI_ROUTER_API_KEY
```

## Open WebUI

- API URL: `https://api.ai-router.dev/v1`
- API key: your AI Router key
- Model: choose a model returned by `/v1/models`

## Common Pitfalls

- Do not use the site root as the API base. Use `https://api.ai-router.dev/v1`.
- Some clients can fetch `/v1/models`, but manual model entry should still be preserved as a fallback.
- `15U` of the `20U` new-user credit is staged and unlocked after top-up. Do not describe it as instantly spendable on signup.
