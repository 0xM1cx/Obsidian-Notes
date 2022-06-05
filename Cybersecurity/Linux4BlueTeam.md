# Introduction To Linux
## What is Linux?
Linux is one of the kernel software, which is the most basic part of the computer OSs. It is a free software project released under the GNU General Public License version 2 and developed under the umbrella of the Linux Foundation. The name Linux was given by its first developer, **Linus Torvalds**, in 1991.

## Purpose of Use of Linux
Linux can be used for many purposes due to its nature. Linux is free and open source software.

<u>Free software</u> means software that respects the freedom of users and the community. <u>Sketchy</u> means that users have the freedom to run, copy, distribute, review, modify, and improve a software. So free software is not a question of price, it's a matter of freedom.

When you want to use Linux, you can install and use it without any license fee. Linux has a flexible structure. You can examine an issue in depth with linux. The open-source code of Linux allows you to work on it more comfortably.

**Uses of Linux**

Linux has the potential for being widely used. In the structure of Linux, it has the ability to work with processors with very high processing power, as well as limited processing power. Therefore, the usage areas of Linux vary widely. It is widely used in server systems, personal computers, devices hosting embedded systems, smart devices, and mobile devices.  
  
  
**Benefits of Linux**

Linux is a user-friendly operating system that provides many benefits to its users. This training explains the importance of Linux from the cyber security perspective.

Linux is famous for its command line. The power of the command line is an opportunity for cybersecurity professionals working in the cybersecurity industry because the use of Linux's command line can make many things easier and provide flexibility in application practice in cyber security projects and operations. It can save time. SOC analysts usually work on high dimensional data and Linux can easily handle the use of high dimensional data with the command line. So, it may always be beneficial for SOC analysts to have a Linux operating system at hand.  
  
  
**Common Linux distributions**

There are many different versions of Linux suitable for every type of user. Each of these versions is called a **distribution**, or simply a **distro**. The most popular and frequently used Linux distributions are as follows:

-   Ubuntu
-   CentOS
-   Fedora
-   Debian
-   Red Hat Enterprise Linux
-   Linux Mint
-   Open SUSE
-   Manjaro
  
There are a number of Linux distributions and the new ones keep being published day by day. In order to see and examine the Linux distributions, you can refer to the [distrowatch](distrowatch.com) web address.

---
# Linux File System Heirarchy
## What is Filesystem Hierarchy?
As in every operating system, Linux has a filing system as well. Everything in the Linux operating system consists of files. When all the files come together, they form all the components of the operating system. Files are in a grouped order by directories. In Linux, directories are in a hierarchical order. Hierarchical order means that one directory can be above or below another. In the Linux operating system, the directory structure must conform to a certain standard. The main directories in Linux and what they are used for are explained below.

**"/" - Root Directory**

The directory used as the top directory in the entire file hierarchy in Linux is the "Root Directory". The root directory is expressed with “/” and each directory to be written to the right is under the root directory. For example, the “/bin” directory means the directory named "bin” under the “/” directory. In other words, a parent directory of the "bin" directory is the "/"(root directory).  
  
  

![](https://letsdefend.io/images/training/linux101/structure.png)

  

  
  
**/bin Directory**

It is the directory where the binary files of the executable commands are located. The executable binary files of the basic commands are located under this directory.  
  
  
**/boot Directory**

The files that are needed when the operating system is first turned on, during the loading of the kernel are located under the boot directory.  
  
  
**/dev Directory**

The /dev directory contains the device files on the system that are recognized by Linux. Access to the disks on the system is made under this directory. For example “/dev/sda1” refers to a device. This device is a disk or a disk partition.  A device file is an interface to a device driver that appears in a file system as if it were an ordinary file. The purpose of device files is usually to provide simple interfaces to standard devices (such as printers and serial ports), but can also be used to access specific unique resources on those devices, such as disk partitions.
  
  
**/etc Directory**

The /etc directory is the directory that contains the configuration files on the system. It is one of the most important directories on Linux in terms of security. For example, the encrypted version of the users' passwords is kept under this directory. This file is explained later in the training. it also contains executables required to boot the system, and some log files.

  
  
**/home Directory**

The /home directory is the directory where users have various personal files. Downloaded files, documents, and user-specific files can be found under this directory. Since the files under this directory can give an idea about the user, they may be of interest to attackers in terms of security. Therefore, it is one of the directories that the SOC analyst should carefully examine. The size of this directory may vary depending on the user's activity. By default, when a new user is created, a new directory belonging to the user is created in the "/home" directory. However, because it is not mandatory, attackers do not usually create a new directory under the "/home" directory for newly created users.  
  
  
**/lib Directory**

Under the /lib directory, there are the library files used by the executable binaries in the system.  
  
  
**/media Directory**

The /media directory is the directory where the removable media, such as CD-ROM and USB, are mounted.  
  
  
**/mnt Directory**

The /mnt directory is the directory where the temporarily mounted file systems are located.  
  
  
**/opt Directory**

The /opt directory is the directory where the application software needed to be installed on the system additionally.  
  
  
**/proc Directory**

The /proc directory is the directory that contains the files that hold information about the current status of the running processes on the system.  
  
  
**/root Directory**

The most authorized user in Linux is the "Root" user. The root user also has a directory that contains its own files, like other users on the system. This directory is the "/root" directory. This directory can contain critical information just like any other user directory. Therefore, SOC analysts should control access to this directory separately.

The "/root" directory should not be confused with the "/" directory. The “/” directory is the topmost directory on the system. The “/root” directory is a directory under the “/” directory and belongs to the root user. Information about the root user and other users is explained in the following sections of the training.  
  
  
**/run Directory**

The /run directory is the directory that holds information about the running system since the last boot of the system.  
  
  
**/sbin Directory**

The /sbin directory is the directory where the binaries of executable commands are located. Usually, only the root users can run executable binaries under this directory.  
  
  
**/srv Directory**

The /srv directory is the directory that contains the data for the services offered by the system. For example, the data of services such as TFTP or FTP are located under this directory.  
  
  
**/tmp Directory**

The /tmp directory is the directory where temporary files are stored. Usually, the files under the "/tmp" directory are deleted during the system reboot. When analyzing a live Linux system, the cyber security specialist who responded to the incident should examine the "/tmp" directory in order to access critical data that may be deleted.  
  
  
**/usr Directory**

The /usr directory is the directory containing executable binaries, libraries, and other files that all users of the system can access with read-only privileges.  
  
  
**/var Directory**

The /var directory is known as the variable directory and contains system logs, files for tracking user activity, and cache files. It contains the logs that must be checked by the SOC analyst. According to the logs in the "/var" directory, the SOC analyst can see the unauthorized access to the system and take the necessary action.

In this part of the training, it is explained for what purpose each directory in the Linux file system hierarchy is used and what type of files it contains. In the next part of the training, the command line and basic commands are explained in practice.