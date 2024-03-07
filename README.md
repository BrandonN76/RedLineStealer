## Malware Analysis
### RedLineStealer Family

**Description:**  
In this analysis, I will be looking at a malware sample called “WEXTRACT.EXE .MUI,” a part of the RedLineStealer family. I will be performing static and dynamic analysis of the malware to get a better understanding of the malware’s characteristics, functionality, and potential impact on the compromised system.

**VirusTotal Report:**
<img src="https://i.imgur.com/pc3X7t2.png">
**Hashes:**  
- MD5: 7b6947899025e73ba2566ce8df23424a  
- SHA-1: ab0fce8b95dc43c410bed7d67419a412bbb27b4e  
- SHA-256: 8edf18907eeca834a387011ff67ea3c40be821c1fd14be4c2cb6810dd8cd9c6f

**Original File Name:** WEXTRACT.EXE.MUI  
**File Name:** 8edf18907eeca834a387011ff67ea3c40be821c1fd14be4c2cb6810dd8cd9c6f.exe  
**File Type:** PE32  
**File Size:** 534528 bytes  
**Libraries:**  
- ADVAPI32.dll  
- KERNEL32.dll  
- GDI32.dll  
- USER32.dll  
- msvcrt.dll  
- COMCTL32.dll  
- Cabinet.dll  
- VERSION.dll

**Notable Strings:**  
- Sleep  
- RegDeleteValue  
- DeleteFile  
- OpenProcessToken  
- LookupPrivilegeValue  
- AdjustTokenPrivileges  
- CheckTokenMembership  
- SeShutdownPrivilege  
- GetTokenInformation  
- GetTickCount  
- GetSystemTimeAsFileTime  
- RegSetValueEx  
- RegCreateKeyEx  
- CreateProcess  
- LoadLibrary  
- RUNPROGRAM  
- rundll32.exe %sadvpack.dll,DelNodeRunDLL32 "%s"  
- rundll32.exe %s,InstallHinfSection %s 128 %s  
- FindFirstFile  
- FindNextFile  
- GetSystemDirectory  
- GetWindowsDirectory  
- Software\Microsoft\Windows\CurrentVersion\RunOnce  
- GetCurrentProcessId  
- GetCurrentProcess  
- GetCurrentThreadId  
- SendMessage  
- GetWindowLong  
- SetWindowLong  
- DecryptFile  
- RegQueryInfoKey  
- RegQueryValueEx  
- GetVolumeInformation  
- GetDesktopWindow  
- AllocateAndInitializeSid  
- EqualSid  
- FreeSid  
- EnumResourceLanguages  
- WritePrivateProfileString  
- Extract  
- SetFileAttributes  
- RemoveDirectory  
- WriteFile  
- SHBrowseForFolder  
- SHGetPathFromIDList  
- GetExitCodeProcess  
- TerminateProcess  
- SetCurrentDirectory

**Dynamic Analysis**

**Files Created:**  
<img src="https://i.imgur.com/tKJqkqS.png">
- C:\Users\vboxuser\AppData\Local\Temp\IXP000.TMP\BQ4Ga08.exe  
- C:\Users\vboxuser\AppData\Local\Temp\IXP001.TMP\3bd934uq.exe  
- C:\Users\vboxuser\AppData\Local\Temp\IXP001.TMP\4Lg4CB6.exe  
- C:\Users\vboxuser\AppData\Local\Temp\IXP000.TMP\5kg59wh.exe  
- C:\Users\vboxuser\AppData\Local\Temp\is64.txt  
- C:\Users\vboxuser\AppData\Local\Temp\is64.bat  
- C:\Users\vboxuser\AppData\Local\Temp\is64.fil

**Files Opened:**  
- C:\Windows\Microsoft.NET\Framework\v4.0.30319\AppLaunch.exe  
- C:\Users\vboxuser\AppData\Local\Microsoft\Windows\INetCookies  
- C:\Users\vboxuser\AppData\Local\Microsoft\Windows\INetCache  
- C:\Users\vboxuser\AppData\Local\Microsoft\Windows\Caches\cversions.1.db  
- C:\Users\vboxuser\AppData\Local\Microsoft\Windows\History\History.IE5  
- C:\Windows\System32\wbem\WmiPrvSE.exe (Windows Management instrumentation)

**Files Deleted:**  
- C:\Users\vboxuser\AppData\Local\Temp\IXP000.TMP\BQ4Ga08.exe  
- C:\Users\vboxuser\AppData\Local\Temp\IXP001.TMP\3bd934uq.exe  
- C:\Users\vboxuser\AppData\Local\Temp\IXP001.TMP\4Lg4CB6.exe  
- C:\Users\vboxuser\AppData\Local\Temp\IXP000.TMP\5kg59wh.exe

**Notable Registry Keys Added:**  
- HKLM\SYSTEM\ControlSet001\Services\bam\State\UserSettings\S-1-5-21-1829532676-1566079715-339616858-1000\\Device\HarddiskVolume1\Users\vboxuser\AppData\Local\Temp\IXP000.TMP\5kg59wh.exe  
- HKU\S-1-5-21-1829532676-1566079715-339616858-1000\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Compatibility Assistant\Store\C:\Users\vboxuser\Desktop\8edf18907eeca834a387011ff67ea3c40be821c1fd14be4c2cb6810dd8cd9c6f.exe

**Network Analysis:**

<img src="https://i.imgur.com/6Zfs2ul.png">

- IP Address: 5.42.92.51  
- Port: 19057  
- Location: Sweden, Stockholm

**Tools used:**
- PEStudio: Used for static analysis of the executable.
- RegShot: Monitored changes to the system's registry.
- Capa: Assisted in identifying capabilities and characteristics of the malware.
- Procmon: Monitored system activity in real-time.
- Wireshark: Captured and analyzed network traffic.

**Overview:**  
The analyzed malware, named "WEXTRACT.EXE .MUI," has a range of functions related to file manipulation, registry modification, and network activity. It creates and deletes several files, modifies registry keys, and attempts to contact a remote server in Sweden. The malware shows interest in system and user directories, including temporary folders and user-specific locations.
