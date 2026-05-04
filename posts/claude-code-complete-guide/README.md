# الدليل الكامل لاستخدام Claude Code

هذا ليس ملخصًا سريعًا. هذا دليل عملي مقسّم لفصول لتعلّم Claude Code واستخدامه كجزء من workflow تطوير حقيقي.

الهدف: أن تعرف **متى تستخدم Claude Code، كيف تضبطه، كيف تقلل أخطاءه، كيف تراقب استهلاكه، وكيف تبني معه طريقة عمل قابلة للتكرار**.

## طريقة قراءة الدليل

ابدأ بالترتيب إذا كنت جديدًا على Claude Code. أما إذا كنت تستخدمه بالفعل، افتح الفصول حسب المشكلة التي تواجهك.

## فهرس الفصول

| رقم | الفصل | الهدف |
|---|---|---|
| 00 | [خريطة الدليل](00-guide-map.md) | كيف تتنقل بين الفصول وما الذي تقرأه أولًا |
| 01 | [الفهم العام والتثبيت](01-concepts-and-setup.md) | ما هو Claude Code، الفرق بينه وبين Claude Desktop/API، وكيف تبدأ |
| 02 | [إعداد المشروع والذاكرة](02-project-memory-and-instructions.md) | كيف تجعل Claude يفهم مشروعك عبر CLAUDE.md وAGENTS.md |
| 03 | [سير العمل الاحترافي](03-professional-workflows.md) | Read → Plan → Execute → Verify → Review |
| 04 | [الأوامر المخصصة](04-custom-commands.md) | إنشاء slash commands متكررة للمراجعة والاختبار والتوثيق |
| 05 | [الصلاحيات والأمان التشغيلي](05-permissions-and-safety.md) | كيف تعطي صلاحيات مفيدة بدون فتح الباب لأخطاء كبيرة |
| 06 | [Hooks والأتمتة](06-hooks-and-automation.md) | استخدام hooks للتذكير، الفحص، ومنع السلوكيات الخاطئة |
| 07 | [MCP والربط مع الأدوات](07-mcp-integrations.md) | ربط GitHub، ملفات، قواعد بيانات، browser، وذاكرة خارجية |
| 08 | [Plugins, Skills, Agents](08-plugins-skills-agents.md) | كيف تفكر في الإضافات والمهارات والوكلاء المتخصصين |
| 09 | [تقليل الاستهلاك والتكلفة](09-usage-and-cost-control.md) | تقليل session waste، context waste، والمهام الواسعة |
| 10 | [المشاكل والحلول](10-troubleshooting-field-guide.md) | مشاكل شائعة من GitHub/Reddit وتجارب المستخدمين |
| 11 | [مكتبة Prompts جاهزة](11-prompt-library.md) | Prompts عملية للقراءة، التخطيط، التنفيذ، الاختبار، والمراجعة |
| 12 | [خطة اختبار 24 ساعة](12-24-hour-test-plan.md) | كيف تقرر بسرعة هل Claude Code مفيد لمشروعك أم لا |

## ملفات مختصرة مساعدة

هذه الملفات تبقى موجودة كاختصارات سريعة:

- [Quick Start](quick-start.md)
- [Commands](commands.md)
- [Tips & Tricks](tips-and-tricks.md)
- [Troubleshooting](troubleshooting.md)
- [Research Notes](research-notes.md)

## الصفحة التفاعلية

- [افتح صفحة الدليل التفاعلية](slides.html)

## الفكرة الأساسية

Claude Code ليس مجرد Chat داخل Terminal. قوته تظهر عندما تعامله كالتالي:

1. يفهم المشروع أولًا.
2. يخطط قبل التعديل.
3. ينفذ خطوة صغيرة.
4. يتحقق بالاختبارات أو البناء أو المراجعة.
5. يتعلم من الأخطاء عبر تحديث تعليمات المشروع.

## القاعدة الذهبية

لا تطلب من Claude Code “اعمل كل شيء”. اطلب منه:

```text
Read first. Plan. Execute one small step. Verify. Then continue.
```

## المصادر الأساسية

- Official Claude Code repository: https://github.com/anthropics/claude-code
- Official documentation: https://code.claude.com/docs/en/overview
- Official plugins: https://github.com/anthropics/claude-code/tree/main/plugins
- Community templates: https://github.com/davila7/claude-code-templates
- Docs mirror: https://github.com/mnestorov/cc-docs-mirror

## القرار التنفيذي

استخدم Claude Code كـ **مساعد تطوير منظم**، وليس كزر سحري. إذا لم يكن عندك طريقة تحقق، فالناتج سيبقى غير مضمون مهما كان الكلام مقنعًا.
