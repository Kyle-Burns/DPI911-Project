# DPI911-Project
## Project Outline

- Kyle Burns, Bradley Sharkey, Itay Gurvich
- Group 2
- Each week has a set of planned Attacks that are apart of the MITRE ATT&CK framework. We intend on creating Splunk rules and test-case files to trigger the corresponding rule.
- [Sysmon Configuration](sysmonconfig-export.xml)
- [Combined Splunk Conf](SplunkAlert_Confs/SplunkComplete.conf)
## Feb 21st
- [x] Project Outlined
- [x] Provide outline for overall tasks.

## Feb 28th
### Initial Access
- [x] Exploit Public-Facing Application: Exploiting bugs and weaknesses found within applications running on public-facing systems.
  - [x] [ExploitPublicFacing.conf](SplunkAlert_Confs/ExploitPublicFacing.conf)
    - Search Term: "NT AUTHORITY\\SYSTEM" AND ParentImage="C:\\Program Files\\Apache Software Foundation\\tomcat\\apache-tomcat-8.0.33\\bin\\tomcat8.exe"
  - [x] Use Metasploit Module
    - exploit/multi/http/struts_dni_rest_exec

### Execution
- [x] Control Panel Items: Control panel items are .exe or .cpl files that can be executed using the command line or the control panel graphical interface application that can be used as execution payloads.

  - [x] [ControlPanelItems.conf](SplunkAlert_Confs/ControlPanelItems.conf)
    - Search Term: control.exe AND .cpl NOT [| inputlookup trustedcpl.csv | fields ParentCommandLine]
  - [x] [control_panel_demo.7z](Scripts/control_panel_demo.7z)
- [x] Dynamic Data Exchange: Client-server protocol for inter-process communications between applications. Microsoft Office documents can include DDE commands allowing for execution of malicious code.
  - [x] [DynamicDataExchange.conf](SplunkAlert_Confs/DynamicDataExchange.conf)
    - Search Term: Image=*\\cmd.exe OR Image=*\\powershell.exe AND ParentImage=*\\WINWORD.EXE
  - [x] [DDE.docx](Scripts/DDE.docx) Note: Only works on Word 2016 and lower
- [ ] ~~Execution through API~~

## Mar 7th
### Persistence
- [x] Screensaver: Portable executable files with a .src extension that run by scrnsave.exe after a specified time of user inactivity. Can be used to maintain malware persistence by running malware after certain time frame.
  - [x] [ScreensaverPersistance.conf](SplunkAlert_Confs/ScreensaverPersistance.conf)
    - Search Term: *.scr NOT [| inputlookup trustedscr.csv | fields CommandLine]
  - [x] [Script](https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1180/T1180.md)
- [x] Security Support Provider: DLL files loaded into the local security authority (lsass.exe) process on system startup. Once loaded DLLs have access to encrypted and plain text Windows passwords.
  - [x] [SecuritySupportProvider.conf](SplunkAlert_Confs/SecuritySupportProvider.conf)
    - Search Term: "HKLM\\System\\CurrentControlSet\\Control\\Lsa\\Security Packages" AND Task="13"
  - [x] [ssp.ps1](Scripts/ssp.ps1)
- [x] Service Registry Permissions Weakness: Windows services registry keys can be modified to include specific execution parameters allowing for the changing of a services executable path.
  - [x] [ServiceRegistryPermissionWeakness.conf](SplunkAlert_Confs/ServiceRegistryPermissionWeakness.conf)
    - Search Term: HKLM\\System\\CurrentControlSet\\services\\ AND Task=13
  - [x] [regVul.ps1](Scripts/regVuln.ps1)
- [x] Shortcut Modification: Symbolic links that point to a specific executable when clicked or executed by startup process. Legitimate shortcuts path can be changed to malicious executable.
  - [x] [ShortcutModificationPersistence.conf](SplunkAlert_Confs/ShortcutModificationPersistence.conf)
    - Search Term: Task=11 AND C:\\Users\\*\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Startup\\*.lnk
  - [x] [modLink.ps1](Scripts/modLink.ps1)
- [ ] ~~System Firmware~~
### Privilege Escalation
- [x] Exploitation for Privilege Escalation: Exploiting a bug in a code to grant elevated privileges to a malicious user. This is usually made by making a running process with an elevated privilege to create a child process which will inherit the parent process privileges.
  - [x] [ExploitationforPrivEsc.conf](SplunkAlert_Confs/ExploitationforPrivEsc.conf)
    - Search Term: ParentImage="C:\\ManageEngine\\DesktopCentral_Server\\bin\\*.jsp" AND "*.exe"
  - [x] Use Metasploit Modules 
    - exploit/windows/http/manageengine_connectionid_write
    - exploit/windows/local/ms14_058_track_popup_menu
- [ ] ~~Extra Window Memory Injection~~
- [x] File System Permissions Weakness: Exploit misconfiguration of read / write permissions on filesystem locations. This can allow an adversary to replace legitimate binaries and executables with malicious versions which will be executed.
  - [x] [FileSystemPermissionsWeakness.conf](SplunkAlert_Confs/FileSystemPermissionsWeakness.conf)
    - Search Term: "C:\\Program Files\\win32.exe" AND "TimeCreated"
  - [x] [filesysperm.ps1](Scripts/filesysperm.ps1)

