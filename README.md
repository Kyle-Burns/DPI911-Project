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

## Feb 21st
- [x] Project Outlined
- [x] Provide outline for overall tasks.

## Feb 28th
### Initial Access
- [x] Exploit Public-Facing Application
  - [x] [ExploitPublicFacing.conf](SplunkAlert_Confs/ExploitPublicFacing.conf)

### Execution
- [x] Control Panel Items
  - [x] [ControlPanelItems.conf](SplunkAlert_Confs/ControlPanelItems.conf)
- [x] Dynamic Data Exchange
  - [x] [DynamicDataExchange.conf](SplunkAlert_Confs/DynamicDataExchange.conf)
- [ ] ~~Execution through API~~

## Mar 7th
### Persistence
- [x] Screensaver
  - [x] [ScreensaverPersistance.conf](SplunkAlert_Confs/ScreensaverPersistance.conf)
- [x] Security Support Provider
  - [x] [SecuritySupportProvider.conf](SplunkAlert_Confs/SecuritySupportProvider.conf)
- [x] Service Registry Permissions Weakness
  - [x] [ServiceRegistryPermissionWeakness.conf](SplunkAlert_Confs/ServiceRegistryPermissionWeakness.conf)
- [x] Shortcut Modification
  - [x] [ShortcutModificationPersistence.conf](SplunkAlert_Confs/ShortcutModificationPersistence.conf)
  - [x] [modLink.ps1](Scripts/modLink.ps1)
- [ ] ~~System Firmware~~
### Privilege Escalation
- [x] Exploitation for Privilege Escalation
  - [x] [ExploitationforPrivEsc.conf](SplunkAlert_Confs/ExploitationforPrivEsc.conf)
- [ ] ~~Extra Window Memory Injection~~
- [x] File System Permissions Weakness
  - [x] [FileSystemPermissionsWeakness.conf](SplunkAlert_Confs/FileSystemPermissionsWeakness.conf)
  - [x] [filesysperm.ps1](Scripts/filesysperm.ps1)

## Mar 14th
### Defense Evasion
- [x] Compiled HTML File
  - [x] [CompiledHTMLFile.conf](SplunkAlert_Confs/CompiledHTMLFile.conf)
- [ ] ~~Component Firmware~~
- [x] Component Object Model Hijacking
  - [x] [ComponentObjectModelHijacking.conf](SplunkAlert_Confs/ComponentObjectModelHijacking.conf)
- [x] Control Panel Items
  - [x] [ControlPanelItems](SplunkAlert_Confs/ControlPanelItems.conf)
- [x] DCShadow
  - [x] [DCShadow.conf](SplunkAlert_Confs/DCShadow.conf)
- [x] DLL Search Order Hijacking
  - [x] [DllHijack.conf](SplunkAlert_Confs/DllHijack.conf)
  - [x] [dllHijack.ps1](Scripts/dllHijack.ps1)

## March 21st
### Credential Access
- [x] Credential Dumping
  - [x] [credentialDump.bat](Scripts/credentialDump.bat)

- [x] Credentials in Files
  - [x] [credInFile.ps1](Scripts/credInFile.ps1)

### Discovery
- [ ] Peripheral Device Discovery
- [x] Permission Groups Discovery
  - [x] [permGroupDisco.bat](Scripts/permGroupDisco.bat)
### Lateral Movement
- [x] Exploitation of Remote Services
- [x] Logon Scripts
  - [x] [logonScripts.bat](Scripts/logonScripts.bat)

logonScripts.bat

## March 28th
### Collection
- [ ] Data from Local System
### Exfiltration
- [ ] Data Compressed
### Command and Control
- [ ] Connection Proxy
- [ ] Custom Command and Control Protocol

- [ ] 1 week grace period for fixing, troubleshooting errors.

## Apr 4th 
- [ ] Completion


