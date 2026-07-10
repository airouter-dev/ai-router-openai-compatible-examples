# LiteLLM

```yaml
model_list:
  - model_name: ai-router-gpt41mini
    litellm_params:
      model: openai/gpt-4.1-mini
      api_base: https://api.ai-router.dev/v1
      api_key: os.environ/AI_ROUTER_API_KEY
```

Notes:

- This is useful when you want an internal LiteLLM layer but still route through an OpenAI-compatible hosted endpoint.
- Keep `api_base` pointed at the API host, not the website root.
