### إيه هو الـ Windows Registry؟

الـ **Registry** عبارة عن مجموعة قواعد بيانات (ملفات) في ويندوز بتخزن إعدادات النظام، الأجهزة، البرامج، وحاجات تخص كل مستخدم.

ببساطة: كل حاجة ممكن تتغيّر في النظام غالبًا ليها أثر في الريجستري

ويندوز بيخزنها في أماكن مختلفة، منها:

- **Windows Registry** (سجل النظام)
- **مجلد المستخدم (User Profile Directory)**
- **ملفات خاصة بالتطبيقات (Application Files)**
- مكون من key & value
- Key = الفولدرات
- Values = البيانات اللي بتبقى حوه الفولدرات دي

    كل مجموعة من دول بتتحط في ملف واحد اسمه hive 

    

الـ 5 Root Keys اللي بتشوفهم في `regedit`:

- `HKEY_CURRENT_USER` — إعدادات المستخدم اللي فاتح الجلسة.
- `HKEY_USERS` — كل مستخدمين النظام (الـ HKCU هو عرض للمفتاح الخاص بالمستخدم الحالي من HKU).
- `HKEY_LOCAL_MACHINE` — إعدادات الجهاز عامة (hardware، software اللي مش خاص بمستخدم).
- `HKEY_CLASSES_ROOT` — معلومات الربط بين الامتدادات والـ COM classes.
- `HKEY_CURRENT_CONFIG` — إعدادات الهاردوير الحالية (اختصارات لإعدادات بعينها)

     

      

### فين ملفات الـ Hive على القرص؟ (مهمة للـ Forensics)

أهم مواقع الملفات:

- `C:\Windows\System32\config\SYSTEM`
- `C:\Windows\System32\config\SOFTWARE`
- `C:\Windows\System32\config\SAM`
- `C:\Windows\System32\config\SECURITY`
- `C:\Users\<username>\NTUSER.DAT` (ده اللي بيملأ HKCU لكل مستخدم)
- `C:\Users\<username>\ntuser.dat.LOG*` (ملفات اللوج)

لو هتعمل تحليل offline (يعني تحلل صورة قرص أو تحلل من غير تشغيل الويندوز)، هتتعامل مع الملفات دي مباشرة.

### أمثلة على مفاتيح/قيم مفيدة في التحقيق الجنائي

- **Run / RunOnce** (`HKLM\...\Run`, `HKCU\...\Run`) — برامج بتشتغل عند بدء التشغيل (ممكن تكشف برمجيات خبيثة أو أدوات تم تثبيتها).
- **UserAssist** (`HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\UserAssist`) — بيسجل البرامج اللي اتفتحت (مشفرة شوية لكن مفيدة جداً).
- **RecentDocs / MRU lists** — القوائم بتاعة الملفات اللي فاتت (بتديك فكرة عن الملفات المفتوحة مؤخرًا).
- **ShellBags** — تفاصيل عن المجلدات اللي اتفتحت في الـ Explorer (مهمة جدًا في تتبع وجود ملفات/مجلدات وحتى ترتيبهم).
- **USB Devices** (`HKLM\SYSTEM\CurrentControlSet\Enum\USBSTOR`) — أجهزة USB اللي اتوصلت للجهاز (اسم الجهاز، توقيت أول وآخر اتصال أحيانًا).
- **MountedDevices** (`HKLM\SYSTEM\MountedDevices`) — معلومات عن الأقراص والفلاشات اللي اتربطت بالنظام.
- **MRU & Browser History** (بعضها في الريجستري لبعض المتصفحات أو في ملفات التطبيق).
- **NTUSER.DAT** — فيه إعدادات ورصد لنشاط كل مستخدم (زي MRU، UserAssist، RecentDocs...).
