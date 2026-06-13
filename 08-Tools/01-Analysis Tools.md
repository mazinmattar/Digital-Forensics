# Eric zimmerman tools

أدواته تُستخدم في تحليل:

- **ملفات النظام (File System)**،
- **سجل النظام (Registry)**،
- **الخط الزمني للأحداث (Timeline)**،
- وغيرها من الأدلة الرقمية المهمة
download -> https://github.com/EricZimmerman
   

# KAPE
Download -> https://www.google.com/search?q=https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kroll-artifact-parser-extractor
# Autopsy

وتُستخدم لتحليل البيانات من:

- **الأجهزة المحمولة (Mobile Devices)**،
- **الأقراص الصلبة (Hard Drives)**،
- **ووسائط التخزين الخارجية (Removable Drives)**.

🔍 **مميزاتها:**

- تحتوي على **مكونات إضافية (Plugins)** تسهل وتسّرع عملية التحليل.
- تستخرج **معلومات قيّمة من البيانات الخام** (Raw Data) وتعرضها بشكل منظم وسهل الفهم.
- تُستخدم بشكل واسع من قبل **المحققين، والباحثين الأمنيين، وجهات إنفاذ القانون**.
download -> https://www.autopsy.com/download/

# GNU sha256sum

sha256sum evidence.dd
download -> https://github.com/coreutils/coreutils

## power shell get file hash

Get-FileHash -Algorithm SHA256 -Path evidence.img
download -> https://github.com/PowerShell/PowerShell

# Volatility

تُستخدم في

**تحليل الذاكرة (Memory Analysis)** تعمل على كلٍّ من **أنظمة Windows وLinux** ، وتُستخدم لاستخراج معلومات مهمة من **الذاكرة (RAM)** الخاصة بالجهاز الذي يتم التحقيق فيه.

- العمليات التي كانت تعمل على النظام.
- الملفات المفتوحة.
- كلمات المرور أو البيانات الحساسة الموجودة مؤقتًا في الذاكرة.
- آثار البرامج الضارة (Malware).
download -> https://www.google.com/search?q=https%3A%2F%2Fgithub.com%2Fvolatilityfoundation%2Fvolatility3%2Ftree%2Fdevelop%2Fvolatility3%2Fframework%2Fplugins%2Fwindows

## Volatility of data

non-volatile

→هي اللي بتعيش بعد ما تقفل الجهاز زي hard disk - usb - archive files

volatile

→هو اللي بيكون جوا الجهاز وهو شغال بس زي الرام 
ولو قطعت الكهربا هتطير ف ثانية 

جزء منها بيبقى متخزن عادي 

# Redline

تستخدم في ال incident response

- جمع **البيانات الجنائية (Forensic Data)** من النظام.
- تحليل هذه البيانات لتحديد أنشطة مشبوهة أو آثار هجمات
download -> https://www.google.com/search?q=https://www.mandiant.com/resources/tools/redline
