# Windows Artifacts Reference Guide

A comprehensive technical study guide covering key Windows digital forensics artifacts, including Application Compatibility Cache (ShimCache) and LNK Files (Shortcuts), detailing their purposes, registry locations, forensic values, and analytical tools.

---

## 1. Application Compatibility Cache (ShimCache)

### Overview
The **Application Compatibility Cache (ShimCache)** is a critical Windows component used by the operating system to identify applications that may require compatibility fixes (shims) to execute properly.

### Key Characteristics & Mechanics
*   **Purpose:** Helps Windows determine how to properly run older or incompatible applications.
*   **How it works:** Tracks executable files and scripts that interact with the target system.
*   **Storage:** Data is actively stored in **kernel memory**.
*   **Persistence:** Information is written to the Windows Registry when the system shuts down or restarts.

### Forensic Value
ShimCache is highly valuable for identifying evidence of execution and file presence:
*   Executable or script names.
*   Full file paths.
*   File last modified time.
*   Binary size.
*   Whether the file was actually executed or just viewed in Windows Explorer.

### Registry Location
```text
HKLM\SYSTEM\ControlSet00x\Control\Session Manager\AppCompatCache
```

### Analytical Tools & Commands
*   **ShimCacheMem:** Used for volatility/memory analysis.
*   **ShimCacheParser.py:** A widely used Python script to parse the cache data.
*   **AppCompatCacheParser:** A powerful command-line parsing utility.

#### Practical Examples:
*   **Parsing a baseline system hive:**
    ```bash
    .\AppCompatCacheParser.exe -f "C:\Path\To\SYSTEM" --csv "C:\Path\To\Output.csv"
    ```
*   **Parsing a live/copied system target to the Desktop:**
    ```bash
    .\AppCompatCacheParser.exe --csv C:\Users\Mazin\Desktop\ --csvf AppCompat.csv
