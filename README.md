# holiday-tasks-2.0

 
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


