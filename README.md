<div align="center">

# EvoLink

### One API for the World's Top AI Models

Always pay less for top AI image, video, and chat models. 53 models, one integration.

[![Website](https://img.shields.io/badge/Website-evolink.ai-blue?style=flat-square)](https://evolink.ai/)
[![Models](https://img.shields.io/badge/Models-53-green?style=flat-square)](https://evolink.ai/models)
[![Success Rate](https://img.shields.io/badge/Success_Rate-99.97%25-brightgreen?style=flat-square)](https://evolink.ai/)
[![Blog](https://img.shields.io/badge/Blog-Latest_Posts-orange?style=flat-square)](https://evolink.ai/blog)

</div>

---

## What is EvoLink?

EvoLink is a unified AI API gateway. One endpoint, one API key — access 53 leading AI models across text, image, video, and audio from 13 providers.

No vendor lock-in. No juggling multiple SDKs. No surprise bills. Each call is intelligently routed to the lowest-cost stable option.

**→ [Get Started](https://evolink.ai/)**

---

## Why EvoLink?

**Lower cost** — 20–70% cheaper than going direct. Every call is routed to the lowest-cost stable option automatically.

**One integration** — Switch between Claude, GPT, Gemini, Kling, Seedance, Sora, and dozens more by changing a single model parameter. Your code stays the same.

**Production-ready** — 99.97% success rate, 24/7 support, automatic failover. Built for production workloads, not just prototyping.

**Smart Router** — Let `evolink/auto` pick the best model for each request. Optimizes for cost, speed, or quality based on your preference.

---

## Supported Models

### Text Generation (24 models)

| Provider | Models |
|----------|--------|
| Anthropic | Claude Opus 4.5, Claude Opus 4.1, Claude Sonnet 4.5, Claude Sonnet 4.0, Claude Haiku 4.5, Claude Sonnet 3.7, Claude Haiku 3.5 |
| OpenAI | GPT-5.4, GPT-5.2, GPT-5.1, GPT-4o |
| Google | Gemini 3 Pro, Gemini 3 Flash, Gemini 2.5 Pro, Gemini 2.5 Flash |
| DeepSeek | DeepSeek V3, DeepSeek R1, DeepSeek R1 Distill |
| Moonshot | Kimi K2 Turbo, Kimi K2 |
| MiniMax | MiniMax Text |
| xAI | Grok |

### Image Generation (12 models)

| Provider | Models |
|----------|--------|
| Google | Nano Banana 2, Nano Banana Pro |
| BytePlus | Seedream 4.0, Seedream 3.0 |
| OpenAI | GPT Image 1 |
| Alibaba | Qwen Image Edit, Qwen Image Gen |
| Raphael | Raphael |

### Video Generation (16 models)

| Provider | Models |
|----------|--------|
| BytePlus | Seedance 2.0, Seedance Pro, Seedance 1.5 Pro |
| Kling | Kling 3.0, Kling o1, Kling 2.0, Kling 1.6 |
| OpenAI | Sora 2 |
| Google | Veo 3.1, Veo 3.1 Fast |
| Alibaba | Wan 2.6, Wan 2.5 |
| MiniMax | Hailuo 02, Hailuo 2.3 |

### Audio Generation

| Provider | Models |
|----------|--------|
| Suno | Suno |

### Other

| Provider | Models |
|----------|--------|
| — | OmniHuman |

> Full model list with real-time pricing: **[evolink.ai/models](https://evolink.ai/models)**

---

## Quick Start

### 1. Get your API key

Sign up at [evolink.ai](https://evolink.ai/) and create an API key in the dashboard.

### 2. Make your first request

EvoLink is OpenAI-compatible. If your code already works with OpenAI's SDK, just change the base URL and API key:

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://api.evolink.ai/v1",
    api_key="your-evolink-api-key"
)

response = client.chat.completions.create(
    model="claude-sonnet-4-5",
    messages=[{"role": "user", "content": "Hello!"}]
)

print(response.choices[0].message.content)
```

### 3. Or use the Anthropic SDK

```python
import anthropic

client = anthropic.Anthropic(
    base_url="https://api.evolink.ai",
    api_key="your-evolink-api-key"
)

response = client.messages.create(
    model="claude-opus-4-5",
    max_tokens=1024,
    messages=[{"role": "user", "content": "Hello!"}]
)
```

### 4. Generate a video

```bash
curl -X POST https://api.evolink.ai/v1/video/generations \
  -H "Authorization: Bearer your-evolink-api-key" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "seedance-2-0",
    "prompt": "A golden retriever running on a beach at sunset, cinematic 4K"
  }'
```

---

## Use with Claude Code / OpenClaw

Set the environment variable and you're done:

```bash
export ANTHROPIC_BASE_URL=https://api.evolink.ai
export ANTHROPIC_API_KEY=your-evolink-api-key
```

Now every Claude Code session routes through EvoLink — same experience, lower cost.

---

## Pricing Highlights

Every call is routed to the lowest-cost stable option. A few examples:

| Model | Starting Price |
|-------|---------------|
| Nano Banana 2 | from $0.036/img (47% off) |
| Seedance 2.0 | from $0.177/s |
| Veo 3.1 Fast | from $0.125/s |
| Kling 3.0 | from $0.075/s |
| Sora 2 | from $0.210/s |
| Claude Sonnet 4.5 | from $0.80/M input tokens |

> Full pricing: **[evolink.ai/models](https://evolink.ai/models)**

---

## Features

- **Unified API** — OpenAI-compatible endpoint for all 53 models
- **Smart Router** — Automatic model selection optimized for cost/speed/quality
- **Real-time Dashboard** — Track usage, costs, and performance per model
- **Auto Failover** — Seamless fallback if a provider goes down
- **Rate Limit Management** — Built-in queuing and retry logic
- **Multi-modal** — Text, image, video, and audio through one gateway
- **No Minimum Commitment** — Pay as you go, scale when ready

---

## Resources

- 🌐 [Website](https://evolink.ai/)
- 📦 [Model Catalog](https://evolink.ai/models)
- 📖 [Blog & Tutorials](https://evolink.ai/blog)
- 📄 [API Docs](https://evolink.ai/docs)
- 🐙 [GitHub](https://github.com/EvoLinkAI)

---

<div align="center">

**[Get Started →](https://evolink.ai/)**

Join 12,000+ developers who never overpay for AI.

</div>
