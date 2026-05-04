# الدليل الكامل لاستخدام Claude Code

دليل عملي لاستخدام Claude Code كأداة تطوير يومية ومنظمة، وليس مجرد محادثة ذكية.

## ماذا ستتعلم؟

- كيف تبدأ بسرعة.
- كيف تنظّم مشروعك حتى يفهمه Claude Code.
- كيف تستخدم plan mode بدل التنفيذ العشوائي.
- كيف تبني workflow آمن وفعال.
- كيف تستخدم commands وskills وplugins وMCP.
- كيف تستفيد من نصائح المجتمع في GitHub وReddit.
- كيف تعالج أشهر المشاكل.

## الملفات

| الملف | الوصف |
|---|---|
| `quick-start.md` | بداية سريعة خلال 30 دقيقة |
| `commands.md` | أوامر الاستخدام الأساسية |
| `tips-and-tricks.md` | التركات والنصائح العملية |
| `troubleshooting.md` | أشهر المشاكل والحلول |
| `research-notes.md` | ملخص البحث والمصادر |
| `slides.html` | صفحة تعليمية تفاعلية |

## القاعدة الذهبية

أهم شيء في Claude Code هو أن تعطيه طريقة ليتحقق من عمله:

- tests
- lint
- build
- preview
- screenshots
- logs
- type check
- PR review

بدون verification، قد يعطيك نتيجة مرتبة لكنها غير صحيحة.

## أفضل استخدام يومي

1. ابدأ من مشروع فيه git.
2. اطلب plan قبل أي تعديل كبير.
3. نفّذ خطوة واحدة كل مرة.
4. راجع diff.
5. شغّل الاختبارات.
6. اجعل Claude يصلح أخطاءه.
7. احفظ الدروس في ملفات ذاكرة خفيفة.

## المصادر الأساسية

- Official repo: https://github.com/anthropics/claude-code
- Official docs: https://code.claude.com/docs/en/overview
- Settings docs: https://code.claude.com/docs/en/settings
- Permissions docs: https://code.claude.com/docs/en/permissions
- Hooks docs: https://code.claude.com/docs/en/hooks
- MCP docs: https://docs.claude.com/en/docs/claude-code/mcp
- Community templates: https://github.com/davila7/claude-code-templates

## القرار التنفيذي

ابدأ بـ Claude Code في مهام صغيرة قابلة للاختبار. لا تعطه feature كامل من أول مرة. اجعله يخطط، ينفذ خطوة، يختبر، ثم يكمل.
