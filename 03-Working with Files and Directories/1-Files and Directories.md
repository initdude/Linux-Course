Files and Directories

In Linux, managing files and directories is a fundamental skill. This page will guide you through the basic commands and concepts needed to create, manipulate, and navigate files and directories in the Linux file system.
Understanding Files and Directories
Files

A file in Linux is a collection of data stored on disk. Files can contain text, binary data, or be executable scripts and programs. Each file is identified by a unique name within its directory.
Directories
Directories, also known as folders, are special files that can contain other files and directories. They help organize the file system into a hierarchical structure, making it easier to manage and locate files.
Basic File Operations
Creating Files

There are several ways to create files in Linux:

    Using touch: Creates an empty file or updates the timestamp of an existing file.

    touch filename.txt

Using echo: Creates a file with content.

echo "Hello, World!" > hello.txt

Using cat: Creates a file with content from standard input.

cat > notes.txt
This is my note.
Press Ctrl+D to save.

Viewing Files

Using cat: Displays the content of a file.

cat filename.txt

Using less: Allows you to scroll through a file's content.

less filename.txt

Using head: Displays the first 10 lines of a file.

head filename.txt

Using tail: Displays the last 10 lines of a file.

tail filename.txt
