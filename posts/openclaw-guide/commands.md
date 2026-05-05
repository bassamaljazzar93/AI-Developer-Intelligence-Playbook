# OpenClaw — مرجع الأوامر

## التثبيت

```bash
# تثبيت OpenClaw
npm install -g openclaw@latest
# أو عبر pnpm
pnpm add -g openclaw@latest

# الإعداد التفاعلي (مع تشغيل تلقائي عند بدء الجهاز)
openclaw onboard --install-daemon

# إعداد بدون daemon (يدوي)
openclaw onboard
```

---

## الربط مع ChatGPT (اشتراك موجود)

```bash
# إعداد ChatGPT/Codex subscription
openclaw onboard --auth-choice openai-codex

# في حالة بيئة headless (بدون متصفح)
openclaw onboard --auth-choice openai-codex --device-code
```

**إعداد يدوي في `~/.openclaw/openclaw.json`:**
```json
{
  "plugins": {
    "entries": {
      "codex": { "enabled": true }
    }
  },
  "agents": {
    "defaults": {
      "model": { "primary": "openai/gpt-5.5" },
      "agentRuntime": { "id": "codex" }
    }
  }
}
```

---

## الربط مع OpenAI API Key

```bash
openclaw onboard --auth-choice openai-api-key
# أو مباشرة
openclaw onboard --openai-api-key "sk-..."
```

**إعداد في `openclaw.json`:**
```json
{
  "env": { "OPENAI_API_KEY": "sk-..." },
  "agents": {
    "defaults": {
      "model": { "primary": "openai/gpt-5.4-mini" }
    }
  }
}
```

---

## الربط مع Claude (Anthropic)

```bash
openclaw onboard --auth-choice apiKey
```

**إعداد في `openclaw.json`:**
```json
{
  "env": { "ANTHROPIC_API_KEY": "sk-ant-..." },
  "agents": {
    "defaults": {
      "model": { "primary": "anthropic/claude-opus-4-6" }
    }
  }
}
```

---

## الربط مع Gemini

```bash
openclaw onboard --auth-choice gemini-api-key
```

```json
{
  "env": { "GEMINI_API_KEY": "..." },
  "agents": {
    "defaults": {
      "model": { "primary": "google/gemini-3.1-pro-preview" }
    }
  }
}
```

---

## الربط مع نماذج محلية (Ollama — مجاني)

```bash
# تثبيت Ollama أولاً
curl -fsSL https://ollama.ai/install.sh | sh
ollama pull llama3.3

# إعداد OpenClaw
openclaw onboard --auth-choice ollama
```

```json
{
  "agents": {
    "defaults": {
      "model": { "primary": "ollama/llama3.3" }
    }
  }
}
```

---

## إعداد قناة تيليغرام

```bash
# أثناء الـ onboarding اختر Telegram
# أو أضف القناة لاحقاً
openclaw channels add telegram
```

الخطوات:
1. افتح [@BotFather](https://t.me/BotFather) في تيليغرام
2. أرسل `/newbot` واتبع التعليمات
3. احتفظ بالـ token الذي يعطيك إياه
4. الصقه عند طلب OpenClaw

---

## أوامر التشغيل اليومي

```bash
openclaw start          # تشغيل الـ gateway
openclaw stop           # إيقاف
openclaw status         # حالة الـ daemon
openclaw doctor         # تشخيص المشاكل
openclaw update --channel stable   # تحديث
openclaw update --channel beta     # نسخة تجريبية
```

---

## أوامر داخل المحادثة (ترسلها للـ bot)

| الأمر | الوظيفة |
|-------|---------|
| `/status` | حالة الـ agent الحالي |
| `/new` | جلسة جديدة |
| `/reset` | إعادة تعيين الجلسة |
| `/compact` | ضغط السياق (توفير tokens) |
| `/think <level>` | رفع مستوى التفكير (0-3) |
| `/usage full` | عرض استهلاك الـ tokens |
| `/verbose on` | تفاصيل كاملة لكل خطوة |
| `/trace on` | تتبع الأوامر المنفّذة |
| `/restart` | إعادة تشغيل الـ agent |

---

## واجهة الويب

```
http://127.0.0.1:18789/
```
تفتح من المتصفح على نفس الجهاز — لوحة تحكم كاملة للجلسات والإعدادات والقنوات.

---

## نماذج مدعومة (مختصر)

| المزود | معرّف الموديل | المصادقة |
|--------|--------------|---------|
| OpenAI API | `openai/gpt-5.5` | `OPENAI_API_KEY` |
| OpenAI اقتصادي | `openai/gpt-5.4-mini` | `OPENAI_API_KEY` |
| ChatGPT اشتراك | `openai/gpt-5.5` + Codex runtime | OAuth |
| Claude | `anthropic/claude-opus-4-6` | `ANTHROPIC_API_KEY` |
| Gemini | `google/gemini-3.1-pro-preview` | `GEMINI_API_KEY` |
| DeepSeek | `deepseek/deepseek-v4-flash` | `DEEPSEEK_API_KEY` |
| Ollama محلي | `ollama/llama3.3` | بدون مفتاح |
| OpenRouter | `openrouter/auto` | `OPENROUTER_API_KEY` |
