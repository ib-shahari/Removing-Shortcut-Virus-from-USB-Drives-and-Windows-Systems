# Removing Shortcut Virus from USB Drives and Windows Systems

The shortcut virus hides legitimate files and replaces them with .lnk extensions. It creates registry entries to ensure persistence and automatic execution upon system startup.

## 1. USB Drive Disinfection

Do not access the drive via File Explorer or click any shortcuts. Open Command Prompt (CMD) as Administrator:

Navigate to the USB drive letter (e.g., G:).

Execute the following commands:

### Restore hidden files and remove system attributes
```bash
attrib -h -r -s /s /d *.*
```
### Delete all shortcut files
```bash
del *.lnk
```
### Delete autorun configuration files
```bash
del autorun.inf
```
### Delete suspicious executable files (optional)
```bash
del *.exe
```

## 2. Process and System Cleanup

Full eradication requires terminating active processes and deleting source files:

Task Manager: Terminate DriveMgr.exe or any unrecognized active processes.

Directory Audit: Delete suspicious files in the following paths:

```
C:\Users\%username%\AppData\Roaming

C:\Users\%username%\AppData\Local

C:\ProgramData
```
## 3. Registry Modification

To prevent the virus from self-restarting, remove malicious entries in the Registry Editor (regedit) under:

```
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run

HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run
```
## 4. Final Steps

Perform a full system scan using your primary security software.

Manually reorganize directories after restoration.
