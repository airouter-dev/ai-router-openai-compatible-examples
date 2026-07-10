# Node.js SDK

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

Notes:

- `baseURL` must include `/v1`.
- Preserve manual model entry as a fallback even if `/v1/models` discovery exists.
