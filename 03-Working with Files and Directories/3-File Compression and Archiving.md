File Compression and Archiving

In Linux, compressing and archiving files is a common practice to save disk space and organize multiple files into a single archive. This page will introduce the most commonly used tools and commands for file compression and archiving.
Understanding Compression and Archiving
Compression

Compression reduces the size of a file or group of files by encoding the data more efficiently. Compressed files use less disk space and can be transferred more quickly over networks. Common compression formats include .gz, .bz2, and .xz.
Archiving
Archiving involves combining multiple files and directories into a single file, often without compression. This makes it easier to manage and transfer large sets of files. The most common format for archiving in Linux is the tarball (.tar).
Combined Compression and Archiving

Often, files are both archived and compressed, creating a single compressed archive. For example, a .tar.gz file is a tarball that has been compressed using gzip.
Common Tools for Compression and Archiving
tar (Tape Archive)

The tar command is the most common tool for creating, extracting, and managing archives. It can be used with or without compression.
Creating an Archive

Basic Archive:

tar -cvf archive.tar /path/to/files

    -c: Create a new archive.
    -v: Verbose mode, lists files being archived.
    -f: Specifies the archive file name.

Compressed Archive with gzip:

tar -czvf archive.tar.gz /path/to/files

    -z: Compress the archive with gzip.

Compressed Archive with bzip2:

tar -cjvf archive.tar.bz2 /path/to/files

    -j: Compress the archive with bzip2.

Compressed Archive with xz:

tar -cJvf archive.tar.xz /path/to/files

        -J: Compress the archive with xz.

Extracting an Archive

Basic Extraction:

tar -xvf archive.tar

    -x: Extract the archive.

Extracting a Compressed Archive:

tar -xzvf archive.tar.gz

    -z: Decompress a gzip archive.

tar -xjvf archive.tar.bz2

    -j: Decompress a bzip2 archive.

tar -xJvf archive.tar.xz

    -J: Decompress an xz archive.

Extract to a Specific Directory:

tar -xvf archive.tar -C /path/to/directory

    -C: Specifies the directory to extract files into.

