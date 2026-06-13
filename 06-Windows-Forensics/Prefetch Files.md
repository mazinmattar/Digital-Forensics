# Windows Artifacts – Prefetch Files (Continued)

> “An application needs to run for about 10 seconds to generate a valid Prefetch file.”

---

## Important Notes

- Prefetch files are path-based.
- Same executable name + different locations = different `.pf` files.
- Useful for identifying copied or masqueraded executables.

### Example


C:\Windows\System32\cmd.exe
C:\Users\Abdo\Documents\cmd.exe


If both are executed:
- Two different `.pf` files will be created.
- One Prefetch file for each execution path.

### Helps distinguish between:
- Legitimate system binaries
- Copied or renamed executables used by attackers
- Masquerading and malware execution paths

---

## Windows Artifacts (Prefetch Files) – Registry & Configuration

### Registry Key


Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management\PrefetchParameters


---

### No Prefetch Files

- Some systems may have no Prefetch files in:

C:\Windows\Prefetch


---

### EnablePrefetcher Values

- `0` = Disabled  
- `1` = Enabled (boot only)  
- `2` = Enabled (applications only)  
- `3` = Enabled (boot and applications) [Default]

---

## Tools

- PECmd (Eric Zimmerman)
- WinPrefetchView (NirSoft)
