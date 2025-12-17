# Zhihuishu-Auto-QA

AI-Based Zhihuishu Auto QA Script

## Installation

First, install the required dependencies.

```sh
uv venv
.venv\Scripts\activate  # Windows
# source .venv/bin/activate  # macOS/Linux
uv sync
```

## Configuration

Copy `.env.example` to `.env` and fill in your configuration:

```sh
cp .env.example .env
```

`.env` file content:

```env
API_KEY=your_api_key_here
BASE_URL=https://api.deepseek.com/v1
MODEL_NAME=deepseek-chat

# Optional: proxy for downloading driver
# PROXY=http://127.0.0.1:7890
```

### Supported Platforms

Any OpenAI-compatible API is supported. Common examples:

| Platform | BASE_URL | MODEL_NAME |
|----------|----------|------------|
| DeepSeek | `https://api.deepseek.com/v1` | `deepseek-chat` |
| SiliconFlow | `https://api.siliconflow.cn/v1` | `deepseek-ai/DeepSeek-V3` |
| OpenAI | `https://api.openai.com/v1` | `gpt-4o` |

### Edge Driver

The script uses Microsoft Edge browser. Driver loading:

1. First tries local driver (`msedgedriver.exe` on Windows, `msedgedriver` on macOS/Linux)
2. If local driver fails, downloads automatically via `webdriver-manager`
3. Set `PROXY` in `.env` if you need a proxy for downloading

## Usage

We suggest responding to questions before asking new ones, because you cannot respond to questions that were asked by yourself.

```bash
uv run main.py
```
