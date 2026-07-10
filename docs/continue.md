# Continue

Example `config.json` fragment:

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

Notes:

- `apiBase` must include `/v1`.
- Keep manual model entry available in case model discovery is restricted.
