Linux Paths

In Linux, paths are used to specify the location of files and directories within the file system. Understanding how paths work is essential for navigating the system, managing files, and executing commands effectively.
What is a Path?

A path is a string that represents the location of a file or directory in the Linux file system. Paths are used in commands to tell the system where to find or place files. There are two types of paths in Linux:

    Absolute Path
    Relative Path


1. Absolute Path

An absolute path specifies the location of a file or directory from the root of the file system, which is denoted by a forward slash /. An absolute path always begins with /, regardless of your current working directory.

Example:

    /home/username/Documents/report.txt
    /etc/nginx/nginx.conf

In these examples, /home/username/Documents/report.txt is the full path to the report.txt file, starting from the root directory (/).
2. Relative Path

A relative path specifies the location of a file or directory relative to your current working directory. Unlike absolute paths, relative paths do not start with a /.

Example:

    Documents/report.txt
    ../username/Documents

If your current directory is /home/username, the relative path Documents/report.txt refers to the file /home/username/Documents/report.txt. The .. in ../username/Documents indicates moving up one directory level.
