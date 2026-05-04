# 04 — الأوامر المخصصة Custom Slash Commands

## لماذا تستخدم أوامر مخصصة؟

عندما تكرر نفس prompt كل يوم، حوّله إلى أمر. هذا يجعل العمل أسرع وأكثر ثباتًا.

بدل أن تكتب كل مرة:

```text
راجع الفرق الحالي وابحث عن bugs ومشاكل tests...
```

تجعلها أمرًا مثل:

```text
/review
```

## متى تنشئ أمرًا؟

أنشئ أمرًا عندما يكون لديك مهمة متكررة مثل:

- مراجعة diff.
- توليد test plan.
- فحص security risks.
- تحديث documentation.
- كتابة commit message.
- تلخيص حالة المشروع.
- البحث عن dead code.

## مكان الأوامر

عادة تكون أوامر المشروع داخل:

```text
.claude/commands/
```

كل أمر يكون ملف Markdown.

## مثال: أمر مراجعة

ملف:

```text
.claude/commands/review.md
```

المحتوى:

```md
Review the current git diff. Do not edit files.
Focus on:
- bugs
- missing tests
- risky assumptions
- unnecessary complexity
- unclear naming

Return findings ordered by severity.
```

الاستخدام داخل Claude Code:

```text
/review
```

## مثال: أمر خطة اختبار

```text
.claude/commands/test-plan.md
```

```md
Create a focused test plan for the current change.
Include:
- what to test
- why it matters
- exact command if known
- manual verification steps if automated tests do not exist
Do not edit files.
```

## مثال: أمر تحديث التوثيق

```text
.claude/commands/docs-update.md
```

```md
Read the implementation first.
Update documentation only to match actual behavior.
Do not invent features.
List files changed and what each update explains.
```

## مثال: أمر تلخيص الجلسة

```text
.claude/commands/session-summary.md
```

```md
Summarize the current work session:
- completed work
- files changed
- open risks
- tests run or not run
- next recommended step
Keep it short and practical.
```

## قواعد كتابة الأوامر الجيدة

الأمر الجيد يجب أن يكون:

1. محددًا.
2. قصيرًا.
3. قابلًا للتكرار.
4. يحتوي قيودًا واضحة.
5. يوضح هل يسمح بالتعديل أم لا.
6. يحدد شكل المخرجات.

## خطأ شائع

أمر سيء:

```md
Improve this project.
```

أمر أفضل:

```md
Review only the current diff. Do not edit. Return the top 5 issues sorted by risk.
```

## مكتبة أوامر مقترحة

| الأمر | الهدف |
|---|---|
| `/review` | مراجعة الفرق الحالي |
| `/test-plan` | خطة اختبار محددة |
| `/bug-hunt` | البحث عن سبب مشكلة |
| `/docs-update` | تحديث التوثيق |
| `/session-summary` | تلخيص الجلسة |
| `/commit-message` | اقتراح رسالة commit |
| `/risk-check` | فحص مخاطر التغيير |

## القرار

أي prompt تكرره أكثر من ثلاث مرات يجب أن يتحول إلى custom command.
