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
