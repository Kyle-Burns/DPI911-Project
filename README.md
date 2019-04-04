     /$$$$$$$                      /$$         /$$$$$$$                  /$$       /$$ /$$                    
    | $$__  $$                    | $$        | $$__  $$                | $$      | $$|__/                    
    | $$  \ $$  /$$$$$$   /$$$$$$$| $$$$$$$   | $$  \ $$  /$$$$$$   /$$$$$$$  /$$$$$$$ /$$  /$$$$$$   /$$$$$$$
    | $$$$$$$  |____  $$ /$$_____/| $$__  $$  | $$  | $$ |____  $$ /$$__  $$ /$$__  $$| $$ /$$__  $$ /$$_____/
    | $$__  $$  /$$$$$$$|  $$$$$$ | $$  \ $$  | $$  | $$  /$$$$$$$| $$  | $$| $$  | $$| $$| $$$$$$$$|  $$$$$$ 
    | $$  \ $$ /$$__  $$ \____  $$| $$  | $$  | $$  | $$ /$$__  $$| $$  | $$| $$  | $$| $$| $$_____/ \____  $$
    | $$$$$$$/|  $$$$$$$ /$$$$$$$/| $$  | $$  | $$$$$$$/|  $$$$$$$|  $$$$$$$|  $$$$$$$| $$|  $$$$$$$ /$$$$$$$/
    |_______/  \_______/|_______/ |__/  |__/  |_______/  \_______/ \_______/ \_______/|__/ \_______/|_______/ 

                                                                                                              
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
- [x] Exploit Public-Facing Application
  - [x] [ExploitPublicFacing.conf](SplunkAlert_Confs/ExploitPublicFacing.conf)
  - [x] Use Metasploit Module
    - exploit/multi/http/struts_dni_rest_exec

### Execution
- [x] Control Panel Items
  - [x] [ControlPanelItems.conf](SplunkAlert_Confs/ControlPanelItems.conf)
  - [x] [control_panel_demo.7z](Scripts/control_panel_demo.7z)
- [x] Dynamic Data Exchange
  - [x] [DynamicDataExchange.conf](SplunkAlert_Confs/DynamicDataExchange.conf)
  - [x] [DDE.docx](Scripts/DDE.docx) Note: Only works on Word 2016 and lower
- [ ] ~~Execution through API~~

## Mar 7th
### Persistence
- [x] Screensaver
  - [x] [ScreensaverPersistance.conf](SplunkAlert_Confs/ScreensaverPersistance.conf)
  - [x] [Script](https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1180/T1180.md)
- [x] Security Support Provider
  - [x] [SecuritySupportProvider.conf](SplunkAlert_Confs/SecuritySupportProvider.conf)
  - [x] [ssp.ps1](Scripts/ssp.ps1)
- [x] Service Registry Permissions Weakness
  - [x] [ServiceRegistryPermissionWeakness.conf](SplunkAlert_Confs/ServiceRegistryPermissionWeakness.conf)
  - [x] [regVul.ps1](Scripts/regVuln.ps1)
- [x] Shortcut Modification
  - [x] [ShortcutModificationPersistence.conf](SplunkAlert_Confs/ShortcutModificationPersistence.conf)
  - [x] [modLink.ps1](Scripts/modLink.ps1)
- [ ] ~~System Firmware~~
### Privilege Escalation
- [x] Exploitation for Privilege Escalation
  - [x] [ExploitationforPrivEsc.conf](SplunkAlert_Confs/ExploitationforPrivEsc.conf)
  - [x] Use Metasploit Modules 
    - exploit/windows/http/manageengine_connectionid_write
    - exploit/windows/local/ms14_058_track_popup_menu
- [ ] ~~Extra Window Memory Injection~~
- [x] File System Permissions Weakness
  - [x] [FileSystemPermissionsWeakness.conf](SplunkAlert_Confs/FileSystemPermissionsWeakness.conf)
  - [x] [filesysperm.ps1](Scripts/filesysperm.ps1)

## Mar 14th
### Defense Evasion
- [x] Compiled HTML File
  - [x] [CompiledHTMLFile.conf](SplunkAlert_Confs/CompiledHTMLFile.conf)
  - [x] [compiledHtmlFile.ps1](Scripts/compiledHtmlFile.ps1)
- [ ] ~~Component Firmware~~
- [x] Component Object Model Hijacking
  - [x] [ComponentObjectModelHijacking.conf](SplunkAlert_Confs/ComponentObjectModelHijacking.conf)
  - [x] [Script](https://github.com/redcanaryco/atomic-red-team/tree/6965fc15ef872281346d99d5eea952907167dec3/atomics/T1122)
- [x] Control Panel Items
  - [x] [ControlPanelItems](SplunkAlert_Confs/ControlPanelItems.conf)
  - [x] [control_panel_demo.zip](Scripts/control_panel_demo.zip)
- [x] DCShadow
  - [x] [DCShadow.conf](SplunkAlert_Confs/DCShadow.conf)
  - [x] [Instructions](https://github.com/redcanaryco/atomic-red-team/tree/6965fc15ef872281346d99d5eea952907167dec3/atomics/T1207)
- [x] DLL Search Order Hijacking
  - [x] [DllHijack.conf](SplunkAlert_Confs/DllHijack.conf)
  - [x] [dllHijack.ps1](Scripts/dllHijack.ps1)

## March 21st
### Credential Access
- [x] Credential Dumping
  - [x] [CredentialDump.conf](SplunkAlert_Confs/CredentialDump.conf)
  - [x] [credentialDump.bat](Scripts/credentialDump.bat)
- [x] Credentials in Files
  - [x] [CredentialsinFiles.conf](SplunkAlert_Confs/CredentialsinFiles.conf)
  - [x] [credInFile.ps1](Scripts/credInFile.ps1)

### Discovery
- [ ] ~~Peripheral Device Discovery~~
- [x] Permission Groups Discovery
  - [x] [PermissionGroupsDiscovery.conf](SplunkAlert_Confs/PermissionGroupsDiscovery.conf)
  - [x] [permGroupDisco.bat](Scripts/permGroupDisco.bat)
### Lateral Movement
- [x] Exploitation of Remote Services
  - [x] [EternalBlueExploitationofRemoteServices.conf](SplunkAlert_Confs/EternalBlueExploitationofRemoteServices.conf)
  - [x] Use Metasploit Module
    - exploit/windows/smb/ms17_010_eternalblue
- [x] Logon Scripts
  - [x] [LogonScripts.conf](SplunkAlert_Confs/LogonScripts.conf)
  - [x] [logonScripts.bat](Scripts/logonScripts.bat)

## March 28th
### Collection
- [ ] ~~Data from Local System~~
### Exfiltration
- [x] Data Compressed
  - [x] [DataCompressed.conf](SplunkAlert_Confs/DataCompressed.conf)
  - [x] [compressC.ps1](Scripts/compressC.ps1)
### Command and Control
- [x] Connection Proxy
  - [x] [ConnectionProxy](SplunkAlert_Confs/ConnectionProxy.conf)
  - [x] [Instructions](https://www.thewindowsclub.com/reset-winhttp-proxy-settings-windows)
- [ ] ~~Custom Command and Control Protocol~~

## Apr 4th 
- [x] Completion



