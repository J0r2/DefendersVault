# holiday-tasks-2.0

### Disk Health Check

> [!NOTE]
> Go to Windows 11 `System > Storage > Disks & Volumes > Properties > Drive health`, there you will be able to see information about health like 
> **Estimated remaining life**, **Available spare** and **Temperature**.

Check all disks health status
```
wmic diskdrive get model,status
```

Repair Windows Image
```
DISM /Online /Cleanup-Image /RestoreHealth
```
*Note: More on https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/repair-a-windows-image*

Repair System Components and Files
```
sfc /scannow
```
*Note: More on https://support.microsoft.com/en-us/topic/use-the-system-file-checker-tool-to-repair-missing-or-corrupted-system-files-79aa86cb-ca52-166a-92a3-966e85d4094e)*

### Disk Defragmentation
 
> [!IMPORTANT]
> Change "c:" to your drive letter, you can run this commands on all your disk drives formatted with NTFS.

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
*Note: Perform retrim to release free slabs. More info here: https://www.crucial.com/articles/about-ssd/what-is-trim*

Defrag
```
defrag c: /H /U /V /D
```
*Note: Fully defragment the disk, like on a normal hard disc drive (HDD).*

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
> ```/H``` - Run the tasks on normal priority instead of low.
> 
> ```/U``` - Show task progress.
> 
> ```/V``` - Verbose (optional)

### Malware Scanning

> [!WARNING]
> This can be used to check that your actual antimalware solution is working as expected, these tools are not a replacement for a real antimalware/antivirus solution.

Kaspersky Virus Removal Tool
(https://www.kaspersky.com/downloads/free-virus-removal-tool)

F-Secure
(https://www.f-secure.com/en/online-scanner)

Sophos Scan & Clean
(https://www.sophos.com/en-us/free-tools/virus-removal-tool)
