# COSMODERM CLINIC — Luxury Aesthetic Experience Platform
### منصة عيادات كوزموديرم للتجميل والجلدية والليزر — جدة، المملكة العربية السعودية

منصة رقمية فائقة الفخامة مبنية وفق أعلى معايير الويب الحديثة (Mobile-First Architecture) لعيادات **COSMODERM CLINIC** الواقعة في حي الروضة بمدينة جدة. تم تطوير المنصة لتعمل كموقع ويب واستعراض أعمال ونظام حجز كونسيرج متكامل باللغتين العربية والإنجليزية.

---

## 📁 هيكلية المشروع (Project Architecture)

```text
project/
├── index.html              # ملف الموقع الرئيسي المتكامل (HTML5, Tailwind CSS, JS)
├── README.md               # دليل التشغيل، الإدارة، والرفع على GitHub
├── .gitignore              # ملف استثناء الملفات المؤقتة وغير الضرورية
│
└── public/
    ├── images/
    │   ├── logo/           # الشعار الرسمي للعيادة (cosmoderm-logo.jpg)
    │   ├── doctors/        # صور الأطباء الاستشاريين (dr-kashmar, dr-samar, dr-khaled, dr-mohamed-dohak)
    │   ├── clinic/         # صور جولة وأجنحة العيادة (clinic-01.jpg .. clinic-08.jpg)
    │   ├── treatments/     # صور الأقسام والعلاجات (filler-botox.jpg)
    │   └── works/          # أغلفة فيديوهات بعض أعمالنا المستخرجة تلقائياً (work-01.jpg .. work-06.jpg)
    │
    └── videos/             # فيديوهات قسم "بعض أعمالنا" (work-01.mp4 .. work-06.mp4)
```

---

## 🚀 1. رفع المشروع على GitHub (Uploading to GitHub)

إذا كان لديك مستودع جديد على GitHub وترغب في رفع المشروع لأول مرة:

### الخطوة 1: فتح موجه الأوامر (Terminal / PowerShell)
توجه إلى مجلد المشروع:
```bash
cd "c:\Users\hp\Desktop\عياده"
```

### الخطوة 2: تهيئة Git وإضافة الملفات
```bash
# تهيئة المستودع المحلي
git init

# إضافة جميع ملفات المشروع
git add .

# تسجيل الـ Commit الأول
git commit -m "Initial commit: Production-ready Cosmoderm Clinic Luxury Platform"

# تعيين الفرع الرئيسي main
git branch -M main
```

### الخطوة 3: ربط المستودع بـ GitHub والرفع (Push)
استبدل الرابط أدناه برابط مستودعك على GitHub:
```bash
git remote add origin https://github.com/YOUR_USERNAME/cosmoderm-clinic.git
git push -u origin main
```

