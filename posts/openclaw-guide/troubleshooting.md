# OpenClaw — مشاكل شائعة وحلولها

## أمر التشخيص الأول

```bash
openclaw doctor
```
يكشف أغلب المشاكل في dmPolicy، الـ daemon، والـ auth تلقائياً.

---

## المشكلة: التثبيت يفشل أو يعطي أخطاء

**السبب الأكثر:** Node.js نسخة قديمة.

```bash
node --version   # يجب أن تكون 24.x أو 22.14+
```

**الحل:**
```bash
# تثبيت Node 24 عبر nvm
nvm install 24
nvm use 24
npm install -g openclaw@latest
```

---

## المشكلة: الـ bot لا يرد على رسائلي في تيليغرام

**الأسباب المحتملة:**

1. **الـ daemon لم يشتغل:**
```bash
openclaw status
openclaw start
```

2. **dmPolicy يحجب رسائلك:**
```json
{ "gateway": { "dmPolicy": "open" } }
```

3. **الـ bot token خاطئ:**
- افتح `~/.openclaw/openclaw.json` وتحقق من الـ token
- أو أعد إعداد القناة: `openclaw channels add telegram`

---

## المشكلة: ChatGPT يطلب login مجدداً باستمرار

**السبب:** انتهاء صلاحية الـ OAuth token.

```bash
openclaw onboard --auth-choice openai-codex
```
أعد المصادقة. إذا كانت بيئة headless:
```bash
openclaw onboard --auth-choice openai-codex --device-code
```

---

## المشكلة: الـ agent يعمل بـ API key بدل اشتراك ChatGPT

**التحقق:** ارسل `/usage full` في المحادثة — إذا يحسب tokens ويفرض رسوم فهو يستخدم API key.

**الحل:** أضف في `openclaw.json`:
```json
{
  "plugins": { "entries": { "codex": { "enabled": true } } },
  "agents": {
    "defaults": {
      "agentRuntime": { "id": "codex" }
    }
  }
}
```

---

## المشكلة: الـ gateway يتوقف بعد إغلاق الـ terminal

**السبب:** لم يُثبَّت الـ daemon.

```bash
openclaw onboard --install-daemon
# أو لاحقاً:
openclaw daemon install
openclaw start
```

---

## المشكلة: Ollama لا يتصل

**تحقق أن Ollama يشتغل:**
```bash
ollama list           # يعرض النماذج المثبتة
ollama serve          # تشغيل الـ server إذا متوقف
curl http://localhost:11434   # اختبار الاتصال
```

**تحقق من الـ model name:**
```bash
ollama pull llama3.3
# في openclaw.json استخدم نفس الاسم بالضبط
```

---

## المشكلة: الـ agent ينفّذ أوامر خاطئة أو يبالغ

**الحل الفوري:** ارسل `/reset` لإعادة الجلسة.

**الحل الدائم:** حدد صلاحيات في `openclaw.json`:
```json
{
  "agents": {
    "defaults": {
      "sandbox": { "mode": "non-main" }
    }
  }
}
```
هذا يمنع التنفيذ الواسع في الـ group chats ويحتاج تأكيد للعمليات الحساسة.

---

## المشكلة: استهلاك tokens مرتفع جداً

**أوامر مساعدة:**
```
/compact        ← يضغط السياق الحالي
/new            ← يبدأ جلسة جديدة نظيفة
/usage off      ← يوقف عرض التفاصيل
```

**تغيير لنموذج أخف:**
```json
{ "agents": { "defaults": { "model": { "primary": "openai/gpt-5.4-mini" } } } }
```
