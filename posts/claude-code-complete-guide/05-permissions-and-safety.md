# 05 — الصلاحيات والأمان التشغيلي

## لماذا هذا الفصل مهم؟

Claude Code يعمل داخل مشروعك. لذلك يجب أن توازن بين السرعة والأمان. إعطاء موافقات واسعة جدًا قد يسرّع العمل، لكنه يزيد احتمال تعديل شيء غير مقصود.

## الفكرة الأساسية

ابدأ بمبدأ:

```text
Least privilege first, expand only when needed.
```

أي: أعطه أقل صلاحية تكفي للمهمة، ثم وسّع تدريجيًا عند الحاجة.

## مستويات الثقة

### مستوى 1: قراءة فقط

مناسب في أول جلسة أو مشروع جديد.

استخدمه عندما تريد:

- فهم المشروع.
- تلخيص الملفات.
- اكتشاف structure.
- اقتراح خطة.

### مستوى 2: تعديل محدود

مناسب بعد أن يثبت أنه فهم المشروع.

استخدمه عندما تريد:

- تعديل ملف واحد.
- إصلاح bug صغير.
- إضافة test صغير.
- تحديث documentation.

### مستوى 3: تنفيذ workflow

مناسب عندما يكون عندك:

- git clean state.
- tests واضحة.
- تعليمات مشروع مكتوبة.
- مراجعة diff بعد كل مرحلة.

## قواعد عملية

### 1. لا تبدأ بصلاحيات واسعة

لا تبدأ جلسة جديدة في مشروع جديد وأنت تسمح بكل شيء. ابدأ بقراءة وخطة.

### 2. افصل بين القراءة والتنفيذ

Prompt جيد:

```text
Read and plan only. Do not change files yet.
```

### 3. راجع قبل المتابعة

بعد أي تغيير:

```text
Show a summary of changed files and what each change does.
```

### 4. لا تسمح بتغييرات غير مرتبطة

```text
Keep changes limited to the requested task. Do not refactor unrelated code.
```

## ملفات حساسة يجب حمايتها

راقب الملفات التي تحتوي:

- credentials.
- deployment config.
- production settings.
- billing settings.
- database migrations.
- generated outputs.
- public routes.

## ماذا تكتب في تعليمات المشروع؟

أضف قسمًا مثل:

```md
## Safety Rules

- Do not add secrets.
- Do not modify deployment files unless asked.
- Keep changes minimal.
- Do not rename public APIs without approval.
- State clearly when tests were not run.
```

## مشكلة شائعة من المجتمع

في GitHub Issues، بعض المستخدمين أشاروا إلى أن الإعدادات العامة قد لا تتصرف دائمًا كما يتوقعون عبر كل المشاريع. لذلك عمليًا، الأفضل أن تضع قواعد المشروع المهمة داخل المشروع نفسه حتى تكون واضحة في كل جلسة.

## كيف تعرف أنك أعطيت صلاحيات أكثر من اللازم؟

علامات الخطر:

- Claude عدّل ملفات لم تطلبها.
- تغيّر formatting واسع.
- ظهرت ملفات generated في diff.
- حاول حل المشكلة بإعادة بناء كبيرة.
- قال إن المهمة انتهت بدون تحقق.

## Prompt آمن قبل أي مهمة حساسة

```text
Before doing anything, list the files you expect to touch and why. Do not edit yet.
```

## القرار

الصلاحيات ليست هدفًا. الهدف هو workflow آمن وسريع. أعطِ Claude Code مساحة عمل كافية، لكن اجعل كل خطوة قابلة للمراجعة والاسترجاع.
