# أوامر Claude Code المهمة

## تشغيل أساسي

```bash
claude
```

تشغيل داخل مجلد مشروع:

```bash
cd my-project
claude
```

## أوامر داخل Claude Code

هذه أوامر شائعة يجب تجربتها داخل الجلسة:

```text
/help
/status
/permissions
/bug
```

## Prompt أوامر عملية

### فهم المشروع بدون تعديل

```text
Read the project only. Do not edit files. Summarize architecture, risks, and first safe improvement.
```

### خطة قبل التنفيذ

```text
Create an implementation plan. Do not edit files yet. Include files, risks, tests, and rollback plan.
```

### تعديل محدود

```text
Implement only step 1. Keep changes minimal. Show summary and test command after editing.
```

### مراجعة diff

```text
Review the current git diff. Identify bugs, risky changes, and missing tests. Do not edit.
```

### توليد tests

```text
Add one focused test for the changed behavior. Run or explain the exact test command.
```

## Custom Slash Commands

يمكنك إنشاء أوامر خاصة بالمشروع داخل:

```text
.claude/commands/
```

مثال:

```bash
mkdir -p .claude/commands
cat > .claude/commands/review.md <<'EOF'
Review the current git diff for bugs, security risks, missing tests, and unclear code. Do not edit files.
EOF
```

بعدها جرّب داخل Claude Code:

```text
/review
```

## ملف تعليمات المشروع

استخدم ملف تعليمات مختصر للمشروع مثل:

```text
CLAUDE.md
```

أو ملف عام للوكلاء:

```text
AGENTS.md
```

ضع فيه:

- طريقة تشغيل المشروع.
- أوامر الاختبار.
- قواعد الكود.
- ممنوعات واضحة.
- أسلوب كتابة commits.

## Commands يجب عدم استخدامها عشوائيًا

تجنب إعطاء موافقة عامة لأوامر مثل:

```bash
rm -rf
sudo
curl | bash
chmod -R 777
git push --force
```

استخدمها فقط بعد فهم كامل للسياق.
