```toc
```

## What is Windows?
This the OS that has many different versions developed by **Microsoft**

The Windows OS was first released in 1985. Many versions of Windows have been released since the day it was released.

### Windows Versions
| **Name**       | **Release Date** |
| -------------- | ---------------- |
| Windows 1.01   | 1985-11-20       |
| Windows 3.0    | 1990-05-22       |
| Windows NT 3.1 | 1993-07-27       |
| Windows 95     | 1995-08-24       |
| Windows 98     | 1998-06-25       |
| Windows 2000   | 2000-02-17       |
| Windows XP     | 2001-10-25       |
| Windows Vista  | 2007-01-30       |
| Windows 7      | 2009-10-26       |
| Windows 8      | 2012-10-26       |
| Windows 10     | 2015-07-29       |
| Windows 11     | 2021-10-05                 |
![[intro1-1.png]]

### Windows Servers
| **Name**            | **Release Date** |
| ------------------- | ---------------- |
| Windows NT 3.1      | 1993-07-27       |
| Windows NT 4.0      | 1996-07-29       |
| Windows 2000        | 2000-02-17       |
| Windows Server 2003 | 2003-04-24       |
| Windows Server 2008 | 2008-02-27       |
| Windows Server 2012 | 2012-09-04       |
| Windows Server 2016 | 2016-10-12       |
| Windows Server 2019 | 2018-11-13       |
| Windows Server 2022 | 2021-08-18                 |

> For a more detailed information about windows versions visit this [link](https://en.wikipedia.org/wiki/List_of_Microsoft_Windows_versions)


## Windows Filesystem
### What is a File System?
A **File system** is a data structure that maintains the order of digital storage areas, and whose unit is a file. The OS cannot make sense of the space on the disk without the file system. It cannot know which data group is on the disk as a file. So the file system is a very important component for running the OS. File systems have different types of data structures. This data structures can be different for each file system.

### File Systems Used in Windows
File systems have also been developed, like every technology that has developed from the past to the present. With the development of technology, the need for new file systems has emerged due to increased processing power and storage capacity. Therefore, different file systems have been developed continuously and released to the market. Some of these file systems used in Windows OS are given below.

#### FAT
**File Allocation Table** file system was developed and released for personal computers in 1977. Although the purpose of its emergence was to be used on floppy disks, it was adapted to be used in hard drives and other devices over time. The FAT file system is not the default file system for Microsoft Windows OS today. Today, it is used in USB flash drives, flash drives, and other embedded systems.

#### exFat
**Extensible File Allocation Table** (exFAT) is a file system introduced by Microsoft in 2006 and optimized for flash memory such as USB flash drives and SD cards. This is designed to be a lightweight file system like FAT32, but without the extra features and overhead of NTFS and without the limitations of FAT32.

Like NTFS, exFAT has a very large limits on file and partition sizes, allowing you to store files much larger than the 4GB allowed by FAT32.

#### NTFS
**New Technology File System** was announced and started to be used with the Windows NT 3.1 version in 1993. It was used as the default file system within the Windows OS. It replaced FAT file system as it is a more advanced file system that is suitable for new technologies. In addition, NTFS file system also supports Linux and BSD systems.

Knowing the structure of the file system ensured that the security-oriented inferences to be obtained in the analyses are more and more consistent for analyst who perform host analysis. 

For a more detailed information on this topics research under the name of **"Filesystem Forensics"**.

## Directory Structure

### What is a Directory Structure?
In every OS, the folder and file structure in Windows takes place in a certain order from the first installation. This order is determined by the OS developer.

Although windows versions have similar folder structure in general, some folder and files may differ depending on the versions of the OS. In Windows, the root directory is *"drive:\"*. E.g. The root directory is usually *"C:\"*. The directory separator is usually a *"\"*. Physical and virtual drives are named by a drive letter, as opposed to being combined as one.

### Directories in Windows
When windows is first installed the directory structure is as follows.![[dir1.png]]

#### preflogs
This is used to keep **Windows performance logs**. It is found as an empty folder because the logging option is turned off by default.

#### Program files
If you have a 32 bit windows OS, all of your files will be stored here. But if you have a 64 bit OS, only 64 bit programs will be stored in this folder.

#### program files(x86)
This folder is only available on 64-bit windows operating systems. On a 64-bit OS all 32-bit programs installed on this architecture are located in this folder.

#### Program data
This folder is located as a hidden folder under the root of the disk where the Windows OS is installed. It contains all the data, settings, and user files that are required by the installed software and UWP apps. This directory contains application data for all users. This folder is used for application data that is not user-specific. I.e. it is where data of installed programs in windows are located.

#### Users
This folder contains the personal folder of each use who has logged on to the system at least once. Folders and documents such as download folder and its files, desktop folder, etc. Are stored under this folder that belongs to each user on the system.

#### WIndows
This is where the entire OS is installed. It has its own structure and it contains many systemic information in a certain order. E.g. the database where users' passwords are kept is located under this folder.

## Windows Command line

### What is the Command Line?
This is an intermediary program that receives commands from the user via the keyboard and transfers them to the OS for execution.

### Basic Commands
Many operations can be done via the command line. Below are some of the commonly used basic commands in Windows

#### help command
This command is used to provide a detailed information about the command used. E.g. `help tree`.

#### DIR
This command is the windows equivalent to ls for Linux and is used to list the files and folders under the current or specified director.

#### cd
This stands for 'Change Directory'. As the name suggests, this command is used to transition/change the current directory.

#### date
This commands is used to view and/or change the system's date information.

#### echo

