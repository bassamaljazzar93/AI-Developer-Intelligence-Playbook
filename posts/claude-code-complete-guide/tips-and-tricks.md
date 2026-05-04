# Tricks, Tips & Field Notes

## 1. لا تبدأ بالتعديل

أول prompt يجب أن يكون قراءة وفهم فقط:

```text
اقرأ المشروع ولا تعدل. أخبرني أين توجد ملفات التشغيل والاختبار والمخاطر.
```

## 2. استخدم Plan → Execute → Verify

أفضل نمط:

```text
Plan first. Do not edit.
```

ثم:

```text
Execute step 1 only.
```

ثم:

```text
Run or explain the verification command.
```

## 3. اجعل المهمة صغيرة

بدل أن تقول:

```text
ابنِ النظام كاملًا.
```

قل:

```text
نفّذ endpoint واحد، مع test واحد، ولا تغير ملفات غير ضرورية.
```

## 4. اطلب منه قراءة diff قبل الاستمرار

```text
Before continuing, review the current git diff and identify anything risky.
```

## 5. استخدم ملفات ذاكرة خفيفة

في `CLAUDE.md` أو `AGENTS.md` ضع أشياء قصيرة:

- كيف نشغل المشروع.
- كيف نختبر.
- قواعد naming.
- ممنوعات.
- أسلوب PR.

لا تضع مقالة طويلة بلا تنظيم.

## 6. امنعه من اختراع النجاح

استخدم هذه الجملة:

```text
Do not claim success unless you ran the command or clearly say it was not run.
```

## 7. لا تفتح الصلاحيات بالكامل

استخدم approve تدريجيًا. أعطه أوامر آمنة مثل:

- read/list/search
- test
- lint
- build

وتجنب الموافقات العامة لأوامر الحذف أو الدفع الإجباري.

## 8. اجعله يكتب خطة rollback

للمهام الحساسة:

```text
Before editing, include a rollback plan.
```

## 9. استخدمه كمراجع ثاني

بعد الانتهاء:

```text
Act as a strict reviewer. Review only the changed files. Find what could break.
```

## 10. نصيحة من نقاشات المجتمع

من GitHub وReddit يتكرر أن أفضل مستخدمي Claude Code لا يعطونه مهمة كبيرة مرة واحدة. هم يقسمون العمل إلى مراحل، ويستخدمون tests، ويجعلون الأداة تقرأ أكثر مما تعدّل.

## 11. لا تعتمد على ذاكرته وحدها

في الجلسات الطويلة، اطلب منه تلخيص الحالة:

```text
Summarize current state, completed work, remaining work, and exact next command.
```

## 12. استخدم أوامر مخصصة للمهام المتكررة

أمثلة:

- `/review`
- `/test-plan`
- `/bug-hunt`
- `/docs-update`
- `/commit-message`

هذه تقلل تكرار الكتابة وتوحّد أسلوب العمل.
