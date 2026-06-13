## 2. LNK Files (Shortcuts)

### Overview
**.lnk Files** are Windows shortcut files (Shell Link files) that point to an application, file, or directory. They serve as rich sources of user activity evidence.

### Technical Characteristics
*   **File Extension:** `.lnk`
*   **File Signature (Magic Bytes):** `0x4C 00 00 00` at offset `0` (highly useful for file carving).
*   **Contents:**
    *   Path of the target file.
    *   The size of the target when it was last accessed.
    *   Serial number of the volume.
    *   Target attributes (Read-only, hidden, system, volume label, encryption, sparse, compressed, etc.).
    *   MAC (Media Access Control) address of the host computer (not always present).

### Forensic Value & Limitations
*   **Value:** Proves file presence and timestamps. Can be correlated directly with the **MFT (Master File Table)**, **Prefetch**, and **Event Logs**.
*   **Limitation:** The presence of a `.lnk` file is **not definitive proof of execution** on its own (it primarily proves file opening or interaction).

### LNK Files - Filesystem Timestamps
*   **Creation Time:** Indicates when the shortcut file itself was created. This often corresponds to the **first interaction** with the target file.
*   **Modification Time:** Updated when the shortcut is reused or when its metadata changes.

### Artifact Locations
LNK files tracking user activity can typically be found in the following directories:
*   `%USERPROFILE%\Recent`
*   `%USERNAME%\AppData\Roaming\Microsoft\Windows\Recent`

### Analytical Tools & Commands
*   **ExifTool:** Excellent for quick metadata extraction.
*   **LinkParser.exe:** A dedicated GUI/CLI shortcut parser.
*   **Windows LNK Parsing Utility** (By tzworks).
*   **LECmd.exe (LNK Explorer Command Line):** An industry-standard parser by Eric Zimmerman.

#### Practical Example:
*   **Parsing the Recent Items directory using LECmd:**
*   LECmd
بتجيب حاجات ممسوحه عادي 
LECmd.exe -d "%userprofile%\AppData\Roaming\Microsoft\Windows\Recent\" --csv "path”
    ```bash
    .\LECmd.exe -d "%userprofile%\AppData\Roaming\Microsoft\Windows\Recent" --csv "path"
    ```
