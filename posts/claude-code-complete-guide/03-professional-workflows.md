# 03 — سير العمل الاحترافي

## لماذا تحتاج Workflow؟

Claude Code يعطي أفضل نتيجة عندما تعمل معه بطريقة منظمة. أكبر خطأ هو أن تطلب مهمة كبيرة مرة واحدة ثم تنتظر نتيجة مثالية.

الطريقة الأفضل:

```text
Read → Plan → Small Step → Verify → Review → Continue
```

## 1. Read

ابدأ دائمًا بالقراءة فقط.

Prompt:

```text
Read the project structure and relevant files only. Do not edit. Summarize what you found and list the files needed for the next step.
```

علامات النجاح:

- يذكر ملفات فعلية.
- يفرق بين backend وfrontend وconfig وtests.
- لا يقترح تغييرًا عامًا بلا سياق.

## 2. Plan

بعد القراءة اطلب خطة.

Prompt:

```text
Create a step-by-step plan. Do not edit. For each step, include files, risk level, and verification method.
```

الخطة الجيدة تحتوي:

- خطوات صغيرة.
- ترتيب منطقي.
- طريقة تحقق لكل خطوة.
- نقطة توقف للمراجعة.

## 3. Small Step

لا تطلب تنفيذ الخطة كلها. اطلب خطوة واحدة فقط.

Prompt:

```text
Implement step 1 only. Keep the change minimal. Do not touch unrelated files.
```

الهدف أن يكون الفرق سهل المراجعة.

## 4. Verify

بعد أي تغيير، اطلب طريقة تحقق.

Prompt:

```text
Show the verification method. If you can run it, run it. If not, explain exactly what I should run.
```

أنواع التحقق:

- Unit test.
- Type check.
- Lint.
- Build.
- Manual browser check.
- Log review.

## 5. Review

قبل المتابعة، اطلب مراجعة الفرق الحالي.

Prompt:

```text
Review the current changes. Identify risks, unintended changes, and missing tests.
```

## 6. Continue

بعد المراجعة اختر:

- المتابعة للخطوة التالية.
- إصلاح خطأ.
- التوقف عند نقطة مستقرة.
- تحديث تعليمات المشروع.

## علامات أن الـ workflow سيء

أوقف أو أعد توجيه الجلسة إذا لاحظت:

- تغييرات كثيرة بلا سبب.
- ادعاء انتهاء المهمة بلا تحقق.
- تكرار نفس الحل الفاشل.
- اقتراح إعادة بناء كاملة لمشكلة صغيرة.
- تجاهل style المشروع.

## قاعدة العمل اليومي

استخدم دورات قصيرة:

```text
20–40 دقيقة عمل → تحقق → مراجعة → حفظ نقطة مستقرة
```

## القرار

أفضل استخدام لـ Claude Code ليس prompt ضخم، بل سير عمل واضح: قراءة، خطة، خطوة، تحقق، مراجعة.
