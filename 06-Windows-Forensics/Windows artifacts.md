- System artifacts

بيانات بينتجها نظام التشغيل زي

(Prefetch - AmCache - ShimCache - Event logs - Registry hives - USN journal - SMFT)

Important Windows Event IDs

4624
→ Successful Logon

4625
→ Failed Logon

4688
→ Process Creation

7045
→ New Service Installed

1102
→ Audit Logs Cleared

4720
→ User Account Created

4726
→ User Account Deleted

دي Event IDs مهمة جدًا في الـ DFIR والـ Threat Hunting لأنها بتساعدنا نعرف النشاط اللي حصل على الجهاز.

- User artifacts

بيانات مرتبطة بشكل مباشر بسلوك ونشاط المستخدم زي 

(NTuser - Download - documents - recycle bin)

Persistence Techniques

هي الطرق اللي بيستخدمها الـ Malware أو المهاجم علشان يفضل موجود على الجهاز حتى بعد الـ Restart.

أشهر طرق الـ Persistence:

- Run Keys
→ برامج بتشتغل تلقائي مع بداية الويندوز.
- Scheduled Tasks
→ مهام بتشتغل في وقت معين أو عند Event معين.
- Services
→ إنشاء Service تشتغل تلقائي مع النظام.
- Startup Folder
→ ملفات بتتحط في Startup وتشتغل أول ما اليوزر يعمل Login.
- WMI Persistence
→ تشغيل أوامر أو Malware تلقائي باستخدام WMI.

أهمية تحليل الـ Persistence:
بتساعدنا نعرف إزاي الـ Malware كان بيرجع يشتغل كل مرة.
