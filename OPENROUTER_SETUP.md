# OpenRouter Configuration

This project now supports OpenRouter as an alternative to OpenAI.

## Environment Variables

To use OpenRouter instead of OpenAI, set these environment variables:

```bash
# OpenRouter API Key (required)
OPENAI_API_KEY=your_openrouter_api_key_here

# OpenRouter Base URL (required for OpenRouter)
OPENAI_BASE_URL=https://openrouter.ai/api/v1

# Model Configuration (optional, defaults shown)
OPENAI_CHAT_MODEL=openai/gpt-4o
OPENAI_IMAGE_MODEL=openai/dall-e-3
```

## Available OpenRouter Models

### Chat Models (for OPENAI_CHAT_MODEL)
- `openai/gpt-4o` - GPT-4 Omni (recommended)
- `openai/gpt-4-turbo` - GPT-4 Turbo
- `anthropic/claude-3.5-sonnet` - Claude 3.5 Sonnet
- `anthropic/claude-3-opus` - Claude 3 Opus
- `meta-llama/llama-3.1-70b-instruct` - Llama 3.1 70B
- And many more at https://openrouter.ai/models

### Image Models (for OPENAI_IMAGE_MODEL)
- `openai/dall-e-3` - DALL-E 3 (recommended)
- `openai/dall-e-2` - DALL-E 2

## Example Dokploy Configuration

Add to your Dokploy environment variables:

```
OPENAI_API_KEY=sk-or-v1-xxxxxxxxxxxxx
OPENAI_BASE_URL=https://openrouter.ai/api/v1
OPENAI_CHAT_MODEL=openai/gpt-4o
OPENAI_IMAGE_MODEL=openai/dall-e-3
```

## To Use Standard OpenAI

Simply don't set `OPENAI_BASE_URL` and use:

```
OPENAI_API_KEY=sk-proj-xxxxxxxxxxxxx
```

The app will default to OpenAI's API.

## Modified Files

- `libraries/nestjs-libraries/src/openai/openai.service.ts`
- `libraries/nestjs-libraries/src/agent/agent.graph.service.ts`
- `libraries/nestjs-libraries/src/agent/agent.graph.insert.service.ts`
- `libraries/nestjs-libraries/src/database/prisma/autopost/autopost.service.ts`
