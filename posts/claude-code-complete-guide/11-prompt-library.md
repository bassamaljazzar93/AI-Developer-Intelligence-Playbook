# 11 — مكتبة Prompts جاهزة

استخدم هذه المكتبة كنقطة بداية. عدّل النص حسب مشروعك.

## قراءة المشروع لأول مرة

```text
Read this project only. Do not edit files. Summarize:
1. project purpose
2. main folders
3. run command if visible
4. test command if visible
5. important risks
6. first safe improvement
```

## خطة قبل التنفيذ

```text
Create a step-by-step plan. Do not edit files yet. For each step, include:
- files likely affected
- risk level
- verification method
- stopping point for review
```

## تنفيذ خطوة واحدة

```text
Implement only step 1 from the plan. Keep changes minimal. Do not touch unrelated files. After finishing, summarize changed files and verification status.
```

## مراجعة الفرق الحالي

```text
Review the current diff as a strict reviewer. Do not edit. Focus on:
- bugs
- missing tests
- risky assumptions
- unclear naming
- unnecessary complexity
Return findings sorted by severity.
```

## إصلاح Bug

```text
We need to fix a bug. First, do not edit. Read only the relevant files, explain the likely root cause, and propose the smallest safe fix with a verification plan.
```

## كتابة اختبار

```text
Add one focused test for the changed behavior. Keep it minimal. Explain what the test proves and how to run it.
```

## تحديث التوثيق

```text
Read the implementation first. Update documentation only to match actual behavior. Do not invent features. Summarize what changed.
```

## تلخيص جلسة

```text
Create a handoff summary:
- goal
- completed work
- files changed
- tests run
- risks
- exact next step
```

## فحص مخاطر قبل التعديل

```text
Before editing, list the files you expect to touch and why. Also list what you will not touch.
```

## منع التوسع

```text
Stay within the requested scope. If you discover a bigger issue, mention it separately but do not fix it now.
```

## عندما يكرر خطأ

```text
You repeated a mistake. Identify why it happened, fix the immediate issue, and suggest one small update to the project instructions to prevent it next time.
```

## عندما تريد نتيجة مختصرة

```text
Keep the response short. Give me only: decision, changed files, test status, and next action.
```

## عندما تريد تعلّم

```text
Explain what you are doing as if teaching a developer. Keep the code changes minimal and include why each change is needed.
```

## Prompt ذهبي يومي

```text
Read the relevant context first. Plan briefly. Make one minimal change. Verify if possible. Then summarize the diff and next action.
```
