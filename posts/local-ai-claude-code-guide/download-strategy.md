# Download Strategy

This file defines how to choose models without wasting time.

## Rule

Do not download many models randomly. Pick two or three, test them, then decide.

## Recommended Order

| Rank | Model / Route | Use |
|---|---|---|
| 1 | Qwen3.5 / Qwen Coder | Main local coding test |
| 2 | GLM Flash style models | Agentic coding experiments |
| 3 | Kimi / MiniMax via cloud route | Stronger non-local option |
| 4 | 7B / 8B models | Small tasks only |

## What To Avoid

Avoid using small chat models as a full Claude replacement.

Small models are useful for:

- explaining small files
- simple scripts
- short refactors
- quick summaries

Small models are weak for:

- full repository analysis
- multi-file edits
- long agentic coding loops
- architecture decisions

## Hardware Logic

| Device Type | Suggested Context | Notes |
|---|---:|---|
| CPU only | 16K or 32K | Keep expectations low |
| Laptop with decent RAM | 32K | Good first test |
| Strong GPU / high VRAM | 64K+ | Better for agentic coding |

## Testing Matrix

Use the same task across models.

| Model | Speed | Tool Use | Code Quality | Daily Use? |
|---|---|---|---|---|
| qwen3.5 |  |  |  |  |
| second model |  |  |  |  |
| third model |  |  |  |  |

## Decision Rule

Keep a model only if it helps with daily tasks. Do not keep a model because it is interesting.
