# Introduction
Windows Kernel Explorer (you can simply call it as "WKE") is a free but powerful Windows kernel research tool. It supports from Windows XP to Windows 10 (32-bit and 64-bit). Compared to WIN64AST and PCHunter, WKE can run on the latest Windows 10 without updating binary files.

### How WKE works on the latest Windows 10
WKE will automatically download required symbol files if the current system is not supported natively, 90% of the features will work after this step. For some needed data that doesn't exist in symbol files, WKE will try to retrieve them from the DAT file (when new Windows 10 releases, I will upload the newest DAT file to GitHub). If WKE cannot access the internet, 50% of the features will still work. Currently, native support is available from Windows XP to Windows 10 RS3, Windows 10 from RS4 to 19H1 are fully supported by parsing symbol files and DAT file.

### How to customize WKE
You can customize WKE by editing the configuration file. Currently, you can specify the device name and symbolic link name of driver, and altitude of filter. You can also enable kernel-mode and user-mode characteristics randomization to avoid being detected by malware. If you rename the EXE file of WKE, then you need to rename SYS/DAT/INI files together with the same name.

### About digital signature and negative report from Anti-Virus softwares
Because I don't have a digital certificate, I have to use the leaked digital certificate from HT SRL to sign drivers of WKE. I use "DSEFIX" as an alternative solution to bypass DSE, you can try to launch WKE with "WKE_dsefix.bat" if WKE loads driver unsuccessfully on your system. Signing files with the HT SRL digital certificate has a side effect: almost all anti-virus softwares infer files with HT SRL digital signature are viruses, because many hackers use it to sign malwares since 2015. Only idiots implant malicious code into a tool for experienced programmers and reverse engineers, because most users only use WKE in test environments, this kind of behavior is meaningless.

### About loading driver unsuccessfully
##### If WKE prompts "unable to load driver", there may be the following reasons:
1. Secure boot is enabled.  
2. You are not running WKE as administrator.  
3. Anti-Virus software prevents the driver from loading.  
##### Solutions:
1. Disable secure boot.  
2. Run WKE as administrator.  
3. Add the files of WKE to the white list of Anti-Virus software.  

### About open source
It is a bit awkward, so I say straightforwardly: I don't plan to share the source code of this tool, but I may share some source code of test programs that associated with this tool.

# Main Features
1. Process management (Module, Thread, Handle, Memory, Window, Windows Hook, etc.)
2. File management (NTFS partition analysis, low-level disk access, etc.)
3. Registry management and HIVE file operation
4. Kernel-mode callback, filter, timer, NDIS blocks and WFP callout functions management
5. Kernel-mode hook scanning (MSR, EAT, IAT, CODE PATCH, SSDT, SSSDT, IDT, IRP, OBJECT)
6. User-mode hook scanning (Kernel Callback Table, EAT, IAT, CODE PATCH)
7. Memory editor and symbol parser (it looks like a simplified version of WINDBG)
8. Hide driver, hide/protect process, hide/protect/redirect file or directory, protect registry and falsify registry data
9. Path modification for driver, process and process module
10. Enable/disable some obnoxious Windows components

# [Screenshots](/screenshots/README.md)
In order to optimize the page load speed in low quality network environments, I only placed one picture on this page.
![image](https://raw.githubusercontent.com/AxtMueller/Windows-Kernel-Explorer/master/screenshots/mainmenu.png)

# Thanking List
1. Team of WIN64AST (I referenced the UI design and many features of this software)
2. Team of PCHunter (I referenced some features of this software)
3. Team of ProcessHacker (I studied the source code of this software, but I didn't use it in my project)
4. Author of DSEFIX (I use it as an alternative solution to load driver)

# Cooperation
### E-MAIL: AxtMueller#gmx.de (Replace # with @)
Please write E-MAIL in English or German, I only reply to E-MAILs that I am interested in.
### Provided services:
1. Feature customization: Add the features you need to WKE.
2. Binary customization: Modify obvious characteristics of WKE and remove all of my personal information in WKE.
3. Implant link: Implant link in WKE on "About" page, all users will see it when main dialog appears.
4. Specific feature separation: Copy source code of specific feature to a separate project.
5. Driver static library: It contains most of main features of WKE.
6. Driver source code: Entire driver source code of WKE.

# [Revision History](/binaries/README.md#all-revision-history)
### Current Version: 20190329
Bug fix: file operation failure in FAT32 partition.  
New feature: export all text in the list view to a file.  
### Revoked Versions: 00000000
These versions have serious security issues and should not be used anymore.
