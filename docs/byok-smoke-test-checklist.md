# BYOK Smoke-test Checklist

Use this checklist when validating any OpenAI-compatible client integration against AI Router or a similar endpoint.

## Minimum contract

1. `base_url` is configurable
2. API key / bearer token is configurable
3. Manual model entry is possible
4. Optional `/v1/models` discovery does not block manual model usage

## Endpoint checks

- Base URL includes `/v1`
- `GET /v1/models` succeeds or fails clearly
- `POST /v1/chat/completions` succeeds with a short prompt
- Error messages distinguish:
  - network / DNS failure
  - auth failure
  - model not found
  - billing/quota failure

## Behavior checks

- No silent fallback to another provider
- Requested model id is logged or shown in redacted diagnostics
- Streaming behavior is tested separately from non-streaming
- Tool calling is tested separately from plain chat
- Usage/token fields are inspected if the client depends on them

## Example target

- Site: https://ai-router.dev
- API base URL: `https://api.ai-router.dev/v1`
- Public examples repo: https://github.com/airouter-dev/ai-router-openai-compatible-examples

## Messaging guardrail

- `20U` onboarding should be described as:
  - `5U` available on signup
  - `15U` unlocked after top-up
- Do not describe the full `20U` as instantly spendable.