> **طريقة بديلة بدون سطر أوامر (GitHub Web / GitHub Desktop):**
> 1. افتح حسابك على [github.com](https://github.com/) وأنشئ مستودعاً جديداً (New Repository).
> 2. اضغط على زر **uploading an existing file**.
> 3. اسحب مجلد `public` وملف `index.html` وملف `README.md` وأفلتها داخل صفحة المستودع ثم اضغط **Commit changes**.
> 4. أو استخدم برنامج **GitHub Desktop** لفتح المجلد وعمل Commit و Push بنقرة واحدة.

---

## 🌐 2 & 3. تفعيل ونشر الموقع عبر GitHub Pages (Enabling GitHub Pages)

الموقع مصمم ليعمل كـ **موقع ثابت (Static Website)** دون الحاجة لأي خادم خلفي، وهو جاهز 100% للنشر المباشر والمجاني عبر **GitHub Pages**:

1. ادخل إلى مستودع المشروع على **GitHub**.
2. اضغط على تبويب **Settings** (الإعدادات) في أعلى المستودع.
3. من القائمة الجانبية اليسرى، اختر **Pages**.
4. تحت قسم **Build and deployment**:
   * **Source**: اختر `Deploy from a branch`.
   * **Branch**: اختر `main` واجعل المجلد `/(root)`.
5. اضغط على **Save**.
6. خلال دقيقة إلى دقيقتين، سيزودك GitHub برابط النشر المباشر:
   ```text
   https://YOUR_USERNAME.github.io/cosmoderm-clinic/
   ```
7. يمكنك في أي وقت ربط نطاق مخصص (Custom Domain) مثل `cosmoderm.sa` من نفس الصفحة.

---

## 🖼️ 4. إضافة وتحديث صور العيادة (Adding Clinic Images)

تم تجهيز نظام المعرض `clinicGalleryContainer` ليقرأ الصور تلقائياً وبأعلى دقة:

1. أضف صورك الجديدة داخل المجلد:
   `public/images/clinic/`
   (يُفضل تسميتها مثل: `clinic-01.jpg`, `clinic-02.jpg`, ... أو أي اسم تفضله).
2. افتح ملف `index.html` وتوجه للمصفوفة `CLINIC_PHOTOS` (حوالي السطر 2850):
   ```javascript
   const CLINIC_PHOTOS = [
     { id: 1, src: "public/images/clinic/clinic-01.jpg", alt: "COSMODERM Reception Lounge", featured: true },
     { id: 2, src: "public/images/clinic/clinic-02.jpg", alt: "COSMODERM Consultation Suite", featured: false },
     // أضف الصور الجديدة هنا
   ];
   ```
3. احفظ الملف وسيتم تحديث المعرض وتوزيع الصور المتجاوبة فوراً.

---

## 👨‍⚕️ 5. إضافة وتعديل بيانات الأطباء (Adding New Doctors)

تتم إدارة قائمة الأطباء من خلال مصفوفة موحدة تدعم ثنائية اللغة (عربي / إنجليزي):

1. ضع الصورة الشخصية للطبيب الجديد داخل:
   `public/images/doctors/dr-name.jpg`
2. افتح ملف `index.html` وتوجه للمصفوفة `DOCTORS` (حوالي السطر 2360):
   ```javascript
   {
     id: "dr-5",
     name: "Dr. Full Name",
     nameAr: "د. اسم الطبيب",
     titleEn: "Consultant Dermatologist & Aesthetic Specialist",
     titleAr: "استشاري الأمراض الجلدية وجراحة الجلد التجميلية",
     descEn: "Medical credentials, board certifications and areas of expertise.",
     descAr: "نبذة عن المؤهلات الطبية، البورد، وسنوات الخبرة والاهتمامات التجميلية.",
     image: "public/images/doctors/dr-name.jpg"
   }
   ```
3. سيقوم النظام تلقائياً بـ:
   * إنشاء بطاقة الطبيب في قسم الفريق الطبي.
   * إضافته كخيار في قائمة اختيار الطبيب داخل نظام الحجز.
   * توفير زر مباشر لحجز موعد معه.

---

## 🎬 6. إضافة فيديوهات جديدة لقسم "بعض أعمالنا" (Adding Videos)

القسم يدعم ملفات الفيديو العمودية (9:16) بتنسيق MP4 المحسّنة للجوال:

1. ضع ملف الفيديو داخل:
   `public/videos/work-07.mp4`
2. استخرج لقطة واضحة كغلاف (Cover/Poster) واحفظها داخل:
   `public/images/works/work-07.jpg`
3. افتح ملف `index.html` وأضف العنصر داخل مصفوفة `WORK_VIDEOS`:
   ```javascript
   {
     id: "v7",
     title: "عمل 07 — عنوان الجلسة أو النتيجة بالعربية",
     titleEn: "Work 07 — English Description",
     video: "public/videos/work-07.mp4",
     poster: "public/images/works/work-07.jpg",
     featured: false // أو true لتمييزها بعرض أكبر
   }
   ```
4. سيتم عرض الفيديو فوراً بوسم `<video preload="none">` الموفر للبيانات، مع تشغيل فوري في المشغل السينمائي المنبثق بدقة HD.

---

## 📱 مزايا معمارية الموقع (Key Architecture Features)

* **تصميم Mobile-First:** إحساس تطبيق حجز فاخر native على الهواتف، مع اتساع فخم على الأجهزة اللوحية والمكتبية.
* **ثنائية اللغة الكاملة (Bilingual RTL/LTR):** تبديل سلس وسريع بين العربية (خط Cairo) والإنجليزية (خط Inter / Cinzel).
* **مسارات نسبية 100%:** جميع الروابط ومسارات الوسائط نسبية لضمان عملها فوراً على أي خادم أو مسار فرعي لـ GitHub Pages.
* **تكامل التواصل المباشر:** أزرار واتساب ذكية تفتح محادثة فورية مع رقم العيادة الرسمي (`01104689702`) مع رسائل تأكيد الحجز المسبقة.
* **رابط خرائط جوجل الرسمي:** ربط مباشر بمقر العيادة في حي الروضة - جدة (`https://maps.app.goo.gl/bt3Evjnsuqog62eY7`).
* **حقوق التصميم والملكية:**
  * **© 2026 جميع الحقوق محفوظة لـ ABDO HOUSE.**
  * **UX/UI Developed & Designed by ABDO HOUSE**
