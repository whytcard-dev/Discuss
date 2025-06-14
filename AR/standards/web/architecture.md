# معايير هندسة الويب

## المبادئ الأساسية

- هندسة معيارية وقابلة للتطوير
- فصل واضح للمهام
- مبادئ SOLID وDRY
- بنية مجلدات متسقة
- هندسة موثقة مع مخططات
- تصميم قائم على المكونات

## البنى الموصى بها

### هندسة الواجهة الأمامية

- **هندسة المكونات**
- منهجية التصميم الذري
- المكونات الذكية مقابل المكونات العرضية
- التركيب بدلاً من التوريث
- مكتبات المكونات وأنظمة التصميم

- **إدارة الحالة**
- حالة مركزية للبيانات على مستوى التطبيق
- حالة محلية للبيانات الخاصة بالمكون
- حالة الخادم لبيانات واجهة برمجة التطبيقات
- واجهة برمجة تطبيقات السياق للموضوع/المصادقة/التوطين

- **تدفق البيانات**
- تدفق بيانات أحادي الاتجاه
- تحديثات حالة ثابتة
- اتصال قائم على الأحداث
- أنماط النشر/الاشتراك للاتصال بين المكونات

### التطبيق البنية

- **العرض من جانب العميل (CSR)**
- للتطبيقات عالية التفاعل
- نموذج تطبيق الصفحة الواحدة (SPA)
- التوجيه من جانب العميل

- **العرض من جانب الخادم (SSR)**
- للتطبيقات المهمة لتحسين محركات البحث (SEO)
- أداء تحميل أولي مُحسّن
- إمكانية وصول وSEO أفضل

- **إنشاء مواقع ثابتة (SSG)**
- لمواقع الويب التي تُركز على المحتوى
- HTML مُقدّم مسبقًا
- متطلبات JavaScript بسيطة

- **التجديد الثابت التدريجي (ISR)**
- للمحتوى الديناميكي مع مزايا ثابتة
- التجديد في الخلفية
- نمط "البقاء قديمًا أثناء إعادة التحقق"

- **بنية الجزر**
- للمواقع الثابتة في الغالب مع مكونات تفاعلية
- ترطيب مكونات مُحددة
- تقليل حمولة JavaScript

## بنية المشروع

```

src/
├── المكونات/ # مكونات واجهة المستخدم القابلة لإعادة الاستخدام
│ ├── الذرات/ # وحدات البناء الأساسية
│ ├── الجزيئات/ # مجموعات الذرات
│ ├── الكائنات الحية/ # مجموعات الجزيئات
│ └── القوالب/ # تخطيطات الصفحات
├── الخطافات/ # خطافات React مخصصة
├── المكتبة/ # دوال ومكتبات الأدوات المساعدة
├── الصفحات/ # مكونات المسار (Next.js)
├── الميزات/ # كود خاص بالميزات
├── الخدمات/ # واجهة برمجة التطبيقات والخدمات الخارجية
├── المتجر/ # إدارة الحالة
├── الأنماط/ # الأنماط العامة و السمات
└── الأنواع/ # تعريفات أنواع TypeScript
```

## أفضل الممارسات

- تجميع الملفات حسب الميزة/الوحدة
- الحفاظ على حدود واضحة بين الوحدات
- الاحتفاظ بملفات التكوين في الجذر
- تطبيق إدارة حالة مُحسّنة
- تقليل التبعيات بين الوحدات
- اتباع مبدأ أقل امتيازات
- استخدام التحميل المتأخر لتقسيم الكود
- تطبيق حدود أخطاء مناسبة

## الأطر الموصى بها

- **Next.js** - لتطبيقات SSR وSSG وISR
- **React** - لواجهات المستخدم القائمة على المكونات
- **Vue.js** - بديل لـ React مع منحنى تعلم أبسط
- **Astro** - لمواقع الويب التي تركز على المحتوى مع الحد الأدنى من JavaScript
- **Remix** - لتطبيقات الويب المتكاملة
- **SvelteKit** - للتطبيقات عالية الأداء