# 10 — دليل المشاكل الميداني

هذا الفصل يجمع المشاكل التي تتكرر في الاستخدام الحقيقي، بناءً على الوثائق، GitHub Issues، وتجارب المستخدمين.

## المشكلة 1: Claude يقرأ كثيرًا ثم لا ينجز

### السبب المحتمل

النطاق واسع جدًا أو الهدف غير واضح.

### الحل

اكتب:

```text
Limit your inspection to the smallest set of files needed. If you need more files, explain why first.
```

ثم حدد نطاقًا:

```text
Focus only on the payment flow.
```

## المشكلة 2: Claude يعدّل ملفات غير مرتبطة

### السبب المحتمل

المهمة مفتوحة أو لا توجد قاعدة “minimal change”.

### الحل

```text
Keep changes minimal. Do not touch unrelated files or formatting.
```

بعد التعديل اطلب:

```text
List every changed file and why it was necessary.
```

## المشكلة 3: يعلن أن المهمة انتهت بدون اختبار

### السبب المحتمل

لا توجد قاعدة تحقق واضحة.

### الحل

```text
Do not claim completion unless you ran a verification step or clearly state it was not run.
```

## المشكلة 4: custom command لا يظهر

### تحقق من

- الملف داخل مجلد commands الصحيح.
- الملف بصيغة Markdown.
- اسم الملف بسيط.
- إعادة تشغيل Claude Code.
- تجربة الأمر خارج tmux إذا كنت على Linux.

## المشكلة 5: مشاكل Windows أو WSL

### نصائح عملية

- استخدم طريقة التثبيت الرسمية للنظام.
- جرّب PowerShell أو terminal مباشر قبل IDE terminal.
- لا تخلط مسارات Windows وWSL في نفس المشروع.
- افتح المشروع من البيئة التي ستعمل فيها فعلًا.

## المشكلة 6: الاستهلاك ينتهي بسرعة

### الأسباب

- جلسة طويلة.
- مشروع كبير.
- مهام مفتوحة.
- لا توجد tests.
- إعادة محاولات كثيرة.

### الحل

- قسّم المهمة.
- اطلب ملخصًا وانتقل لجلسة جديدة.
- اجعل كل مرحلة لها نتيجة قابلة للقياس.

## المشكلة 7: جودة الإجابة تقل في المهام الكبيرة

### السبب

Claude Code يحتاج سياقًا منظمًا ومراحل صغيرة.

### الحل

استخدم:

```text
Plan first. Do not implement yet.
```

ثم:

```text
Implement only the first step.
```

## المشكلة 8: UI wrappers غير مستقرة

بعض واجهات المجتمع مفيدة، لكنها تضيف طبقة مشاكل مثل:

- تسجيل الدخول.
- الجلسات.
- Docker volumes.
- terminal compatibility.
- فرق بين auth عبر CLI وAPI.

لذلك للمهام الجدية، ابدأ بالـ CLI الرسمي.

## المشكلة 9: Claude لا يلتزم بأسلوب المشروع

### الحل

أضف قواعد واضحة في ملف تعليمات المشروع:

```md
## Code Style
- Keep changes minimal.
- Follow existing naming.
- Do not reformat unrelated code.
- Explain any deviation.
```

## المشكلة 10: يكرر نفس الخطأ

بعد حل الخطأ، اطلب:

```text
Suggest one small update to the project instructions so this mistake is not repeated.
```

## طريقة تشخيص سريعة

اسأل نفسك:

1. هل أعطيته نطاقًا واضحًا؟
2. هل أعطيته طريقة تحقق؟
3. هل طلبت خطة قبل التنفيذ؟
4. هل المشروع فيه تعليمات؟
5. هل التغيير كبير جدًا؟

## القرار

معظم مشاكل Claude Code ليست “الأداة سيئة” فقط. غالبًا هي غياب نطاق، غياب تحقق، أو جلسة طويلة جدًا. أصلح workflow قبل أن تغيّر الأداة.
