# Evidence Acquisition
The acquired forensic image will be the foundation of your analysis; any mistake may tamper with the evidence, rendering it inadmissible in court. You may have two or more chances on the analysis part, but the acquisition is a single-shot chance. Just by looking through the files or by booting up the computer, you may destroy or even lose your evidence. Therefore, following the right steps of evidence acquisition will guarantee sound evidence and will make you confident about the evidence between your hands. 

In data acquisition you will deal with three types of data: **active**, **archival**, and **latent data.** 

First is the ***active data***, which is the information that you can actually see. The active data includes files data, programs, and operating system files. Acquiring such a data type is the easiest. 

You may also deal with ***archival Data***, which is backed up and stored, this includes tapes, CDs, or an entire hard drive. 

The third type is ***latent data***, such as deleted or partially overwritten data. The latent type of data requires special tools to access it. According to the case, you may deal with one or all these types of data.

No matter the type of data, you should always keep in mind that digital evidence is fragile and volatile. Hence, methodological procedures should be followed to ensure the integrity of the data during the acquisition process, this includes:
- Understanding the order of volatility
- Understanding imaging methods
- Knowing availbale forensics image files formats
- Be familiar with the capabilities of imaging tools
- Keep continuity in mind
- Understand and know how to use write-blockers
- Understand and know how to validate acquired images
- Last but most important, documentation aka CoC

### Understanding the order of volatility
The evidence acquisition must be based on the volatility of the evidence data, this guarantees no or minimum data modification. Therefore, the order of volatility is important in forensic investigation. Knowing which evidence drive is more volatile, determines which evidence will be captured first. The order is as follows:
1. Cache and Registers
2. ARP cache, routing table, memory, kernel statistics, process table.
3. Temporary files
4. Disks
5. Monitoring data and remote logging about the computer in question
6. Physical configuration, network topology
7. Archival media

The first row of evidence types can only be captured in case the investigated machine was running. However, in some cases, a part of the memory (PageFile) may be found on the hard disk. Many applications store files as temporary, which holds valuable evidence for investigation.

Throughout the upcoming courses, you will learn and practice several concepts, methods, and tools for forensic acquisition. When you capture digital evidence, the evidence is saved in a form of a forensic image. So what is a forensic image?

### Copy or Image
During a forensic investigation, we cannot perform tasks directly on the original evidence, since it will be considered contaminated. If I cannot work on the original evidence, should I copy or clone the drive or should I capture an image? What is the difference between these three concepts?

First, **copying** a piece of evidence provides the actual data of a particular file. Therefore, you just copy the data without any extra information, such as the file’s metadata. Due to the importance of metadata and other information on the drive, digital forensic investigators capture an image of the drive. 

**Imaging** an evidence drive allows capturing the entire drive ***bit-by-bit***, including actual files, data in slack space, swap files, and unallocated space(which may contain deleted files).

The term **cloning** is used in the place of imaging, and both create a replica of your drive. If you clone the drive, all files will be copied along with the Master Boot Record(MBR) and all other files needed for booting. Cloning is creating a one-to-one copy of the drive, thus, if a drive fails, you can just replace it with a cloned drive.

This means that you can insert the drive into another machine and boot the machine from this drive. However, imaging beats cloning in performance, since drive imaging creates compressed replicas of your drive, it provides more flexibility.

Frequently, forensic images are compressed to save space and maybe fragmented into several files that make it more manageable. Uncompressing a compressed image or recombining a fragmented image will generate the replica of the source. Besides, a cloned disk presents problems associated with guaranteeing the forensic integrity of the evidence on the destination drive. Except if it is mounted read-only, hence, is not commonly used as an imaging technique.

Another thing to keep in mind is Contiguity, which considers a backup plan in case your acquisition plan cannot be applied or an issue occurs during the acquisition. To ensure Contiguity, follow these guidelines:
1. Create two copies/images from the evidence drive, hence, in case one got corrupted the second one can be used for further analysis.
2. Use two different tools for image acquisition.

### Chain of Custody
The chain of custody is a series of documents that describes the evidence. It is used to keep track of evidence and ensure its integrity through forensic investigation. The contents in the chain of custody document will differ according to the law enforcement agency. However, some information is necessary, such as time and location of collection, details of collected evidence, and the reason it was collected.
![[Pasted image 20220516211123.png]]

Some chain of custody documents may contain the information of several evidence items. In such a document, the quantity and description of the item may be added.
![[Pasted image 20220516211244.png]]

The chain of custody document should be filled accurately with information about who is responsible for securing the digital evidence in every step during the investigation. Also, photos can be attached to this document to show the evidence state at the collection time. This is very important in case of acquiring a powered-on machine, which has running applications on its screen. You can also include a photo of the disk label.
![[Pasted image 20220516211411.png]]

### Write-Blocker
The **write blocker** is a hardware device or software application that enables read-only access to digital evidence. Write blocker ensures dataintegrity, since it ensures that no data is modified or added to the evidence drive. Windows mounts connected devices automatically, modifying files’ metadata, hence, it is essential to use a write-blocker. Both hardware and software blockers serve the same purpose.