# Operations Guide

Operational guide for testing Claude Code with local or low-cost AI models.

## Practical Objective

The goal is not to prove that local AI is better than Claude.

The goal is to answer:

> Can local AI reduce premium Claude usage in daily coding tasks?

## Recommended Path

1. Install Claude Code.
2. Install Ollama.
3. Pull one coding-focused model.
4. Launch Claude Code with Ollama.
5. Test one real task.
6. Record results.
7. Decide within 24 hours.

## First 60 Minutes

```bash
ollama pull qwen3.5
ollama launch claude --model qwen3.5
```

Test prompt:

```text
Inspect this project. Do not edit files. Give me a 5-point refactor plan only.
```

## Next 90 Minutes

Test exactly three tasks:

1. Explain a project structure.
2. Fix one small bug.
3. Generate one test.

## Evaluation Criteria

| Criterion | Question |
|---|---|
| Speed | Is it fast enough to use daily? |
| Tool use | Does it use Claude Code tools correctly? |
| Code quality | Are edits accurate? |
| Stability | Does it hang or fail often? |
| Value | Does it reduce paid model usage? |

## Common Issues

### 404 Error

Likely cause: wrong base URL.

Use:

```text
http://localhost:11434
```

Do not use:

```text
http://localhost:11434/v1
```

### Model Does Not Use Tools

Likely cause: the model is not good for agentic coding.

Fix: use a coding or agentic model, not a general chat model.

### Slow or Hanging

Likely cause:

- context too high
- CPU overload
- weak hardware
- model too large

Fix:

Start with 16K or 32K context.

### Weak Output

Likely cause: small model such as 7B or 8B.

Fix:

Use small models only for small tasks.

## Final Decision

Keep the setup only if it passes real daily tasks.

If it does not help, stop polishing and move to a stronger route such as LM Studio, llama.cpp, or hosted models.
