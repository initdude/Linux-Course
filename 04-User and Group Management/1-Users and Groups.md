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

