# Disk Fundamentals

Before understanding file systems such as NTFS, it is important to understand how data is physically organized on a storage device.

## Tracks

A **Track** is a circular path on the surface of a hard disk platter.

- Data is written and read along these circular paths.
- Each platter contains multiple concentric tracks.
- Tracks are used to organize data physically on the disk.

---

## Sectors

A **Sector** is the smallest physical storage unit on a disk.

- A sector represents a subdivision of a track.
- Data is stored and accessed sector by sector.
- Common sector sizes:
  - 512 Bytes
  - 4096 Bytes (4K Advanced Format)

### Why Sectors Matter in Forensics

Investigators often work with sector-level data when:

- Recovering deleted files
- Analyzing disk images
- Examining unallocated space
- Carving files from raw storage

---

## Clusters

A **Cluster** is a group of one or more sectors combined by the file system.

- The operating system allocates storage in clusters rather than individual sectors.
- Files are stored using clusters.
- Even a very small file occupies at least one cluster.

### Example

If the cluster size is **4096 bytes**:

- A file of 100 bytes still consumes 4096 bytes.
- The unused space inside the cluster is known as **Slack Space**.

### Forensic Significance

Slack Space may contain:

- Fragments of deleted files
- Previously stored data
- Potential evidence left behind by user activity

---

## Cylinders

A **Cylinder** is a collection of tracks with the same radius across all platters in a hard disk.

- Represents a vertical alignment of tracks.
- Historically used to improve disk access efficiency.
- Important when studying legacy storage architectures.

---

## Disk Structure Overview

The relationship between disk components can be summarized as:

```text
Disk
 └── Platters
      └── Tracks
           └── Sectors
                └── Clusters
```

![Hard Disk Structure](images/hard-disk-structure.png)

---

## Forensic Relevance

Understanding disk structure helps investigators:

- Analyze forensic disk images.
- Recover deleted information.
- Understand file allocation mechanisms.
- Examine slack space and unallocated space.
- Interpret file system artifacts correctly.
