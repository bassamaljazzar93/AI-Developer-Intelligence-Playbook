# Common Problems & Fixes

## 1. الاستهلاك يزيد بسرعة

الأسباب الشائعة:

- جلسة طويلة جدًا.
- طلب scan واسع للمشروع.
- تعديل ملفات كثيرة دفعة واحدة.
- عدم وجود tests واضحة.

الحل:

- قسّم المهمة.
- اطلب قراءة ملفات محددة فقط.
- استخدم plan قبل التنفيذ.
- أوقف الجلسة بعد نقطة مستقرة.
- لا تطلب فحص المشروع كاملًا بلا سبب.

## 2. يطلب موافقات كثيرة

الحل العملي:

- راجع إعدادات الصلاحيات من داخل Claude Code.
- ابدأ بموافقات محدودة.
- اجعل قواعد المشروع واضحة داخل ملفات المشروع.
- لا تفتح كل شيء دفعة واحدة.

ملاحظة من GitHub Issues: بعض المستخدمين أبلغوا عن اختلاف بين إعدادات المستخدم وإعدادات المشروع. لذلك للمشاريع الجدية، اجعل قواعد العمل داخل المشروع نفسه.

## 3. custom slash command لا يظهر

تحقق من:

- المسار الصحيح للأوامر داخل مجلد المشروع.
- أن الملف بصيغة Markdown.
- إعادة تشغيل Claude Code بعد إضافة الأمر.
- استخدام اسم بسيط وواضح للأمر.

ملاحظة من GitHub Issues: ظهرت تقارير عن اختلاف السلوك بين macOS وLinux أو tmux في بعض الحالات.

## 4. Claude يعدّل قبل أن يفهم

استخدم هذا الأسلوب:

```text
Read first. Do not edit files. After reading, explain what you found and wait.
```

ثم:

```text
List the exact files you need before making any change.
```

## 5. نتائج ضعيفة في مشروع كبير

الأسباب المحتملة:

- تعليمات المشروع غير واضحة.
- المهمة كبيرة جدًا.
- لا توجد tests.
- المشروع يحتاج context أكثر.

الحل:

- أضف ملف تعليمات مختصر للمشروع.
- حدد الملفات المطلوبة.
- اطلب خطة فقط.
- نفّذ خطوة واحدة كل مرة.

## 6. مشاكل Windows أو WSL

أفضل نهج:

- استخدم طريقة التثبيت الرسمية للنظام.
- جرّب التيرمنال مباشرة قبل استخدام IDE terminal.
- لا تخلط مسارات Windows وWSL في نفس التشغيل.
- حدّث Claude Code قبل تشخيص المشكلة.

## 7. UI wrappers غير مستقرة

بعض واجهات المجتمع مفيدة، لكن GitHub Issues تظهر مشاكل حول:

- session duplication.
- login state.
- Docker volumes.
- terminal compatibility.
- الفرق بين CLI auth وSDK/API auth.

للمهام الجدية، ابدأ بالـ CLI الرسمي أولًا.

## 8. يعلن النجاح بدون اختبار

استخدم قاعدة واضحة:

```text
Do not claim the task is fixed unless you ran the test. If you did not run it, say that clearly.
```

## 9. يعدل ملفات كثيرة

اطلب منه:

```text
Make the smallest possible change. Do not touch unrelated files.
```

ثم راجع حجم التعديل قبل المتابعة.

## 10. ينسى قيود المشروع

اجعل القيود مكتوبة في ملف واضح داخل المشروع، واطلب منه قراءتها في بداية الجلسة.

مثال:

```text
Read the project instructions first and summarize the rules you will follow.
```
