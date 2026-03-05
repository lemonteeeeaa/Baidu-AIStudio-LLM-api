# Agent Skills - Baidu AI Studio LLM API

A collection of skills for AI coding agents. Skills are packaged instructions and scripts that extend agent capabilities.

Skills follow the [Agent Skills](https://agentskills.io/) format.

## Available Skills

### baidu-aistudio-llm-api

Baidu AI Studio LLM API calling assistant. Helps developers quickly integrate ERNIE, DeepSeek, Kimi and other large language models from AI Studio. Fully compatible with OpenAI Python SDK.

**Use when:**
- Calling ERNIE (文心) large model API
- Using DeepSeek, Kimi and other open source models
- Integrating AI Studio LLM services
- Asking about AI Studio model usage
- "Help me call ERNIE", "Use Wenxin API", "AI Studio LLM"

**Key Features:**
- Fully compatible with OpenAI SDK
- 1 million free tokens on registration
- Supports multiple model categories:
  - **Text-to-Text**: ERNIE series, DeepSeek, Kimi-K2, Qwen3-Coder
  - **Deep Thinking**: ERNIE X1, DeepSeek-R1 (Chain-of-Thought)
  - **Multimodal**: ERNIE 4.5 VL (Image/Video understanding)
  - **Embedding**: embedding-v1, bge-large-zh
  - **Text-to-Image**: Stable-Diffusion-XL

**Categories covered:**
- Quick Start (API Key, Installation, Basic Call)
- Model Selection Guide
- Common Features (Streaming, Multi-turn, Web Search, Function Calling, Structured Output)
- Advanced Features (Deep Thinking, Multimodal, Text-to-Image)
- Error Handling

## Installation

```bash
npx skills add your-username/aistudio-llm-api
```

## Usage

Skills are automatically available once installed. The agent will use them when relevant tasks are detected.

**Examples:**
```
Help me call ERNIE API
```
```
Use DeepSeek model to generate code
```
```
Connect to AI Studio LLM service
```

## Getting Started

### 1. Get API Key

Visit https://aistudio.baidu.com/account/accessToken to get your Access Token

### 2. Set Environment Variable

```bash
# macOS/Linux
export AI_STUDIO_API_KEY="your-access-token"

# Windows PowerShell
$env:AI_STUDIO_API_KEY="your-access-token"
```

### 3. Install Dependencies

```bash
pip install openai
```

### 4. Basic Usage

```python
import os
from openai import OpenAI

client = OpenAI(
    api_key=os.environ.get("AI_STUDIO_API_KEY"),
    base_url="https://aistudio.baidu.com/llm/lmapi/v3",
)

response = client.chat.completions.create(
    model="ernie-4.5-turbo-128k-preview",
    messages=[
        {"role": "user", "content": "Hello!"}
    ]
)

print(response.choices[0].message.content)
```

## Official Resources

- API Documentation: https://ai.baidu.com/ai-doc/AISTUDIO/rm344erns
- Get Token: https://aistudio.baidu.com/account/accessToken

## Skill Structure

```
aistudio-llm-api/
├── README.md            # This file
├── .claude-plugin/
│   └── marketplace.json # Claude Market registration
└── skills/
    └── baidu-aistudio-llm-api/
        ├── SKILL.md              # Main skill instructions
        ├── references/
        │   ├── models.md         # Complete model list
        │   └── api_params.md     # API parameters reference
        └── scripts/
            ├── test_connection.py # Test API connection
            └── list_models.py     # List available models
```

## License

MIT