## Mar 14th
### Defense Evasion
- [x] Compiled HTML File: Compiled HTML Files (.chm extension) are a legitimate file type part of the Windows HTML Help System. Adversaries can use this file type to conceal malicious code by embedding it within a seemingly-benign file.
  - [x] [CompiledHTMLFile.conf](SplunkAlert_Confs/CompiledHTMLFile.conf)
    - Search Term: hh.exe AND .chm AND cmd.exe OR powershell.exe
  - [x] [compiledHtmlFile.ps1](Scripts/compiledHtmlFile.ps1)
- [ ] ~~Component Firmware~~
- [x] Component Object Model Hijacking: COM allows for interaction between Windows software components through the operating system.COM references can be hijacked to execute malicious code instead of legitimate software.

  - [x] [ComponentObjectModelHijacking.conf](SplunkAlert_Confs/ComponentObjectModelHijacking.conf)
    - Search Term: Task=13 AND HKU\\*\\CLSID
  - [x] [Script](https://github.com/redcanaryco/atomic-red-team/tree/6965fc15ef872281346d99d5eea952907167dec3/atomics/T1122)
- [x] Control Panel Items: Control panel items are .exe or .cpl files that can be executed using the command line or the control panel graphical interface application that can be used as execution payloads.
  - [x] [ControlPanelItems](SplunkAlert_Confs/ControlPanelItems.conf)
    - Search Term: control.exe AND .cpl NOT [| inputlookup trustedcpl.csv | fields ParentCommandLine]
  - [x] [control_panel_demo.zip](Scripts/control_panel_demo.zip)
- [x] DCShadow: A way of manipulating AD data by simulating the actions of a DC. Can allow for object injection into AD environment.
  - [x] [DCShadow.conf](SplunkAlert_Confs/DCShadow.conf)
    - Search Term: mimikatz.exe
  - [x] [Instructions](https://github.com/redcanaryco/atomic-red-team/tree/6965fc15ef872281346d99d5eea952907167dec3/atomics/T1207)
- [x] DLL Search Order Hijacking: Windows use a common method for loading DLL files into program. Abusing the DLL search can allow for malicious DLLs to be loaded.
  - [x] [DllHijack.conf](SplunkAlert_Confs/DllHijack.conf)
    - Search Term: Task=11 AND “.dll”
  - [x] [dllHijack.ps1](Scripts/dllHijack.ps1)

## March 21st
### Credential Access
- [x] Credential Dumping: Theses are techniques used to gain credentials on the system or across the network and are usually found in the form of plaintext or hashed. Tools like pwdumpx.exe and Mimikatz are commonly used. 
  - [x] [CredentialDumping.conf](SplunkAlert_Confs/CredentialDumping.conf)
    - Search Term: (procdump.exe AND lsass.exe) OR mimikatz.exe OR pwdump.exe OR secretdump.py OR gsecdump.exe
  - [x] [credentialDump.bat](Scripts/credentialDump.bat)
- [x] Credentials in Files
  - [x] [CredentialsinFiles.conf](SplunkAlert_Confs/CredentialsinFiles.conf)
    - Search Term: findstr.exe AND (pass OR pwd OR password OR login OR credentials OR login)
  - [x] [credInFile.ps1](Scripts/credInFile.ps1)

### Discovery
- [ ] ~~Peripheral Device Discovery~~
- [x] Permission Groups Discovery: Adversaries attempt to determine the domain or local groups including permissions and settings.
  - [x] [PermissionGroupsDiscovery.conf](SplunkAlert_Confs/PermissionGroupsDiscovery.conf)
    - Search Term: net.exe AND localgroup OR (group /domain)
  - [x] [permGroupDisco.bat](Scripts/permGroupDisco.bat)
### Lateral Movement
- [x] Exploitation of Remote Services: Lateral movement through the exploitation of software bugs and weaknesses found on internal systems.
  - [x] [EternalBlueExploitationofRemoteServices.conf](SplunkAlert_Confs/EternalBlueExploitationofRemoteServices.conf)
    - Search Term: Task=1 AND parentimage AND “spoolsv.exe” AND commandline AND “CMD”
  - [x] Use Metasploit Module
    - exploit/windows/smb/ms17_010_eternalblue
- [x] Logon Scripts: Allows for scripts to be run when a user logs into a system. Can be altered to execute malicious tools when a user logs into a system.
  - [x] [LogonScripts.conf](SplunkAlert_Confs/LogonScripts.conf)
    - Search Term: reg.exe AND UserInitMprLogonScript
  - [x] [logonScripts.bat](Scripts/logonScripts.bat)

## March 28th
### Collection
- [ ] ~~Data from Local System~~
### Exfiltration
- [x] Data Compressed: Data can be compressed over the network to minimize the chance of network detection of know data. This is be done using custom compression algorithms or common ones like 7zi0p, ZIP or RAR.
  - [x] [DataCompressed.conf](SplunkAlert_Confs/DataCompressed.conf)
    - Search Term: (rar.exe or 7zip.exe or compact.exe) AND (powershell.exe cmd.exe)
  - [x] [compressC.ps1](Scripts/compressC.ps1)
### Command and Control
- [x] Connection Proxy: A system uses a proxy to forward traffic on its behalf, an adversary might use this as an intermediate for network communication. 
  - [x] [ConnectionProxy](SplunkAlert_Confs/ConnectionProxy.conf)
    - Search Term: netsh winhttp
  - [x] [Instructions](https://www.thewindowsclub.com/reset-winhttp-proxy-settings-windows)
- [ ] ~~Custom Command and Control Protocol~~

## Apr 4th 
- [x] Completion



