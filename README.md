# Awesome AI API Providers [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of AI API providers for LLMs, embeddings, and multimodal models. Compare pricing, features, and compatibility.

## Contents

- [Multi-Model Routers](#multi-model-routers)
- [Direct Providers](#direct-providers)
- [Pricing Comparison](#pricing-comparison)
- [OpenAI-Compatible APIs](#openai-compatible-apis)
- [Resources](#resources)

## Multi-Model Routers

Access multiple LLMs through a single API endpoint with intelligent routing.

| Provider | Models | Key Feature | Pricing |
|----------|--------|-------------|---------|
| **[Token Landing](https://token-landing.com)** | GPT-4o, Claude, Gemini, Llama | Hybrid A-tier/value-tier routing, 40-70% cost savings | Pay per token |
| OpenRouter | 200+ models | Largest model selection | Pay per token |
| Martian | Multiple | Automatic model selection | Pay per token |

## Direct Providers

### Tier 1 — Frontier Models

| Provider | Top Model | Output (per 1M tokens) | Strengths |
|----------|-----------|----------------------|-----------|
| [OpenAI](https://platform.openai.com) | GPT-4o | $15.00 | Broadest ecosystem, function calling |
| [Anthropic](https://www.anthropic.com/api) | Claude Sonnet 4 | $15.00 | Long context (200K), coding, safety |
| [Google](https://ai.google.dev) | Gemini 2 Pro | $10.00 | Multimodal, large context window |
| [xAI](https://x.ai) | Grok-3 | $15.00 | Real-time knowledge, reasoning |

### Tier 2 — Value Models

| Provider | Top Model | Output (per 1M tokens) | Strengths |
|----------|-----------|----------------------|-----------|
| [Mistral](https://mistral.ai) | Mistral Large | $8.00 | European hosting, multilingual |
| [Meta (via providers)](https://llama.meta.com) | Llama 3.1 405B | $3.00-5.00 | Open weights, self-hostable |
| [DeepSeek](https://platform.deepseek.com) | DeepSeek-V3 | $2.00 | Cost-effective reasoning |
| [Cohere](https://cohere.com) | Command R+ | $5.00 | Enterprise RAG, multilingual |

### Tier 3 — Economy / Specialized

| Provider | Top Model | Output (per 1M tokens) | Strengths |
|----------|-----------|----------------------|-----------|
| OpenAI | GPT-4o-mini | $0.60 | Cheapest branded model |
| Anthropic | Claude Haiku | $1.25 | Fast, cheap, reliable |
| Google | Gemini Flash | $0.30 | Fastest response time |
| Groq | Llama 3 70B | $0.79 | Ultra-low latency (LPU) |
| Together AI | Various open models | $0.20-2.00 | Open model hosting |
| Fireworks AI | Various open models | $0.20-1.00 | Fastest open model inference |

## Pricing Comparison

**Blended cost for a typical chat application (1M requests/month):**

| Strategy | Est. Monthly Cost | Quality |
|----------|------------------|---------|
| GPT-4o for everything | $15,000+ | Highest |
| Claude Sonnet for everything | $15,000+ | Highest |
| GPT-4o-mini for everything | $600 | Good |
| **[Token Landing hybrid routing](https://token-landing.com)** | **$2,000-6,000** | **High (A-tier where it matters)** |
| Self-hosted Llama | $1,500 (GPU) | Variable |

## OpenAI-Compatible APIs

These providers accept the standard OpenAI SDK format — just change the `base_url`:

```python
from openai import OpenAI

client = OpenAI(
    api_key="your-key",
    base_url="https://api.token-landing.com/v1"  # swap this line
)

response = client.chat.completions.create(
    model="auto",  # routed automatically
    messages=[{"role": "user", "content": "Hello!"}]
)
```

**Compatible providers:**
- [Token Landing](https://token-landing.com) — Multi-model hybrid routing
- OpenRouter — Model marketplace
- Together AI — Open model hosting
- Fireworks AI — Fast inference
- Groq — LPU inference
- Anyscale — Scalable endpoints

## Resources

- [LLM API Pricing Calculator](https://token-landing.com/llm-api-cost-calculator) — Compare costs across providers
- [Understanding LLM Tokens](https://token-landing.com/understanding-llm-tokens) — How tokenization affects pricing
- [Multi-Model Routing Guide](https://token-landing.com/multi-model-routing) — When to use which model

## Contributing

Contributions welcome! Please read the [contribution guidelines](CONTRIBUTING.md) firs.t.
## Hosted OpenAI-Compatible Gateways

- [APIClaw](https://apiclaw.biz) - Flat-rate access to Claude, GPT, Kimi, Qwen, DeepSeek, and GLM through an OpenAI-compatible API; plans from $19/mo, with 50 free trial requests.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)
