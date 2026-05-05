# Local AI مع Claude Code

دليل عملي لتشغيل نماذج محلية أو منخفضة التكلفة مع Claude Code — لتقليل التكلفة والتجريب السريع.

## الهدف

استخدام النماذج المحلية للمهام التكرارية الصغيرة، والاحتفاظ بـ Claude الأصلي للقرارات المعمارية ومراجعة الإنتاج.

## أسرع بداية

```bash
# 1. حمّل نموذج الكود
ollama pull qwen2.5-coder

# 2. اضبط متغيرات الاتصال
export ANTHROPIC_BASE_URL=http://localhost:11434
export ANTHROPIC_API_KEY=ollama

# 3. شغّل Claude Code مع النموذج
claude --model qwen2.5-coder
```

> قاعدة: لا تجرب أكثر من نموذجين في نفس اليوم. أثبت قيمة واحد أولاً.

## كيف تعمل المعمارية

Claude Code لا يشغّل النموذج مباشرة — يتصل بـ API endpoint. Ollama يوفر هذا الـ endpoint محلياً بعنوان `http://localhost:11434`.

## خيارات الـ Backend

| الخلفية | أفضل استخدام | الحكم |
|---------|-------------|-------|
| Ollama | أسرع تشغيل محلي | ابدأ هنا |
| LM Studio | واجهة رسومية واختبار النماذج | خيار ثانٍ |
| llama.cpp | GGUF وتحكم أداء متقدم | بعد إتقان الأساس |
| LiteLLM Router | توجيه متعدد المسارات | مرحلة متقدمة |

## الملفات

- [quick-start.md](quick-start.md): خطوات التشغيل في 15 دقيقة.
- [commands.md](commands.md): مرجع الأوامر الكامل.
- [tips-and-tricks.md](tips-and-tricks.md): نصائح ميدانية.
- [troubleshooting.md](troubleshooting.md): المشاكل الشائعة وحلولها.
- [download-strategy.md](download-strategy.md): استراتيجية اختيار النماذج.
- [operations-guide.md](operations-guide.md): الدليل التشغيلي التفصيلي.
- [slides.html](slides.html): الدليل التفاعلي في المتصفح.

## قرار 24 ساعة

سؤال واحد فقط:

> هل يقلل هذا الإعداد استهلاكي الفعلي من Claude في مهام الكود اليومية؟

إذا نعم — احتفظ به. إذا لا — توقف عن التجريب وانتقل.
