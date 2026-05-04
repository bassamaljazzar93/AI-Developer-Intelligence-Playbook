# Claude Code Quick Start

## 30 دقيقة للبدء

### 1. ثبّت Claude Code

راجع دائمًا صفحة setup الرسمية لأن طرق التثبيت تتغير. المستودع الرسمي يذكر أن npm installation أصبح deprecated، والطرق الموصى بها الآن هي install script أو Homebrew أو WinGet.

Mac/Linux:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Windows PowerShell:

```powershell
irm https://claude.ai/install.ps1 | iex
```

أو WinGet:

```powershell
winget install Anthropic.ClaudeCode
```

### 2. افتح مشروعك

```bash
cd path/to/project
claude
```

### 3. اطلب فهم المشروع فقط

استخدم prompt بسيط:

```text
اقرأ المشروع فقط. لا تعدل أي ملف. أعطني ملخصًا من 7 نقاط عن البنية، ثم اقترح أول 3 تحسينات قابلة للاختبار.
```

### 4. اطلب خطة قبل التنفيذ

```text
ضع خطة تنفيذ من 5 خطوات. لا تنفذ الآن. لكل خطوة اذكر الملفات المحتملة والاختبار المطلوب.
```

### 5. نفّذ خطوة واحدة

```text
نفّذ الخطوة الأولى فقط. بعد التنفيذ اعرض diff مختصر وأخبرني كيف أختبرها.
```

## أول اختبار حقيقي

اختر مهمة صغيرة:

- إصلاح bug بسيط.
- كتابة test واحد.
- تحسين README.
- إضافة validation بسيط.
- refactor دالة واحدة.

لا تبدأ بمهمة كبيرة مثل:

- إعادة بناء architecture.
- تحويل framework.
- تعديل 20 ملف.
- security redesign.

## نتيجة مقبولة بعد أول ساعة

Claude Code يجب أن يكون قادرًا على:

- فهم هيكل المشروع.
- عدم تعديل الملفات إذا طلبت منه ذلك.
- اقتراح خطة واقعية.
- تنفيذ تعديل صغير.
- تشغيل أو اقتراح اختبار واضح.

إذا فشل في هذه الأشياء، لا تعطه مهمة أكبر قبل ضبط التعليمات والـ context.
