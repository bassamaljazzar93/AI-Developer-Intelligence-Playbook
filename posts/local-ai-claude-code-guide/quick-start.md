# البداية السريعة — Local AI مع Claude Code

هدف واحد: تشغيل Claude Code مع Ollama خلال 15 دقيقة واختبار مهمة حقيقية.

---

## الخطوات (Linux / macOS)

```bash
# 1. ثبّت Ollama
curl -fsSL https://ollama.com/install.sh | sh

# 2. حمّل نموذج مخصص للكود
ollama pull qwen2.5-coder

# 3. ثبّت Claude Code
npm install -g @anthropic-ai/claude-code

# 4. اضبط متغيرات الاتصال
export ANTHROPIC_BASE_URL=http://localhost:11434
export ANTHROPIC_API_KEY=ollama

# 5. شغّل Claude Code مع النموذج
claude --model qwen2.5-coder
```

---

## الخطوات (Windows PowerShell)

```powershell
# 1. ثبّت Ollama
winget install Ollama.Ollama
# أو من الموقع مباشرة: https://ollama.com/download

# 2. حمّل نموذج مخصص للكود
ollama pull qwen2.5-coder

# 3. ثبّت Claude Code
npm install -g @anthropic-ai/claude-code

# 4. اضبط متغيرات الاتصال
$env:ANTHROPIC_BASE_URL="http://localhost:11434"
$env:ANTHROPIC_API_KEY="ollama"

# 5. شغّل Claude Code مع النموذج
claude --model qwen2.5-coder
```

---

## اختبار سريع

بعد التشغيل، جرّب هذا الـ prompt داخل Claude Code:

```text
افهم هيكل هذا المشروع. لا تعدل أي ملف. أعطني 5 نقاط للتحسين فقط.
```

إذا رد بفهم واضح للمشروع — الإعداد يعمل.

---

## نقطة الاتصال المهمة

| الحالة | العنوان |
|--------|---------|
| ✓ صحيح | `http://localhost:11434` |
| ✗ خاطئ | `http://localhost:11434/v1` — يسبب خطأ 404 |

---

## القرار خلال 24 ساعة

اختبر مهمة حقيقية واحدة. إذا وفّر وقتاً وتكلفة — احتفظ به. إذا لم يساعد — انتقل لمسار أقوى.
