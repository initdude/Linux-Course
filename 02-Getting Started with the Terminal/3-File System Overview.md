File System Overview

The Linux file system is a hierarchical structure that organizes and stores all the data on a Linux system. Understanding the file system's layout and components is crucial for effectively managing files and navigating the system.
The Hierarchical Structure

The Linux file system is organized in a tree-like structure, with the root directory (/) at the top. All files and directories branch off from the root, forming a unified directory tree. This structure provides a consistent and organized way to manage files, regardless of their physical location on the storage devices.
Root Directory (/)

The root directory is the top-level directory in the Linux file system. All other directories and files reside under this directory. It serves as the starting point for navigating the entire file system.
Key Directories in the Linux File System

/bin: Contains essential user command binaries (executables) needed for system operation, such as ls, cp, and grep.

/sbin: Contains essential system binaries, typically for administrative tasks, like ip, iptables, and shutdown.

/etc: Stores system-wide configuration files. Examples include /etc/passwd for user accounts and /etc/fstab for file system mount points.

/home: Contains the home directories for all regular users. Each user has a personal directory under /home, such as /home/username.

/root: The home directory for the root (superuser) account. It is separate from /home for security reasons.

/var: Contains variable data files, including logs (/var/log), mail (/var/mail), and other files that change frequently.

/usr: Stores user-installed software and read-only data. It has several subdirectories, such as /usr/bin for non-essential command binaries and /usr/share for shared data like documentation and icons.

/lib: Contains essential shared libraries needed by binaries in /bin and /sbin. For example, /lib/x86_64-linux-gnu/ contains libraries for the x86_64 architecture.

/opt: A directory for installing optional software packages. Software installed here is usually independent of the system's package manager.


    /tmp: A temporary directory for storing transient files created by programs. Files in /tmp are often deleted upon reboot.

    /dev: Contains device files, which represent hardware devices like disks, terminals, and printers. For example, /dev/sda represents the first hard drive.

    /proc: A virtual file system that provides a view into the kernel's current state. It contains files that represent system information, such as /proc/cpuinfo for CPU details.

    /sys: Another virtual file system that exposes information about the system's hardware and kernel modules. It is often used in conjunction with /proc.

    /mnt: A directory typically used for mounting temporary file systems, such as a CD-ROM or USB drive.

    /media: Automatically created directories for mounting removable media like CDs, DVDs, and USB drives.

File Types in Linux

Linux supports various file types, each serving different purposes. You can identify the type of a file using the ls -l command, which displays a character at the beginning of each line to denote the file type:

    Regular Files (-): Standard files that contain data, such as text files, executables, and images.

    Directory Files (d): Special files that act as containers for other files and directories.

    Symbolic Links (l): Files that act as pointers or shortcuts to other files or directories.

    Character Devices (c): Files that represent devices that process data one character at a time, like keyboards and serial ports.

    Block Devices (b): Files that represent devices that process data in blocks, such as hard drives.

    Sockets (s): Files used for inter-process communication, often for network services.

    Named Pipes (p): Files used for inter-process communication, where data is read in the order it was written.
Inodes and File Metadata

In Linux, every file and directory is associated with an inode, a data structure that stores metadata about the file, such as:

    File Size: The total size of the file in bytes.
    File Permissions: The access permissions that determine who can read, write, or execute the file.
    Owner and Group: The user and group that own the file.
    Timestamps: Information about when the file was created, last modified, and last accessed.
    Link Count: The number of hard links to the file.

The inode does not store the file name or data itself; it only stores the metadata. The file name is stored in the directory that contains the file, which points to the inode.
Mounting and Unmounting File Systems

Linux can manage multiple file systems on different storage devices by mounting them to specific directories in the unified directory tree. Mounting makes a file system accessible at a specific point in the directory tree, while unmounting removes access.

    Mounting a File System:

    mount /dev/sdb1 /mnt/external

This command mounts the file system on /dev/sdb1 to the /mnt/external directory.

Unmounting a File System:

umount /mnt/external

This command unmounts the file system, making /mnt/external inaccessible until it is mounted again.
