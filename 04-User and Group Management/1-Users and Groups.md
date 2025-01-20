***After 2years of being away of this repo, i want to start it again for my freinds.***
Users and Groups

In Linux, users and groups are fundamental to managing access control, defining who can access what resources, and ensuring system security. This page will explore how to manage users and groups, including creating, modifying, and deleting them, as well as setting appropriate permissions.
Understanding Users and Groups
Users

A user in Linux is an account that can log in to the system and perform tasks. Each user has a unique username, user ID (UID), and a home directory where personal files and configurations are stored.
Groups

A group is a collection of users. Groups are used to simplify the management of permissions. Instead of assigning permissions to each user individually, you can assign them to a group, and all members of that group inherit those permissions.
System vs. Regular Users

    System Users: These accounts are used by system processes and services. They typically have a UID below 1000 and do not have a home directory.
    Regular Users: These are the accounts created for human users. They usually have a UID starting from 1000 and a home directory in /home.
Managing Users
Adding a New User

To add a new user, use the useradd command:

sudo useradd username

    By default, this command creates a user with the specified username, assigns the next available UID, and creates a home directory at /home/username.

Creating a User with Specific Options

Specify Home Directory:

sudo useradd -m -d /custom/home/dir username

    -m: Creates a home directory.
    -d: Specifies a custom home directory.

Assigning a Shell:

sudo useradd -s /bin/bash username

    -s: Specifies the login shell.

Setting an Expiry Date:

sudo useradd -e 2024-12-31 username

    -e: Specifies an expiry date for the account.
Setting a Password for a User

To set a password for a user, use the passwd command:

sudo passwd username

This command prompts you to enter and confirm a password for the specified user.
Modifying User Accounts

To modify an existing user account, use the usermod command:

    Change a User's Home Directory:

    sudo usermod -d /new/home/dir -m username

    -d: Specifies the new home directory.
    -m: Moves the content of the old home directory to the new one.

Change a User's Shell:

sudo usermod -s /bin/zsh username

    -s: Specifies the new login shell.

Lock or Unlock a User Account:

sudo usermod -L username   # Lock
sudo usermod -U username   # Unlock

        -L: Locks the user account.
        -U: Unlocks the user account.

Deleting a User

To delete a user, use the userdel command:

sudo userdel username

Delete a User and Their Home Directory:

sudo userdel -r username

        -r: Removes the user's home directory and mail spool.

Managing Groups
Adding a New Group

To add a new group, use the groupadd command:

sudo groupadd groupname

This creates a new group with the specified groupname.
Adding a User to a Group

To add a user to a group, use the usermod command with the -aG option:

sudo usermod -aG groupname username

    -aG: Adds the user to the specified group(s) without removing them from other groups.
Viewing a User's Groups

To view the groups a user belongs to, use the groups command:

groups username

Changing a User's Primary Group

A user's primary group is the group that owns files created by the user. To change the primary group, use the usermod command:

sudo usermod -g groupname username

    -g: Specifies the new primary group.

Deleting a Group

To delete a group, use the groupdel command:

sudo groupdel groupname

This removes the specified group from the system.
Understanding /etc/passwd, /etc/shadow, and /etc/group
/etc/passwd

The /etc/passwd file contains user account information, including usernames, UIDs, home directories, and default shells. Each line represents a user, with fields separated by colons (:).

Example entry:

username:x:1001:1001::/home/username:/bin/bash

/etc/shadow

The /etc/shadow file stores hashed passwords and related information. It is readable only by the root user for security reasons.

Example entry:

username:$6$hashvalue:18442:0:99999:7:::

/etc/group

The /etc/group file contains group information, including group names, GIDs, and group members. Each line represents a group.

Example entry:

groupname:x:1001:user1,user2


