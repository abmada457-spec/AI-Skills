# AI-Skills

مستودع مركزي لمهارات قابلة لإعادة الاستخدام في ChatGPT Work.

## UI UX Pro Max

تجمع المهارة توصيات للهوية البصرية وتخطيط الصفحات والألوان والخطوط وإمكانية الوصول. يعمل محرك البحث محليًا بمكتبة Python 3 القياسية. يحتوي [مجلد المهارة](ui-ux-pro-max/) على تعليماتها ومراجعها وبرامجها وقواعد بياناتها. راجع [المصدر والإصدار](ui-ux-pro-max/UPSTREAM.md) و[الترخيص](ui-ux-pro-max/LICENSE).

### الاستخدام في مشروع جديد

انسخ [نص الطلب الجاهز](USAGE-PROMPT.md) إلى ChatGPT Work مع وصف المشروع. إذا توفر Git وPython في بيئة العمل، يمكن تشغيل هذه الأوامر من جذر المشروع.

```bash
project_root="$PWD"
skills_tmp="$(mktemp -d)"
git clone --depth 1 https://github.com/abmada457-spec/AI-Skills.git "$skills_tmp/AI-Skills"
export UI_UX_PRO_MAX_DIR="$skills_tmp/AI-Skills/ui-ux-pro-max"
export PYTHONDONTWRITEBYTECODE=1
cat "$UI_UX_PRO_MAX_DIR/SKILL.md"

python3 "$UI_UX_PRO_MAX_DIR/scripts/search.py" \
  "beauty spa wellness service" --design-system -p "Serenity Spa"

python3 "$UI_UX_PRO_MAX_DIR/scripts/search.py" \
  "beauty spa wellness service" --design-system --persist \
  -p "Serenity Spa" --page booking --output-dir "$project_root"
```

استبدل وصف البحث واسم المشروع وصفحته. أمر الحفظ يولّد `design-system/serenity-spa/MASTER.md` و`design-system/serenity-spa/pages/booking.md`. أبقِ نسخة المهارة في المسار المؤقت وأضف إلى مستودع المشروع الكود وملفات التصميم الخاصة به فقط. اقرأ نظام التصميم الحالي قبل توليد تحديث له.

إذا تعذّر الاستنساخ، استخدم تنزيل ZIP من GitHub أو اجلب ملفات المهارة عبر أدوات GitHub المتاحة إلى مجلد مؤقت بنفس بنيتها. إذا غابت بيئة Python، اذكر أن تشغيل المحرك غير متاح في تلك الجلسة.

### اختبار التشغيل

نجح توليد نظام تصميم لمشروع **Serenity Spa** على Python 3.12.14. اقترح المحرك **Soft UI Evolution** وخطّي **Lora** و**Raleway** واللون الأساسي `#EC4899`. أنشأ `--persist` الملف الرئيسي وملف صفحة الحجز. أعاد البحث في `ux` والبحث في `nextjs` ثلاث نتائج لكل منهما.
