# Forensic & Incident Response Tools Registry

A comprehensive curated index of industry-standard Digital Forensics and Incident Response (DFIR) tools, including direct links to their open-source GitHub repositories or official enterprise download portals.

---

## 1. Full Forensic Suites & Triage Frameworks

| Tool Name | Core Analytical Purpose | Primary Download Source |
| :--- | :--- | :--- |
| **Volatility 3 & 2** | Advanced volatile memory (RAM) forensics framework for Windows & Linux. | [GitHub Repository](https://github.com/volatilityfoundation/volatility3) |
| **Velociraptor** | Next-generation endpoint monitoring, digital forensics, and live remote response. | [GitHub Repository](https://github.com/Velociraptor-攻擊/velociraptor) |
| **Eric Zimmerman Tools** | Command-line utilities for deep parsing of Windows Registry, File System, and Timelines. | [Official Download Site](https://ericzimmerman.github.io/#!index.md) / [GitHub Source](https://github.com/EricZimmerman) |
| **KAPE (Kroll Artifact Parser)** | High-speed triage collection and parsing engine to automate artifact acquisition. | [Official Download Site](https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kroll-artifact-parser-extractor) / [GitHub Community Files](https://github.com/get-kape/KapeFiles) |
| **Autopsy** | Open-source graphical digital forensics platform for disk, image, and mobile analysis. | [Official Download Site](https://www.autopsy.com/download/) / [GitHub Repository](https://github.com/sleuthkit/autopsy) |
| **Redline (Mandiant)** | Host-based triage and memory/endpoint indicator gathering tool for Incident Response. | [Official Download Site (Closed Source)](https://www.mandiant.com/resources/tools/redline) |
| **FTK Imager (Exterro)** | Standard bit-stream forensic acquisition, verification, and file preview utility. | [Official Download Site (Closed Source)](https://www.exterro.com/ftk-imager) |

---

## 2. Integrity Verification & Hashing Tools

| Tool Name | Core Analytical Purpose | Primary Download Source |
| :--- | :--- | :--- |
| **GNU sha256sum** | Native Linux utility for generating and validating SHA-256 cryptographic hashes. | *Built-in to Linux* / [GNU Coreutils GitHub](https://github.com/coreutils/coreutils) |
| **PowerShell (Get-FileHash)** | Built-in Windows environment cmdlet for generating file checksums/hashes. | *Built-in to Windows* / [PowerShell GitHub](https://github.com/PowerShell/PowerShell) |

---

## 3. Metadata, Data Extraction & Inspection Utilities

| Tool Name | Core Analytical Purpose | Primary Download Source |
| :--- | :--- | :--- |
| **ExifTool** | Read, write, and parse meta information in image, video, and file systems. | [Official Website](https://exiftool.org/) / [GitHub Mirror](https://github.com/exiftool/exiftool) |
| **pdfinfo & pdfimages** | Part of Poppler/Xpdf suite; extracts embedded structural image streams and metadata from PDFs. | [Official Binaries](https://www.xpdfreader.com/download.html) / [Poppler GitHub Source](https://github.com/freedesktop/poppler) |
| **olevba** | Part of oletools suite; parses OLE and OpenXML files to extract malicious VBA Macro scripts. | [GitHub Repository](https://github.com/decalage2/oletools) |
| **strings** | Extracts and prints readable ASCII/Unicode character strings from raw binary structures. | [Official Windows Sysinternals](https://learn.microsoft.com/en-us/sysinternals/downloads/strings) / [GNU Binutils GitHub](https://github.com/bminor/binutils-gdb) |
| **binwalk** | Fast, easy-to-use tool for analyzing, reverse engineering, and carving embedded file images. | [GitHub Repository](https://github.com/ReFirmLabs/binwalk) |

---

## 4. Steganography & Image Structure Analysis

| Tool Name | Core Analytical Purpose | Primary Download Source |
| :--- | :--- | :--- |
| **zsteg** | Detects hidden steganographic payloads in PNG and BMP image structures (highly used in CTFs). | [GitHub Repository](https://github.com/zed-0xff/zsteg) |
| **steghide** | Embeds or extracts configuration-locked and encrypted data inside JPEG, BMP, WAV, and AU files. | [GitHub Repository (Updated Branch)](https://github.com/vnaum/steghide) |
| **pngcheck** | Verifies the integrity of PNG, JNG, and MNG files; uncovers structural anomalies. | [Official Website](http://www.libpng.org/pub/png/apps/pngcheck.html) |

---

> 📌 **Note on Volatility Plugins:** Internal analytical modules such as `pslist`, `psscan`, `malfind`, `netscan`, `procdump`, `cmdline`, `dlllist`, `filescan`, `printkey`, `sessions`, `apihooks`, and `psxview` are **natively integrated** inside the core framework. Their execution logic can be reviewed directly in the [Volatility 3 Framework Plugins Subdirectory](https://github.com/volatilityfoundation/volatility3/tree/develop/volatility3/framework/plugins/windows).
