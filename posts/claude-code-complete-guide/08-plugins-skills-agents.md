# 08 — Plugins, Skills, Agents

## ما الفكرة؟

Claude Code لا يقتصر على جلسة واحدة داخل التيرمنال. يمكن توسيعه عبر plugins وskills وagents وcommands. الهدف هو تحويل المعرفة المتكررة إلى مكونات قابلة لإعادة الاستخدام.

## الفرق بينهم

| العنصر | الفكرة | أفضل استخدام |
|---|---|---|
| Command | prompt محفوظ باسم قصير | مهام متكررة مثل review أو test plan |
| Skill | معرفة أو طريقة تنفيذ متخصصة | PDF، Excel، frontend design، security review |
| Agent | دور متخصص | code reviewer، architect، test writer |
| Plugin | حزمة تجمع commands وagents وskills وhooks | workflow كامل للفريق |

## متى تستخدم Command؟

استخدم command عندما تحتاج نفس الطلب كثيرًا.

مثال:

- review diff.
- write tests.
- summarize session.
- update docs.

## متى تستخدم Skill؟

استخدم skill عندما تكون المهمة تحتاج طريقة ثابتة أو خبرة متخصصة.

أمثلة:

- بناء HTML tutorial pages.
- مراجعة security patterns.
- تجهيز docs.
- بناء slides أو guides.

## متى تستخدم Agent؟

استخدم agent عندما تريد منظورًا متخصصًا.

أمثلة:

- Security reviewer.
- Frontend designer.
- API architect.
- Database reviewer.
- Test strategist.

## متى تستخدم Plugin؟

استخدم plugin عندما يكون لديك workflow متكامل تريد نقله بين مشاريع أو مشاركته مع فريق.

مثال plugin جيد:

- command لمراجعة الكود.
- agent متخصص للمراجعة.
- skill يشرح قواعد المشروع.
- hook يذكّر بالتحقق.

## ما الذي تعلمناه من المستودعات الرسمية والمجتمع؟

المستودع الرسمي لـ Claude Code يحتوي أمثلة plugins تشمل:

- code review.
- git workflow commands.
- feature development workflow.
- frontend design skill.
- security guidance.
- plugin development tools.

ومجتمع Claude Code بنى مكتبات templates تحتوي:

- agents.
- commands.
- MCP configs.
- settings.
- hooks.
- skills.

## كيف تبدأ بدون تعقيد؟

لا تبدأ ببناء plugin. ابدأ بهذا الترتيب:

1. Prompt متكرر.
2. حوّله إلى command.
3. إذا صار command يحتاج معرفة طويلة، حوّله إلى skill.
4. إذا صار لديك عدة commands وskills مرتبطة، اجمعها في plugin.

## مثال عملي

لديك workflow لمراجعة PR:

1. اقرأ diff.
2. افحص bugs.
3. افحص tests.
4. افحص naming.
5. اكتب ملخصًا.

ابدأ بـ `/review` command. بعد فترة، أضف agent اسمه `strict-code-reviewer`. لاحقًا اجعلهم plugin للفريق.

## أخطاء شائعة

### 1. البدء من plugin مباشرة

هذا يجعل النظام معقدًا قبل أن تعرف ما تحتاجه.

### 2. كثرة agents

كل agent يجب أن يحل دورًا واضحًا. لا تضف agent فقط لأن الاسم جميل.

### 3. Skill طويل بلا structure

Skill الجيد يجب أن يكون واضحًا ومقسّمًا، وليس مقالة طويلة.

## القرار

ابدأ صغيرًا: command واحد يحل مشكلة حقيقية. ثم وسّع إلى skill أو plugin بعد أن يتكرر الاستخدام وتثبت الفائدة.
