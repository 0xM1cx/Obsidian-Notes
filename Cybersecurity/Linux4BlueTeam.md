# Introduction To Linux
```toc
```
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

The /dev directory contains the device files on the system that are recognized by Linux. Access to the disks on the system is made under this directory. For example “/dev/sda1” refers to a device. This device is a disk or a disk partition.  A **device file** is an interface to a device driver that appears in a file system as if it were an ordinary file. The purpose of device files is usually to provide simple interfaces to standard devices (such as printers and serial ports), but can also be used to access specific unique resources on those devices, such as disk partitions.
  
  
**/etc Directory**

The /etc directory is the directory that contains the configuration files on the system. It is one of the most important directories on Linux in terms of security. For example, the encrypted version of the users' passwords is kept under this directory. This file is explained later in the training. it also contains executables required to boot the system, and some log files.

  
  
**/home Directory**

The /home directory is the directory where users have various personal files. Downloaded files, documents, and user-specific files can be found under this directory. Since the files under this directory can give an idea about the user, they may be of interest to attackers in terms of security. Therefore, it is one of the directories that the SOC analyst should carefully examine. The size of this directory may vary depending on the user's activity. By default, when a new user is created, a new directory belonging to the user is created in the "/home" directory. However, because it is not mandatory, attackers do not usually create a new directory under the "/home" directory for newly created users.  
  
  
**/lib Directory**

Under the /lib directory, there are the library files used by the executable binaries in the system.  In simple terms, these are helpful files which are used by an application, command or a process for their proper execution.
  
  
**/media Directory**

The /media directory is the directory where the removable media, such as CD-ROM and USB, are mounted.  
  
  
**/mnt Directory**

The /mnt directory is the directory where the temporarily mounted file systems are located. Another way to define this directory is that is used as the temporary mount points for mounting storage devices, such as CDROMs, floppy disks and USB key drives.  

###### Difference between /media and /mnt 
The new standard is that /media is where the system mount removable media, and /mnt is for you to mount things manually.
  
**/opt Directory**

The /opt directory is the directory where the application software needed to be installed on the system additionally. Furthermore, it is usually described as for optional add-on software packages source, or anything that isn't part of the base system.
  
  
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


###### /bin, /sbin, /usr/bin,  /usr/sbin, /usr/local/bin, /usr/local/sbin

- **/bin**: For binaries usable before the **/usr** partition is mounted. This is used for trivial binaries used in the very early boot stage or ones that you need to have available in booting single-user mode. Think of binaries like `cat`, `ls`, etc.
- **/sbin**: Same, but for binaries with ***superuser(root)*** privileges required.
- **/usr/bin**: Same as first, but for general system-wide binaries.
- **/usr/sbin**: Same as above, but for binaries with superuser(root) privileges required
 
> If I'm writing my own scripts, where should I add these?

None of the above. You should use **/usr/local/bin** or **/usr/local/sbin** for system-wide available scripts. The **local** path means it's not managed by the system packages.

For user-scoped scripts, usr **~/bin**(a personal bin folder in you home directory)

---
# Command Line
The command line is an intermediary program that receives commands from the user via the keyboard and transfers the commands to the operating system for execution. The command line in Linux is called "shell". There are many types of shells supported on Linux.

For debian, it uses "bash" shell.

## Command Line Structure
When the command line window is opened, we see a structure with a cursor waiting for a command from the user. This structure is as follows:

`username@hostname:current_directory$`

In this structure, the part before the "@" sign represents the username. The part from the "@" sign to the ":" sign represents the hostname. The part from the “:” to the `$` sign indicates which directory it is being worked on. The `$` sign on the far right is the last element in this structure. In the command line of the root user, who is the most authorized user in the system, the "#" sign is replaces  "$" sign at the end of this structure.

![[Pasted image 20220606090904.png]]

## Useful Linux Commands
### whatis
This command allows us to view a single line of brief information about commands running on the command line. 

### help 
This command is one of the information commands that gives a more detailed output than the `whatis` command. 

### man
This command provides the most detailed information about the commands and programs on the command line. It has a specific writing format. It offers very detailed content from description to parameters.

### pwd
This commands outputs the current directory that it is ran on. This commands stands for "print working directory". Again, it is the command that shows the working directory. 

### cd
This command is used to switch current directories. It stands for "change directory". When switching between directories with the cd command, the path of the target directory must be specified. There are two methods for specifying this path:
	**a. Absolute Path** -> is a notation written to indicate all sub-directories from the root directory ("/") to the current directory. For example, our current directory is `/home/shawn/Desktop` and we want to move to the `Documents` directory. We can use the absolute path as `cd /home/shawn/Documents`.
	**b. Relative Path** -> Unlike absolute path, Relative path is to write the part after the current directory instead of typing the full path of the directory to be traversed from the root directory "/".
	**c. Switching to the last directory with the Previous directory sign("-")** -> It is possible to switch to the previous directory, regardless of which directory it is. For example, our current directory `/home/shawn/Documents/tenable_CTF` and to move to the previous directory(`/home/buck/Desktop`) we use the "-".
```bash
shawn@shawn:~/Documents/tenable_CTF$ cd -
/home/buck/Desktop
shawn@shawn:~/Desktop$
```

### ls
This command lists directories and files. With this command, directories and files under a specified directory can be viewed.
		**Viewing hidden files and directories with the ls command**. The ls command does not show hidden files when used without parameters. In order to see hidden files, you must supply the `-a` parameter. When using this command the hidden files are indicated with the `.` at as a prefix to the file or folder name.
		**Getting detailed information about directories and files with the ls command**. When the ls command is used with the `-l` parameter, it provides detailed information about the files/directories it lists. The information given in by this command includes: permissions of the file/directory, owner of the file/directory the name of the user,  the owner of the file/directory the name of the group, the size of the file/directory(in bytes), the date the file/directory was last modified, and the name of the file/directory. 

### touch
The **touch** command is used to create an new empty file. An example would be `touch new.py`

### mkdir
This command is used to create a new directory, as it stands for "make directory". An example of the usage of this command: `mkdir new_Dir`. It is possible to make nested directories by supplying the `-p` parameter. Example `mkdir -p directory1/directory2`.

### mv
This command is used to move file/directory to another location. This command can also be used to rename the file/directory. Example of moving a file to another directory: `mv file1 Directory1/`. Example of renaming a file: `mv file1 file2_renamed`.

### cp
The **cp** command is used in file/directory copy operations. The first parameter in the cp command is the path of the file/directory to be copied. The second parameter is the target path. Example usage `cp file1 /directory1`.

It is possible to copy nested directories with the cp command. The `-r` parameter is used for this operation. Example of copy a nested directory: `cp -r /directory1/file1 directory2/`

### rm
This command is used to delete files/directories. In order to delete a directory, the parameter `-r` must be supplied for the rm command to delete files recursively i.e delete all the nested files and directories.

### cat
The cat command is the command used for reading from the file. The path of the file to be read can also be given as a parameter. Example `cat file.txt` or path to file `cat /Documents/passwd/passwds.doc`

### echo

