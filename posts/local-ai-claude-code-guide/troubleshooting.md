# مشاكل شائعة وحلولها — Local AI مع Claude Code

## أمر التشخيص الأول

```bash
echo $ANTHROPIC_BASE_URL    # يجب: http://localhost:11434
echo $ANTHROPIC_API_KEY     # يجب: ollama
ollama list                 # تحقق أن النموذج محمّل
```

---

## المشكلة: خطأ 404

**السبب:** عنوان الـ API خاطئ — أضفت `/v1` في النهاية.

```bash
# ✓ صحيح
export ANTHROPIC_BASE_URL=http://localhost:11434

# ✗ خاطئ — يسبب 404
export ANTHROPIC_BASE_URL=http://localhost:11434/v1
```

---

## المشكلة: النموذج لا يستخدم أدوات Claude Code

**السبب:** النموذج ليس مخصصاً للبرمجة الوكيلة.

**الحل:** استخدم نموذج كود متخصصاً:

```bash
ollama pull qwen2.5-coder
claude --model qwen2.5-coder
```

تجنب نماذج المحادثة العامة (chat models) لمهام الكود الوكيلة.

---

## المشكلة: بطء شديد أو توقف

**الأسباب:**
- سياق كبير على جهاز ضعيف
- الجهاز يعمل بـ CPU فقط بدون GPU
- النموذج أكبر من طاقة الجهاز

**الحل:**

```bash
# قلّل السياق وأعد تشغيل Ollama
OLLAMA_CONTEXT_LENGTH=16000 ollama serve

# أو استخدم نموذجاً أصغر
ollama pull qwen2.5-coder:7b
claude --model qwen2.5-coder:7b
```

---

## المشكلة: Ollama لا يستجيب

**تحقق من حالة الـ server:**

```bash
ollama list                       # يعرض النماذج المحملة
ollama serve                      # شغّل الـ server يدوياً
curl http://localhost:11434       # اختبر الاتصال
```

---

## المشكلة: نتيجة ضعيفة أو خاطئة

**الأسباب:**
- النموذج صغير جداً (7B أو 8B) للمهمة
- المهمة معقدة تتطلب Claude الأصلي

**القاعدة:** النماذج المحلية للمهام الصغيرة والتكرارية. Claude الأصلي للقرارات الكبيرة.

---

## المشكلة: Claude Code لا يتصل بـ Ollama

**تحقق من المتغيرات:**

```bash
# Linux / macOS
export ANTHROPIC_BASE_URL=http://localhost:11434
export ANTHROPIC_API_KEY=ollama
claude --model qwen2.5-coder
```

```powershell
# Windows PowerShell
$env:ANTHROPIC_BASE_URL="http://localhost:11434"
$env:ANTHROPIC_API_KEY="ollama"
claude --model qwen2.5-coder
```

**ملاحظة:** المتغيرات تُضبط لجلسة الـ terminal الحالية فقط. يجب إعادة ضبطها في كل جلسة جديدة، أو إضافتها لملف `.bashrc` / `$PROFILE`.
