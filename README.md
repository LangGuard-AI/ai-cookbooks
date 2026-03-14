# AI Cookbooks

Practical, hands-on notebooks for building production-grade AI systems for use with LangGuard. 

Each cookbook covers a specific pattern or capability — governance, observability, evaluation, multi-agent orchestration — with runnable code you can adapt to your own stack.

The cookbooks are designed to work with **any OpenAI-compatible endpoint** (OpenAI, Gemini, OpenRouter, AWS Bedrock, etc.) and export telemetry via **OpenTelemetry** to any OTel-compatible backend, including LangGuard.

## Cookbooks

### [Agentic Governance](agentic_governance_cookbook.ipynb)

Build a governed multi-agent system with policy-as-code guardrails, OpenTelemetry tracing, and automated evaluation.

Based on [OpenAI's Agentic Governance Cookbook](https://github.com/openai/openai-cookbook/blob/main/examples/partners/agentic_governance_guide/) (MIT license), extended with:

- **Provider-agnostic configuration** — swap between OpenAI, Gemini, OpenRouter, or Bedrock by changing two variables
- **OpenTelemetry observability** — traces follow the [GenAI Semantic Conventions](https://opentelemetry.io/docs/specs/semconv/gen-ai/) (`gen_ai.*` attributes) via `opentelemetry-instrumentation-openai-agents-v2`
- **LangGuard integration** — export spans to LangGuard or any OTel-compatible receiver (Jaeger, Datadog, etc.)
- **Connection validation** — startup cell tests both the LLM endpoint and trace backend before running the notebook

**What it builds:** A Private Equity firm AI assistant with specialist agents (deal screening, portfolio management, investor relations), a triage agent with handoffs, centralized guardrails via `openai-guardrails`, eval-driven tuning, and red teaming with Promptfoo.

**Key dependencies:** `openai-agents`, `openai-guardrails`, `opentelemetry-sdk`, `opentelemetry-instrumentation-openai-agents-v2`

## Getting Started

### Google Colab (recommended)

The fastest way to get started — no local install required.

1. Open the notebook in Colab: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LangGuard-AI/ai-cookbooks/blob/main/agentic_governance_cookbook.ipynb)
2. Run the first cell to install dependencies
3. Edit the configuration cell to set your API key, endpoint, model, and LangGuard URL
4. Run the rest of the notebook

> **Note:** Update the Colab link above if the repository owner or branch differs from `LangGuard/ai-cookbooks/main`.

### Local

```bash
python -m venv venv
source venv/bin/activate
pip install jupyter
jupyter notebook
```

Open the cookbook and run the configuration cell at the top to set your API key, endpoint, and model.

## License

MIT
