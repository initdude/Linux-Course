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
```bash
    htop
    ```

    This opens the `htop` interface, where you can scroll, sort, and manage processes interactively.

## Managing Processes: `kill`, `pkill`, `killall`, and `nice`

### `kill` Command

The `kill` command sends signals to processes, typically to terminate them.

- **Kill a Process by PID**:

    ```bash
    kill PID
    ```

    This sends the default `SIGTERM` signal to gracefully terminate the process with the specified PID.

- **Force Kill a Process**:

    ```bash
    kill -9 PID
    ```

    This sends the `SIGKILL` signal to forcibly terminate the process.

### `pkill` Command

`pkill` allows you to send signals to processes based on their name, rather than their PID.

- **Kill Processes by Name**:

    ```bash
    pkill process_name
    ```

    This sends the `SIGTERM` signal to all processes with the specified name.

### `killall` Command

`killall` kills all instances of a process by name.

- **Kill All Instances of a Process**:

    ```bash
    sudo killall process_name
    ```

    This command kills all processes with the specified name.

### `nice` and `renice` Commands

The `nice` command is used to start a process with a modified scheduling priority, while `renice` changes the priority of an existing process.

- **Start a Process with a Lower Priority**:

    ```bash
    nice -n 10 command
    ```

    This starts the command with a nice value of 10, making it less CPU-intensive.

- **Change Priority of a Running Process**:

    ```bash
    sudo renice 10 -p PID
    ```

    This changes the priority of the process with the specified PID.

## Monitoring System Performance: `vmstat` and `iostat`

### `vmstat` Command

`vmstat` reports information about processes, memory, paging, block IO, traps, and CPU activity.

- **Basic Usage**:

    ```bash
    vmstat
    ```

    This displays a summary of the current system performance.

- **Continuous Monitoring**:

    ```bash
    vmstat 5
    ```

    This updates the performance summary every 5 seconds.

### `iostat` Command

`iostat` reports CPU and I/O statistics, useful for identifying bottlenecks in disk performance.

- **Basic Usage**:

    ```bash
    iostat
    ```
