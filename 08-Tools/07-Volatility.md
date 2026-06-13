python vol.py -f <file_name>.mem windows.malfind

```
pslist
```

👉 العمليات اللي شغالة

```
psscan
```

👉 يجيب العمليات حتى المحذوفة أو المخفية

```
pstree
```

👉 يوضح مين شغّل مين (شجرة العمليات)

## 3. العمليات المشبوهة (Injection)

```
malfind
```

👉 يكتشف:

- كود محقون
- Malware متخبي

---

## 4. سطر الأوامر

```
cmdline
```

👉 يوضح البرنامج اتشغل بإيه

---

## 5. المسار الكامل للبرنامج

```
dlllist
```

👉 يعرض:

- DLLs
- مكان تشغيل البرنامج

---

## 🌐 تحليل الشبكة

## 6. الاتصالات

```
netscan
```

👉 يطلع:

- IPs
- Ports
- اتصالات خارجية

---

# 📂 استخراج بيانات

## 7. استخراج Process

```
procdump-p PID-D out/
```

👉 تطلع الملف الخبيث من الذاكرة

---

## 8. استخراج DLL

```
dlldump
```

---

# 🧠 أوامر متقدمة

## 9. البحث عن ملفات مفتوحة

```
filescan
```

---

## 10. Registry

```
printkey
```

👉 يشوف:

- Persistence
- Autorun

---

## 11. البحث عن Strings

```
strings
```

---

## 12. Sessions (المستخدمين)

```
sessions
```

---

# 🧨 أوامر خاصة بالـ Malware

## 13. API Hooks

```
apihooks
```

## 14. Hidden processes

```
psxview
```

👉 يقارن طرق عرض العمليات

---

# 🎯 تمشي بيهم ازاي (الترتيب الصح)

امشي كده:

1. `imageinfo`
2. `pslist`
3. `pstree`
4. `psscan`
5. `malfind`
6. `netscan`
7. `cmdline`
8. `procdump`




# Windows Artifacts Reference Guide - Analysis Tools (Volatility)

A comprehensive technical study guide covering **Volatility** as an advanced memory forensics framework, detailing core plugins, architectural differences, and memory investigation workflows.

---

## 7. Forensic Analysis Tools: Volatility

### Overview
**Volatility** is an open-source memory forensics framework. It is explicitly designed to analyze volatile memory (RAM) images and is widely recognized as an essential tool in incident response, threat hunting, and malware analysis.

### Importance of Memory Analysis
While disk analysis provides a rich historical record, memory analysis captures the live, operational state of a system because:
*   **Volatile Execution:** Running processes exist exclusively within RAM.
*   **Transient Data:** Active network connections and open sockets may never be committed or saved to the permanent disk.
*   **Malware Evasion:** Advanced malware samples (fileless malware, rootkits) often hide or execute strictly within memory to evade traditional disk-based forensic analysis.

### Forensic Capabilities
Volatility is capable of extracting vital runtime artifacts, including:
*   Running and hidden processes.
*   Loaded Dynamic Link Libraries (DLLs) and injected code segments.
*   Active/terminated network connections, ports, and sockets.
*   Open files, security handles, and registry objects.
*   Definitive evidence of malicious or anomalous software activity.

---

## 8. Version Comparison & Common Plugins

### Volatility Versioning
The framework has evolved across two primary versions used in investigations:

| Feature / Attribute | Volatility 2 | Volatility 3 |
| :--- | :--- | :--- |
| **Profile Requirement** | Requires a specific OS/Memory Profile (`--profile`) | No profiles required (automatically detects architecture) |
| **Status** | Deprecated | Active development / Still evolving |
| **Language/Backend** | Python 2 | Completely rewritten in Python 3 with improved parsing |

### Common Ingest & Parsing Plugins
The following table outlines standard plugins utilized to extract core memory structures:

| Plugin Name | Analytical Purpose |
| :--- | :--- |
| `pslist` / `psscan` | Lists active running processes (scanning uncovers unlinked/hidden processes). |
| `netscan` | Scans for active, established, or listening network connections. |
| `dlllist` | Displays loaded DLLs for specific processes. |
| `malfind` | Detects potential shellcode, injected code, and anomalous memory protections (`PAGE_EXECUTE_READWRITE`). |
| `handles` | Displays open files, registry keys, and synchronization objects held by processes. |

---

## 9. Memory Forensics Workflow

### Investigative Steps
To correctly integrate volatile memory parsing into a Digital Forensics and Incident Response (DFIR) lifecycle, follow this workflow:

1.  **Capture RAM:** Secure the memory dump immediately using trusted acquisition tools like **FTK Imager** or **DumpIt** before modifying the live system state.
2.  **Identify OS and Architecture:** Determine the exact operating system build and architecture of the target machine.
3.  **Run Core Volatility Plugins:** Execute baseline plugins (`pslist`, `netscan`, `malfind`) to map active execution status.
4.  **Correlate with Disk Artifacts:** Cross-reference findings (such as suspicious PIDs, parent-child process anomalies, or external IPs) with traditional disk artifacts like ShimCache, Prefetch, and Event Logs.

```text
[Live System] ──> (Capture: FTK Imager/DumpIt) ──> [RAM Dump] ──> (Volatility Plugins) ──> [Correlate with Disk]
