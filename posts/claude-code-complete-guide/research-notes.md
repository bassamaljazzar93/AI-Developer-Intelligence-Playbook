# Research Notes — Claude Code

## ما تم فحصه

تم بناء هذا الدليل من مصادر متعددة:

1. المستودع الرسمي لـ Claude Code.
2. صفحة plugins الرسمية داخل المستودع.
3. وثائق Claude Code الرسمية.
4. GitHub Issues في المستودع الرسمي ومستودعات المجتمع.
5. مشاريع المجتمع مثل templates وUI wrappers.
6. Reddit discussions حول الاستخدام العملي والنصائح والمشاكل.

## مصادر رسمية مهمة

### Official repository

الرابط:

```text
https://github.com/anthropics/claude-code
```

ملاحظات:

- Claude Code أداة agentic coding تعمل من التيرمنال.
- تدعم العمل من التيرمنال والـ IDE وGitHub.
- طرق التثبيت الرسمية تغيرت، وnpm installation مذكور كخيار deprecated في README الرسمي.

### Official docs

```text
https://code.claude.com/docs/en/overview
https://code.claude.com/docs/en/setup
https://code.claude.com/docs/en/settings
https://code.claude.com/docs/en/permissions
https://code.claude.com/docs/en/hooks
```

### MCP docs

```text
https://docs.claude.com/en/docs/claude-code/mcp
```

### Official plugins

```text
https://github.com/anthropics/claude-code/tree/main/plugins
```

المستودع الرسمي يوضح أن plugins قد تحتوي على:

- custom slash commands
- specialized agents
- hooks
- MCP servers
- skills

## مصادر مجتمع مفيدة

### Claude Code Templates

```text
https://github.com/davila7/claude-code-templates
```

ملاحظات:

- يقدم agents وcommands وMCPs وsettings وhooks وskills.
- مفيد كفكرة لتنظيم مكتبة جاهزة للأوامر والمهام.
- ليس بديلًا عن فهم إعدادات مشروعك.

### Docs Mirror

```text
https://github.com/mnestorov/cc-docs-mirror
```

ملاحظات:

- مشروع مجتمع لعمل mirror لوثائق Claude Code.
- مفيد للوصول السريع والبحث المحلي.
- يجب الرجوع للمصدر الرسمي عند القرارات الحساسة.

### Claude Code UI / CloudCLI style projects

هذه المشاريع تعطي واجهة رسومية، لكن issues تظهر أن بعض المستخدمين واجهوا مشاكل مثل:

- session duplication.
- login state.
- Docker volume reset.
- terminal compatibility.
- CLI auth vs SDK/API auth.

الخلاصة: ممتازة للتجربة، لكن للمهام المهمة ابدأ بالـ CLI الرسمي.

## أنماط متكررة من GitHub Issues

1. استهلاك الاستخدام بسرعة في جلسات طويلة أو agentic tasks.
2. مشاكل permissions بين إعدادات المستخدم وإعدادات المشروع.
3. custom slash commands قد تتصرف بشكل مختلف حسب النظام والبيئة.
4. Windows/WSL يحتاجان عناية في المسارات والبيئة.
5. UI wrappers قد تضيف طبقة مشاكل فوق Claude Code نفسه.
6. بعض المستخدمين يفضلون ملفات project instructions واضحة لتقليل التخبط.

## أنماط متكررة من Reddit والمجتمع

1. أفضل النتائج تأتي من تقسيم المهام.
2. plan mode قبل التنفيذ يقلل التخريب.
3. tests أهم من جودة الكلام.
4. custom commands مفيدة جدًا للمهام المتكررة.
5. لا تجعل Claude Code يعمل على مشروع كبير بلا تعليمات.
6. راقب الاستهلاك في الجلسات الطويلة.
7. اجعل Claude يراجع diff قبل commit.

## الاستنتاج

Claude Code قوي جدًا عندما يكون المشروع منظمًا وفيه tests وتعليمات واضحة. يصبح أقل فائدة عندما تعطيه مهمة ضخمة بدون خطة أو verification.

أفضل طريقة لاستخدامه:

```text
Read → Plan → Execute small step → Verify → Review diff → Continue
```
