# GAMELOOP PRO OPTIMIZER

برنامج سطح مكتب لنظام Windows مبني بـ **Python 3.11 + PySide6** لتشخيص ومعالجة مشاكل **GameLoop / PUBG Mobile** (اللاج، هبوط الإطارات، التقطيع، التجميد، زمن الاستجابة، الأعطال، استهلاك الموارد، وأخطاء ADB) بطريقة آمنة وقابلة للتراجع بالكامل.

A diagnostic-driven, safety-first Windows desktop suite built with **Python 3.11 + PySide6** to diagnose and mitigate **GameLoop / PUBG Mobile** stability, stuttering, crash, resource, and ADB issues — with zero telemetry and full SHA-256 verified rollback.

## التحميل | Download

حمّل أحدث إصدار جاهز للتشغيل على Windows من قسم **Releases** في القائمة الجانبية للمستودع:
- `GAMELOOP PRO OPTIMIZER.exe` — الملف التنفيذي الجاهز.
- `GAMELOOP PRO OPTIMIZER.exe.sha256` — بصمة التحقق من سلامة الملف.

## مبادئ الأمان | Security & Honesty Principles

- **لا تضحية بأمان Windows:** لا يعطّل Windows Defender أو الجدار الناري أو Windows Update، ولا يغيّر إعدادات الإقلاع (`bcdedit`).
- **تعديلات قابلة للتراجع:** كل تعديل يمر بمعاينة وموافقة صريحة، مع نسخة احتياطية موثقة بـ SHA-256 وإمكانية التراجع الفوري أو الفردي.
- **لا قياسات وهمية:** أي مستشعر غير متاح (مثل الحرارة بدون LibreHardwareMonitor/OpenHardwareMonitor أو FPS بدون RTSS) يظهر بوضوح كـ **غير متاح (Unavailable)** دون أرقام مختلقة.
- **تنظيف آمن (Cleaner PRO):** معاينة إلزامية قبل التنفيذ، حظر كامل للمساس بملفات `.sav` و`.ini` و`.cfg` و`.pak` و`.obb`، ونقل الملفات المؤقتة إلى **سلة المحذوفات** فقط.
- **بلا تيليمتري أو تنزيلات صامتة:** جميع الأوامر تُنفّذ دون `shell=True` ودون أي تنزيلات خلفية.

## حالة الاختبار | Testing Status

- الاختبارات الآلية غير المرتبطة بالواجهة (`pytest -v -m "not gui"`) تغطي الوحدات الخلفية باستخدام Mocks معزولة (حالات غياب GameLoop، انقطاع ADB، التشغيل بدون Admin، التراجع الكامل، وحماية Cleaner PRO).
- يُنصح بتجربة الفحص اليدوي على جهاز Windows فعلي عند أول تشغيل للتحقق من قراءة WMI وRegistry وEvent Log و`adb.exe` و`RTSS` وتبديل اللغة (RTL / LTR).

## البناء التلقائي | Automated Build

يتم بناء ملف `GAMELOOP PRO OPTIMIZER.exe` تلقائياً على خادم `windows-latest` عبر **GitHub Actions** من الأرشيف `gameloop-pro-optimizer.zip`، ويشمل ذلك:
1. فك ضغط المشروع وتثبيت اعتماديات Python 3.11 من `requirements.txt`.
2. تشغيل الاختبارات الآلية (`pytest -v -m "not gui"`).
3. توليد أيقونة البرنامج (`scripts/generate_icon.py`).
4. بناء ملف `.exe` واحد عبر PyInstaller وحساب بصمة `SHA256`.
5. نشر الملفات تلقائياً في صفحة **Releases** (مع إمكانية تشغيل البناء يدوياً وتحديد رقم إصدار جديد من تبويب **Actions**).

## الرخصة | License

مرخّص بموجب رخصة [MIT](LICENSE).
