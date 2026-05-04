# 02 — إعداد المشروع والذاكرة

## لماذا يحتاج Claude Code إلى تعليمات؟

Claude Code يستطيع قراءة الملفات، لكنه لا يعرف تلقائيًا قواعد مشروعك الداخلية. إذا لم تعطِه قواعد واضحة، سيحاول الاستنتاج من الكود، وقد ينجح أحيانًا ويفشل أحيانًا.

ملفات التعليمات تجعل Claude يعرف:

- كيف يشغل المشروع.
- كيف يختبر التغييرات.
- ما أسلوب كتابة الكود.
- ما الملفات التي يجب الحذر معها.
- ما قواعد naming.
- كيف يكتب commit message.
- ما الذي يعتبر تغييرًا غير مرغوب.

## CLAUDE.md

استخدم `CLAUDE.md` عندما تريد تعليمات خاصة بـ Claude Code.

مثال محتوى مختصر:

```md
# Project Instructions

## Run
Use the documented commands in README.

## Testing
Before saying a task is done, run the smallest relevant test when possible.

## Code Style
Keep changes minimal. Do not reformat unrelated files.

## Safety
Do not edit generated files unless asked.
Do not add secrets or credentials.

## Response Style
Summarize changes, affected files, and test result.
```

## AGENTS.md

استخدم `AGENTS.md` عندما تريد تعليمات عامة تصلح لأكثر من agent أو tool. هذا مفيد إذا كنت تستخدم Claude Code مع Codex أو أدوات AI أخرى.

مثال:

```md
# Agent Rules

- Read before editing.
- Prefer small changes.
- Explain risks before large refactors.
- Do not claim tests passed unless actually run.
- Keep public documentation free of secrets.
```

## ماذا تكتب في تعليمات المشروع؟

### 1. وصف سريع للمشروع

اكتب فقرة واحدة:

```md
This is a Flask web app for managing inspection reports. The backend is Python, the frontend is simple HTML templates, and reports are exported as PDF.
```

### 2. أوامر التشغيل

```md
## Run
python app.py
```

### 3. أوامر الاختبار

```md
## Test
pytest
```

أو إذا لا يوجد tests:

```md
No automated tests yet. For changes, explain manual verification steps.
```

### 4. الملفات المهمة

```md
## Important Files
- app.py: main backend
- templates/: UI pages
- reports/: generated outputs
```

### 5. ممنوعات واضحة

```md
## Do Not
- Do not edit generated reports.
- Do not rename public routes without asking.
- Do not remove Arabic RTL support.
```

## التعليمات يجب أن تكون قصيرة

ملف تعليمات طويل جدًا قد يضعف الفائدة. الأفضل:

- عناوين واضحة.
- نقاط قصيرة.
- أمثلة عملية.
- تحديث مستمر بعد الأخطاء.

## متى تحدث التعليمات؟

حدث الملف عندما:

- Claude يكرر نفس الخطأ.
- تكتشف أمر تشغيل جديد.
- تضيف قاعدة style مهمة.
- تغير طريقة الاختبار.
- تضيف folder حساس.

## Prompt لتحديث التعليمات

بعد جلسة ناجحة:

```text
Based on what we learned, suggest a small update to CLAUDE.md so future sessions avoid the same mistakes.
```

## أخطاء شائعة

### خطأ 1: تعليمات عامة جدًا

غير مفيد:

```md
Write good code.
```

أفضل:

```md
Keep changes minimal and avoid modifying unrelated formatting.
```

### خطأ 2: عدم ذكر الاختبار

إذا لم يعرف Claude كيف يختبر، سيخمن أن المهمة انتهت.

### خطأ 3: تعليمات متضاربة

لا تكتب:

```md
Always refactor fully.
Keep changes minimal.
```

اختر القاعدة حسب طبيعة المشروع.

## القرار

أي مشروع تريد استخدام Claude Code معه أكثر من مرة يحتاج ملف تعليمات. بدون هذا الملف، ستكرر نفس التوجيهات يدويًا في كل جلسة.
