# Local AI with Claude Code

Arabic practical guide for running local or low-cost AI models with Claude Code.

## Goal

Use local models to reduce cost, improve privacy for experiments, and keep hosted premium models for hard architecture and production-level decisions.

## Recommended Start

Start with **Ollama + Claude Code**.

```bash
ollama launch claude --model qwen3.5
```

Do not start with ten routes. Prove one route first.

## How It Works

Claude Code does not run the model directly. It connects to an API endpoint. A local engine provides an Anthropic-compatible API or a gateway translates requests.

## Backend Options

| Backend | Best Use | Verdict |
|---|---|---|
| Ollama | Fastest local start | Start here |
| LM Studio | GUI and model testing | Good second option |
| llama.cpp | GGUF and advanced performance control | Use after basics |
| LiteLLM Router | Multi-model routing | Later stage |

## Files

- [commands.md](commands.md): installation and run commands.
- [download-strategy.md](download-strategy.md): model and download strategy.
- [operations-guide.md](operations-guide.md): troubleshooting and execution plan.
- [slides.html](slides.html): browser-based slide deck.
- [assets/README.md](assets/README.md): slide image asset notes.

## 24-Hour Decision

Answer one question only:

> Does this setup reduce real Claude usage in daily coding tasks?

If yes, keep it. If not, stop polishing and move to the next route.
