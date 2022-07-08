## Physical vs Logical Drives
**Disk partitioning or disk slicing** is the creation of one or more regions on secondary storage, so that each region can be managed separately. These regions are called partitions. It is typically the first step of preparing a newly installed disk, before any file system is created.

#### Physical Hard drive components
- Platters -- A hard disk
- Spindle -- Spins the platters
- Heads -- Read/Write
- Actuator arm -  Aligns the heads
![[Pasted image 20220427140018.png]]

![[Pasted image 20220427140248.png]]


#### Logical Structures
***Low-level Format***
- Physically lays down the tracks and sectors on the surface of the hard disks
- Low-level formatting is performed by the manufacturer

 *Track* The concentric circles on the platter. The circles are smaller towards the center of the platter and larger towards the outer edge. One white rick is one track.
 ![[Pasted image 20220427140616.png]]
 *Sectors*. This is one section of a track. It is the smallest unit of storage on the platter. This is just a little pie piece of the disk.
 ![[Pasted image 20220427140753.png]]
 *Clusters*. Group of sectors which are used to allocate the data storage area. A cluster has to do with allocation. A cluster is used to store data.
 ![[Pasted image 20220427141007.png]]
 
