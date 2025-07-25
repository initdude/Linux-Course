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
Copying Files

Using cp: Copies a file from one location to another.

cp source.txt destination.txt

Moving and Renaming Files

Using mv: Moves a file to a new location or renames it.

mv oldname.txt newname.txt
mv file.txt /path/to/destination/

Deleting Files

Using rm: Removes a file.

rm filename.txt

Searching for Files

Using find: Searches for files by name, type, or other criteria.

find /path/to/search -name "filename.txt"

Using locate: Searches for files in a pre-built database (faster than find).

locate filename.txt

Basic Directory Operations
Creating Directories

Using mkdir: Creates a new directory.

mkdir mydirectory

Creating Nested Directories: Use the -p option to create nested directories.

mkdir -p parent/child/grandchild

Navigating Directories

Using cd: Changes the current directory.

cd /path/to/directory

Going to Home Directory:

cd ~

Moving Up One Directory Level:

cd ..

Using pwd: Prints the current working directory.

pwd
Listing Directory Contents

Using ls: Lists files and directories.

ls

Listing with Details:

ls -l

Listing Hidden Files:

ls -a

Copying Directories

Using cp -r: Recursively copies a directory and its contents.

cp -r sourcedir destinationdir

Moving Directories

Using mv: Moves a directory to a new location.

mv mydirectory /path/to/destination/

Deleting Directories

Using rmdir: Removes an empty directory.

rmdir emptydir

Using rm -r: Recursively removes a directory and its contents.

rm -r mydirectory

File Types and Extensions

In Linux, file types are determined by their content and not just their extension. Common file types include:

    Regular Files: Contain data or code (.txt, .sh, .jpg).
    Executable Files: Can be run as programs (.sh, .bin, .exe).
    Symbolic Links: Pointers to other files or directories.
    Directories: Containers for files and other directories.

You can use the file command to determine the type of a file:

file filename

File Permissions and Ownership

Every file and directory in Linux has associated permissions and ownership that control access:

    Owner: The user who owns the file.
    Group: The group that owns the file.
    Others: All other users.

File Permissions

Permissions are represented as a string of 10 characters (e.g., -rwxr-xr--):

    The first character indicates the file type (- for a regular file, d for a directory).
    The next three characters represent the owner's permissions (r for read, w for write, x for execute).
    The following three represent group permissions.
    The last three represent others' permissions.
Changing Permissions

Using chmod: Modifies file permissions.

chmod 755 filename.txt

Using chown: Changes file ownership.

chown user:group filename.txt

Special Directories
Home Directory

The home directory (~) is where user files and personal settings are stored. Each user has a unique home directory located under /home/username.
Root Directory

The root directory (/) is the top-level directory in the file system hierarchy. It contains all other directories and files.
Temporary Directory
The /tmp directory is used for temporary files, often deleted on system reboot.
