# وصّلها BM — صفحة تحميل التطبيق

صفحة تحميل Static بسيطة لتطبيق **وصّلها BM**، مبنية بـ HTML + CSS + Vanilla JavaScript وتعمل على GitHub Pages.

## الملفات

- `index.html` — الموقع بالكامل.
- `assets/logo.png` — لوجو التطبيق.
- `downloads/waselha-bm.apk` — ملف APK المرفق حاليًا.

## تشغيلها مباشرة

افتح `index.html` محليًا أو ارفع المشروع إلى GitHub Pages.

زر التحميل في الوضع الافتراضي يستخدم:

`downloads/waselha-bm.apk`

## استخدام GitHub Release للحصول على عداد تحميلات حقيقي

للحصول على `download_count` الحقيقي من GitHub:

1. أنشئ Repository على GitHub.
2. ارفع `index.html` و`assets/logo.png`.
3. يفضل عدم الاعتماد على رفع APK داخل ملفات Pages نفسها.
4. أنشئ Release جديد، مثل:
   `v1.0.0`
5. ارفع ملف APK كـ Release Asset، وسمّه بالضبط:
   `waselha-bm.apk`
6. افتح `index.html`.
7. داخل `CONFIG` غيّر:

```js
useGitHubRelease: true,
githubOwner: "اسم حسابك",
githubRepo: "اسم المستودع",
releaseTag: "v1.0.0",
apkFileName: "waselha-bm.apk"
```

بعد ذلك سيستخدم الموقع GitHub Releases API للحصول على:
- رابط التحميل المباشر `browser_download_url`
- عدد تحميلات الـAPK `download_count`

## عداد المشاهدات

GitHub Pages Static لا يوفر عداد مشاهدات إجماليًا من تلقاء نفسه. لذلك الموقع لا يضع رقمًا وهميًا ولا يستخدم `localStorage` كإجمالي للمشاهدات، ويعرض `--` حاليًا.

إذا أردت لاحقًا عداد مشاهدات حقيقي، ستحتاج خدمة Analytics/Counter خارجية أو Backend.

## تفعيل GitHub Pages

من Repository:

`Settings → Pages → Deploy from a branch`

اختر:

`main` → `/ (root)` → Save

بعدها سيظهر رابط الموقع في إعدادات Pages.

## تحديث التطبيق

عند إصدار نسخة جديدة:

1. أنشئ Release جديد، مثل `v1.0.1`.
2. ارفع APK الجديد باسم `waselha-bm.apk`.
3. غيّر `releaseTag` في `CONFIG` إلى `v1.0.1`.

يمكن لاحقًا تعديل الكود لاستخدام أحدث Release تلقائيًا بدل تحديد Tag.
