

```markdown
# Windows Artifacts Reference Guide - Analysis Tools

A comprehensive technical study guide covering **FTK Imager** as a key forensic acquisition and preview tool, detailing its usage, supported formats, data integrity mechanisms, and workflow integration.

---

## 3. Forensic Analysis Tools: FTK Imager

### Overview
**FTK Imager** is an industry-standard forensic acquisition and preview tool. It is primarily utilized during the early stages of digital forensics investigations to secure data without altering the original evidence source.

### Primary Functions & Capabilities
FTK Imager is specifically designed to:
* **Create Forensic Disk Images:** Generates bit-stream copies of media devices (e.g., hard drives, USBs).
* **Capture Physical Memory (RAM):** Extracts volatile memory from a live system for analysis of running processes and network connections.
* **Preview Files & Folders:** Allows investigators to browse directory structures and view content safely without modifying file system metadata (such as access timestamps).
* **Calculate and Verify Hashes:** Generates cryptographic checksums to establish a chain of custody and verify integrity.

### Supported Image Formats
* **RAW (dd):** A flat, uncompressed bit-by-bit copy of the storage media.
* **E01 (EnCase Format):** An expert witness format that includes metadata headers, embedded hashes, and optional data compression.

---

## 4. Evidence Integrity & Workflow

### Evidence Integrity Mechanisms
Maintaining evidence integrity is crucial for legal admissibility. FTK Imager enforces this through:
* **Hash Calculation:** Automatically computes **MD5** and **SHA1** hash values for the target media.
* **Acquisition-Time Hashing:** Hashes are generated dynamically during the acquisition process.
* **Verification:** Compares the acquisition hash with the verification hash to provide absolute mathematical proof that the evidence has not been altered or tampered with.

### FTK Imager in DFIR Workflow
In a Digital Forensics and Incident Response (DFIR) lifecycle, FTK Imager serves a precise role:
1.  **First Responder / Acquisition Tool:** Deployed at the immediate start of an investigation to preserve volatile and non-volatile data.
2.  **Pre-Analysis Execution:** Used *before* deep-dive analysis tools are introduced to the environment.
3.  **Downstream Analysis:** The output forensic images (RAW/E01) are subsequently ingested and parsed by full-scale analysis suites like **Autopsy**, Axiom, or EnCase.

```text
[Target Media/RAM] ──> (FTK Imager Acquisition) ──> [E01/RAW Image + Hashes] ──> (Autopsy / Analysis Suite)
