# Filters

Filters in Linux are commands that process text streams and produce output that can be used in further processing. They are an integral part of shell scripting and command-line operations, especially when working with pipelines (`|`), where the output of one command is used as input for another.

This page will cover some of the most commonly used filters in Linux, including `cat`, `grep`, `sort`, `uniq`, `cut`, `tr`, and `sed`.

## `cat`: Concatenate and Display Files

The `cat` command reads files sequentially, writing their contents to the standard output. It’s often used to display the contents of files or to concatenate multiple files into one.

### Basic Usage

- **Display a File**: 

    ```bash
    cat filename
    ```

- **Concatenate Multiple Files**: 

    ```bash
    cat file1 file2 > combinedfile
    ```

- **Display Line Numbers**: 

    ```bash
    cat -n filename
    ```

## `grep`: Search Text Using Patterns

The `grep` command searches through text using patterns (regular expressions). It’s commonly used to find specific lines in a file that match a pattern.

### Basic Usage

- **Search for a Pattern in a File**:

    ```bash
    grep "pattern" filename
    ```

- **Search Recursively in a Directory**:

    ```bash
    grep -r "pattern" directory/
    ```

- **Show Line Numbers**:

    ```bash
    grep -n "pattern" filename
    ```

- **Ignore Case**:

    ```bash
    grep -i "pattern" filename
    ```

## `sort`: Sort Text

The `sort` command sorts lines in a file alphabetically or numerically.

### Basic Usage

- **Sort a File Alphabetically**:

    ```bash
    sort filename
    ```

- **Sort Numerically**:

    ```bash
    sort -n filename
    ```

- **Sort in Reverse Order**:

    ```bash
    sort -r filename
    ```

- **Sort by a Specific Field**:

    ```bash
    sort -k 2 filename
    ```

## `uniq`: Report or Omit Repeated Lines

The `uniq` command filters out repeated lines in a file, often used in conjunction with `sort`.

### Basic Usage

- **Remove Duplicate Lines**:

    ```bash
    sort filename | uniq
    ```

- **Count Occurrences of Lines**:

    ```bash
    sort filename | uniq -c
    ```

- **Only Print Duplicate Lines**:

    ```bash
    sort filename | uniq -d
    ```

## `cut`: Remove Sections from Each Line

The `cut` command extracts sections from each line of input, typically used to extract columns from text files or command outputs.
