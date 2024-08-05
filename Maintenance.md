# holiday-tasks-2.0

### Why is System and Disk Drive Maintenance Important?

System and disk drive maintenance is crucial for several reasons:

1. **Prevent Damage:** Regular maintenance helps prevent damage to your system and hardware. If any issues are detected, maintenance can attempt to repair them or alert you to take action.
   
2. **Optimize Performance:** Many antivirus and antimalware programs are designed to optimize computer performance. For instance, if your antivirus is set to scan a file within 5 seconds, but you have a large 1GB file on a slower hard drive or SSD, it may not complete the scan in time, leaving your system vulnerable. Disk drive optimization ensures your drive reads data quickly, enhancing security.

### Disk Health Check

> [!NOTE]
> On Windows 11, navigate to `System > Storage > Disks & Volumes > Properties > Drive health` to view health information such as **Estimated remaining life**, **Available spare**, and **Temperature**.

To check the health status of all disks, use the following command:
```
wmic diskdrive get model,status
```
> [!IMPORTANT]
> You must run these commands in Command Prompt (cmd) or PowerShell as an administrator.

Repair Windows Image
```
DISM /Online /Cleanup-Image /RestoreHealth
```
*Note: More information can be found [here](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/repair-a-windows-image).*

Repair System Components and Files
```
sfc /scannow
```
*Note: More information can be found [here](https://support.microsoft.com/en-us/topic/use-the-system-file-checker-tool-to-repair-missing-or-corrupted-system-files-79aa86cb-ca52-166a-92a3-966e85d4094e).*

### Disk Defragmentation
 
> [!IMPORTANT]
> You must run these commands in Command Prompt (cmd) or PowerShell as an administrator.  
> Change "c:" to your drive letter; you can run these commands on all your disk drives formatted with NTFS.

Analyze
```
defrag c: /H /U /V /A
```
*Note: Perform the disk analysis.*

BootOptimize (for drive C: only)
```
defrag c: /H /U /V /B
```
*Note: Perform the defragmentation of boot files.*

> [!NOTE]
> **For SSDs (SSD, M.2, eMMC...)**

Retrim
```
defrag c: /H /U /V /L
```
*Note: Perform retrim to release free slabs. More info [here](https://www.crucial.com/articles/about-ssd/what-is-trim).*

Defrag
```
defrag c: /H /U /V /D
```
*Note: Fully defragment the disk, similar to a normal hard disk drive (HDD).*

> [!NOTE]
> **For SSDs (SSD, M.2, eMMC...)**

Slab consolidate
```
defrag c: /H /U /V /K
```
*Note: Perform slab consolidation to increase slab usage efficiency.*

> [!NOTE]
> **For HDDs only**

Tier Optimize
```
defrag c: /H /U /V /G
```
*Note: On tiered volumes, optimize files to reside on the appropriate storage tier.*

Consolidate free space
```
defrag c: /H /U /V /X
```
*Note: Perform free space consolidation, moves free space towards the end of the volume.*

> [!TIP]
> - ```/H``` - Run the tasks at normal priority instead of low.  
> - ```/U``` - Show task progress.  
> - ```/V``` - Verbose (optional).


### Malware Scanning

> [!WARNING]
> These tools can be used to check that your actual antimalware solution is working as expected; however, they are not a replacement for a real antimalware/antivirus solution.

- **Kaspersky Virus Removal Tool:** [Download Here](https://www.kaspersky.com/downloads/free-virus-removal-tool)
- **F-Secure Online Scanner:** [Download Here](https://www.f-secure.com/en/online-scanner)
- **Sophos Scan & Clean:** [Download Here](https://www.sophos.com/en-us/free-tools/virus-removal-tool)
