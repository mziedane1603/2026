تشغيل لوحة المبيعات على Firebase (مشروع report-ee942)

1) من Firebase Console:
   - Authentication > Sign-in method: فعّل Email/Password.
   - Authentication > Users: أضف مستخدمين (إيميل وباسورد) للإدارة.
   - Authentication > Settings > User actions: عطّل "Enable create (sign-up)" عشان محدش يسجّل نفسه.
   - Firestore Database: Create database (production mode).
2) على جهازك (يحتاج Node.js):
   npm install -g firebase-tools
   firebase login
   cd (فولدر المشروع هذا)
   firebase use report-ee942
   firebase deploy --only firestore:rules,hosting
3) افتح رابط الـ Hosting واضغط "🔐 أدمن" وسجّل الدخول، ثم اضغط "بيانات أولية" واختر الملفين من فولدر seed (seed-sales.json و seed-items.json). أي حد تاني بيفتح الرابط بيقرا العرض مباشرة من غير أي صفحة دخول. زرار الأدمن مخفي، وبيظهر بس لو فتحت الرابط وفي آخره #admin (مثال: https://موقعك.web.app/#admin).
4) بعد كده كل يوم: زرار "استيراد Excel" وارفع شيت العملاء، وملف نوفمبر (الكمية + البونص + الرصيد + آخر بيع + آخر شراء).

ملاحظة أمان: القراءة عامة، يعني أي حد معاه الرابط يشوف المبيعات والأصناف. الكتابة للأدمن فقط. لا تضع فولدر seed داخل public، وعطّل Enable create (sign-up) في Authentication.
