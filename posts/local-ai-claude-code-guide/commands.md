# Commands

Exact commands for testing local models with Claude Code.

## Windows PowerShell

```powershell
# Install Claude Code
irm https://claude.ai/install.ps1 | iex

# Install Ollama
irm https://ollama.com/install.ps1 | iex

# Check Ollama
ollama -v

# Pull a coding model
ollama pull qwen3.5

# Launch Claude Code with Ollama
ollama launch claude --model qwen3.5
```

## macOS / Linux / WSL

```bash
# Install Claude Code
curl -fsSL https://claude.ai/install.sh | bash

# Install Ollama
curl -fsSL https://ollama.com/install.sh | sh

# Pull model
ollama pull qwen3.5

# Launch Claude Code with Ollama
ollama launch claude --model qwen3.5
```

## Manual Environment Variables

Use this only when you need manual debugging.

### Bash

```bash
export ANTHROPIC_AUTH_TOKEN=ollama
export ANTHROPIC_API_KEY=""
export ANTHROPIC_BASE_URL=http://localhost:11434

claude --model qwen3.5
```

### PowerShell

```powershell
$env:ANTHROPIC_AUTH_TOKEN="ollama"
$env:ANTHROPIC_API_KEY=""
$env:ANTHROPIC_BASE_URL="http://localhost:11434"

claude --model qwen3.5
```

## Important Endpoint Rule

Correct:

```text
http://localhost:11434
```

Wrong:

```text
http://localhost:11434/v1
```

Adding `/v1` with Ollama can cause 404 errors.

## Context Length

Start small on weak devices.

```bash
OLLAMA_CONTEXT_LENGTH=32000 ollama serve
```

For stronger machines:

```bash
OLLAMA_CONTEXT_LENGTH=64000 ollama serve
```

On Windows PowerShell:

```powershell
$env:OLLAMA_CONTEXT_LENGTH="32000"
ollama serve
```

## Quick Test Prompt

```text
Inspect this project. Do not edit anything. Give me a 5-point refactor plan only.
```
