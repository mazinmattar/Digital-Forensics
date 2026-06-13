- Data encryption

الجهاز بقي يشفر الملفات بكل سهولة ومن غير ما اليوزر يلاحظ

- Data integrity

اي خلل في الانتجرتي تخليك تشك 

- Access control

بتخليك تشوف مين اللي مسموحله يقرأ ويعدل ويكتب ويعمل كل حاجه
# File System Basics

## NTFS Structure

NTFS (New Technology File System) is the default file system used in modern Windows operating systems. It offers enhanced security, reliability, and scalability compared to FAT/FAT32.

### Key Advantages of NTFS over FAT

1. Reliability & Journaling
2. Extended Metadata Support
3. Security Enhancements
4. Scalability
5. File Compression Support
6. Disk Quotas
7. Better Handling of Fragmentation
8. Alternate Data Streams (ADS)

![NTFS Structure](images/ntfs-structure.png)

---

## The Master File Table (MFT)

The Master File Table (MFT) is the core database of NTFS. Every file and directory stored on an NTFS volume is represented by an entry within the MFT.

### Important MFT Entries

- `$MFT` – Master File Table
- `$MFTMirr` – Backup copy of critical MFT records
- `$LogFile` – Transaction log for recovery
- `$Volume` – Volume information
- `$AttrDef` – Attribute definitions
- `$Root` – Root Directory / INDEX_ROOT
- `$Bitmap` – Allocation bitmap
- `$Boot` – Boot sector information
- `$BadClus` – Bad cluster tracking
- `$Secure` – Security descriptors
- `$UpCase` – Unicode character mappings
- `$Extend` – Extended system metadata

### Why is the MFT Important?

The MFT is one of the first locations examined during a forensic investigation because it contains metadata about files, directories, timestamps, and allocation information.

![MFT Entries](images/mft-entries.png)

---

## MFT Attributes

Each MFT record contains attributes that describe different aspects of a file.

### Common NTFS Attributes

| Attribute | Hex Value | Description |
|------------|-----------|-------------|
| `$STANDARD_INFORMATION` | 0x10 | File timestamps and permissions |
| `$ATTRIBUTE_LIST` | 0x20 | Additional attributes |
| `$FILE_NAME` | 0x30 | File name information |
| `$OBJECT_ID` | 0x40 | Unique file identifier |
| `$SECURITY_DESCRIPTOR` | 0x50 | Security information |
| `$DATA` | 0x80 | Actual file content |
| `$INDEX_ROOT` | 0x90 | Root directory index |
| `$INDEX_ALLOCATION` | 0xA0 | Directory index allocation |
| `$BITMAP` | 0xB0 | Allocation bitmap |

### Forensic Significance

MFT attributes help investigators determine:

- File creation time
- Last modification time
- Last access time
- Metadata modification time
- Original file names
- File locations
- Security permissions
- Evidence of deleted files

![MFT Attributes](images/mft-attributes.png)

---

### References

- Windows Internals
- NTFS Documentation
- SANS DFIR Resources
- Microsoft Documentation
