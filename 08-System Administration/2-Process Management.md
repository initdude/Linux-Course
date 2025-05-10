# Process Management

Process management is a fundamental aspect of Linux system administration, allowing you to monitor, control, and optimize the running processes on your system. This page covers the key commands and concepts related to managing processes in Linux.

## Understanding Processes

A process is an instance of a program running on your system. Each process is assigned a unique Process ID (PID) and operates independently, though processes can also create child processes. Processes can be in various states, such as running, sleeping, or stopped.

### Types of Processes

- **Foreground Processes**: These processes run directly under user control, often launched from a terminal, and block the terminal until they complete.
  
- **Background Processes**: These processes run independently of the terminal, allowing the terminal to be used for other tasks while the process continues running.

- **Daemon Processes**: These are background processes that typically start at boot and run continuously, providing services like web serving or database management.

## Viewing Processes: `ps`, `top`, and `htop`

### `ps` Command

The `ps` command provides a snapshot of currently running processes. It is highly versatile and can be used to display detailed process information.

- **Basic Process List**:

    ```bash
    ps
    ```

    This shows processes running in the current terminal.

- **Detailed Process List**:

    ```bash
    ps aux
    ```

    This command displays a detailed list of all running processes, including those not associated with the current terminal.

- **Filter by Process Name**:

    ```bash
    ps aux | grep process_name
    ```

    This command filters the process list to show only processes matching `process_name`.

### `top` Command

The `top` command provides a dynamic, real-time view of system processes. It displays resource usage and allows for process management.

- **Start `top`**:

    ```bash
    top
    ```

    This launches the `top` interface, showing processes, CPU usage, memory usage, and more.

- **Interactive Commands**:

    - `k`: Kill a process by entering its PID.
    - `r`: Renice (change the priority of) a process.
    - `q`: Quit the `top` interface.

### `htop` Command

`htop` is a more user-friendly version of `top`, offering a color-coded, interactive interface for monitoring processes.

- **Install `htop`** (if not already installed):

    ```bash
    sudo apt install htop
    ```

- **Start `htop`**:

