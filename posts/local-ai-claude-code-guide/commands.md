# الأوامر المرجعية — Local AI مع Claude Code

## Windows PowerShell

```powershell
# ثبّت Claude Code
npm install -g @anthropic-ai/claude-code

# ثبّت Ollama
winget install Ollama.Ollama
# أو من ollama.com/download

# حمّل نموذج الكود
ollama pull qwen2.5-coder

# اربط Claude Code بـ Ollama وشغّله
$env:ANTHROPIC_BASE_URL="http://localhost:11434"
$env:ANTHROPIC_API_KEY="ollama"
claude --model qwen2.5-coder
```

## macOS / Linux

```bash
# ثبّت Claude Code
npm install -g @anthropic-ai/claude-code

# ثبّت Ollama
curl -fsSL https://ollama.com/install.sh | sh

# حمّل نموذج الكود
ollama pull qwen2.5-coder

# اربط Claude Code بـ Ollama وشغّله
export ANTHROPIC_BASE_URL=http://localhost:11434
export ANTHROPIC_API_KEY=ollama
claude --model qwen2.5-coder
```

## متغيرات الاتصال الضرورية

المتغيران الوحيدان المطلوبان للاتصال بـ Ollama:

### Bash / Zsh

```bash
export ANTHROPIC_BASE_URL=http://localhost:11434
export ANTHROPIC_API_KEY=ollama

claude --model qwen2.5-coder
```

### PowerShell

```powershell
$env:ANTHROPIC_BASE_URL="http://localhost:11434"
$env:ANTHROPIC_API_KEY="ollama"

claude --model qwen2.5-coder
```

## نقطة الاتصال المهمة

```text
# ✓ صحيح — بدون /v1
http://localhost:11434

# ✗ خاطئ — يسبب خطأ 404 مع Ollama
http://localhost:11434/v1
```

## إعداد السياق

ابدأ بسياق صغير على الأجهزة الضعيفة.

```bash
# للأجهزة الضعيفة (CPU فقط)
OLLAMA_CONTEXT_LENGTH=16000 ollama serve

# للأجهزة القوية (GPU)
OLLAMA_CONTEXT_LENGTH=64000 ollama serve
```

```powershell
# Windows
$env:OLLAMA_CONTEXT_LENGTH="32000"
ollama serve
```

## مراقبة النماذج

```bash
ollama list            # النماذج المحملة
ollama ps              # النماذج الشغّالة حالياً
ollama stop MODEL      # أوقف نموذجاً لتحرير الذاكرة
```

## اختبار سريع بعد الربط

```text
افهم هيكل هذا المشروع. لا تعدل أي ملف. أعطني 5 نقاط للتحسين فقط.
```
