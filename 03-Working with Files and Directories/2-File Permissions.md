File Permissions

File permissions in Linux control who can read, write, and execute files and directories. Understanding and managing these permissions is crucial for maintaining the security and integrity of your system.
Understanding File Permissions

In Linux, each file and directory has three types of permissions that apply to three categories of users:
Categories of Users

    Owner: The user who owns the file.
    Group: The group that owns the file.
    Others: All other users who are not the owner or part of the group.

Types of Permissions

    Read (r): Allows viewing the contents of a file or listing a directory's contents.
    Write (w): Allows modifying a file's contents or adding/removing files in a directory.
    Execute (x): Allows running a file as a program or entering a directory.
Permission Structure

File permissions are represented as a string of 10 characters. For example:

-rwxr-xr--

The characters represent the following:

    The first character indicates the file type:
        - for a regular file.
        d for a directory.
        l for a symbolic link.
    The next three characters represent the owner's permissions.
    The following three represent the group's permissions.
    The last three represent others' permissions.

In the example -rwxr-xr--, the file is a regular file where:

    The owner has read, write, and execute permissions (rwx).
    The group has read and execute permissions (r-x).
    Others have only read permissions (r--).

Viewing File Permissions

To view the permissions of a file or directory, use the ls -l command:

ls -l filename.txt

The output will display the permissions, owner, group, size, and other details about the file:

-rw-r--r-- 1 user group 1234 Sep  2 14:32 filename.txt
Modifying File Permissions
Using chmod

The chmod command is used to change the permissions of a file or directory. Permissions can be set using either symbolic or numeric modes.
Symbolic Mode

In symbolic mode, you specify the permission type (r, w, x) and the category (u for owner, g for group, o for others, a for all):

    Grant Permissions:

    chmod u+x filename.txt

This command adds execute permissions for the owner.

Revoke Permissions:

chmod g-w filename.txt

This command removes write permissions for the group.

Set Permissions Exactly:

chmod o=r filename.txt

    This command sets others' permissions to read only.

Numeric Mode

In numeric mode, permissions are represented by a three-digit number, where each digit corresponds to the permissions for the owner, group, and others:

    r = 4
    w = 2
    x = 1

You add the values to set the desired permissions. For example:

    7 = rwx (4+2+1)
    6 = rw- (4+2)
    5 = r-x (4+1)
    4 = r-- (4)

To set permissions using numeric mode:

chmod 755 filename.txt

This command sets the permissions to rwxr-xr-x, where the owner can read, write, and execute, while the group and others can read and execute.
Using chown

The chown command changes the ownership of a file or directory:

    Change Owner:

    chown newowner filename.txt

Change Group:

chown :newgroup filename.txt

Change Owner and Group:

chown newowner:newgroup filename.txt
Special Permissions
Setuid and Setgid

Setuid (s): When applied to an executable file, the file runs with the privileges of the file's owner, not the user running it. This is indicated by an s in the owner's execute position.

chmod u+s filename

Setgid (s): When applied to a directory, new files created within inherit the group of the directory, rather than the primary group of the user who created the file. This is indicated by an s in the group's execute position.

chmod g+s directory

Sticky Bit

Sticky Bit (t): When set on a directory, only the file's owner, the directory's owner, or the root user can delete or rename files within the directory. This is commonly used on shared directories like /tmp. It is indicated by a t in the others' execute position.

chmod +t directory

Permission Pitfalls

    Overly Permissive Files: Setting permissions like 777 (read, write, and execute for everyone) can be a security risk. It allows any user to modify or execute the file.

    Root Permissions: Be cautious when modifying permissions as the root user. Incorrect settings can make critical system files inaccessible or executable, leading to system instability.

Practical Examples
Securing a Script

To create a script that only the owner can modify and execute, and others can only execute:

chmod 755 script.sh

Protecting a Shared Directory

To allow users to create files in a shared directory but prevent them from deleting each other's files:

mkdir /shared
chmod 1777 /shared

Setting a File for Execution with Owner's Privileges

To create a script that runs with the owner's privileges, regardless of who executes it:

chmod u+s script.sh
