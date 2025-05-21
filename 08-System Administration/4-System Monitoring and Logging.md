# System Monitoring and Logging

Effective system monitoring and logging are critical for maintaining a healthy and secure Linux environment. This page covers essential tools and techniques for monitoring system performance and managing logs.

## System Monitoring Tools

### `top` and `htop`

- **`top`**: A command-line tool that provides real-time information on system processes, including CPU and memory usage.
  - **Usage**: 
    ```bash
    top
    ```
  - **Key Features**:
    - Displays system summary, including uptime, load averages, and memory usage.
    - Shows a list of processes, sorted by CPU or memory usage.

- **`htop`**: An enhanced version of `top` with a user-friendly interface and more features.
  - **Usage**: 
    ```bash
    htop
    ```
  - **Key Features**:
    - Color-coded display for easier readability.
    - Interactive interface for killing processes, changing priority, and sorting by various metrics.

### `vmstat`

- **`vmstat`**: Reports virtual memory statistics, including processes, memory, paging, block I/O, traps, and CPU activity.
  - **Usage**: 
    ```bash
    vmstat 5
    ```
  - **Key Features**:
    - Provides a snapshot of system performance every 5 seconds.
    - Useful for identifying bottlenecks in memory or CPU usage.

### `iostat`

- **`iostat`**: Monitors system I/O, CPU, and disk usage statistics.
  - **Usage**: 
    ```bash
    iostat 5
    ```
  - **Key Features**:
    - Reports on disk read/write operations.
    - Helps identify I/O bottlenecks.

### `mpstat`

- **`mpstat`**: Reports CPU usage per processor.
  - **Usage**: 
    ```bash
    mpstat -P ALL 5
    ```
  - **Key Features**:
    - Displays CPU usage statistics for each CPU core.
    - Helps analyze multi-core CPU performance.
# System Monitoring and Logging

Effective system monitoring and logging are critical for maintaining a healthy and secure Linux environment. This page covers essential tools and techniques for monitoring system performance and managing logs.

## System Monitoring Tools

### `top` and `htop`

- **`top`**: A command-line tool that provides real-time information on system processes, including CPU and memory usage.
  - **Usage**: 
    ```bash
    top
    ```
  - **Key Features**:
    - Displays system summary, including uptime, load averages, and memory usage.
    - Shows a list of processes, sorted by CPU or memory usage.

- **`htop`**: An enhanced version of `top` with a user-friendly interface and more features.
  - **Usage**: 
    ```bash
    htop
    ```
  - **Key Features**:
    - Color-coded display for easier readability.
    - Interactive interface for killing processes, changing priority, and sorting by various metrics.

### `vmstat`

- **`vmstat`**: Reports virtual memory statistics, including processes, memory, paging, block I/O, traps, and CPU activity.
  - **Usage**: 
    ```bash
    vmstat 5
    ```
  - **Key Features**:
    - Provides a snapshot of system performance every 5 seconds.
    - Useful for identifying bottlenecks in memory or CPU usage.

### `iostat`

- **`iostat`**: Monitors system I/O, CPU, and disk usage statistics.
  - **Usage**: 
    ```bash
    iostat 5
    ```
  - **Key Features**:
    - Reports on disk read/write operations.
    - Helps identify I/O bottlenecks.

### `mpstat`

- **`mpstat`**: Reports CPU usage per processor.
  - **Usage**: 
    ```bash
    mpstat -P ALL 5
    ```
  - **Key Features**:
    - Displays CPU usage statistics for each CPU core.
    - Helps analyze multi-core CPU performance.

### `netstat` and `ss`

- **`netstat`**: Displays network connections, routing tables, interface statistics, masquerade connections, and multicast memberships.

### `netstat` and `ss`

- **`netstat`**: Displays network connections, routing tables, interface statistics, masquerade connections, and multicast memberships.
  - **Usage**: 
    ```bash
    netstat -tuln
    ```
  - **Key Features**:
    - Lists all listening ports and active network connections.

- **`ss`**: A more modern and faster alternative to `netstat` for displaying socket statistics.
  - **Usage**: 
    ```bash
    ss -tuln
    ```
  - **Key Features**:
    - Provides detailed network socket information.
    - Faster and more detailed than `netstat`.
### `sar`

- **`sar`**: Collects, reports, or saves system activity information.
  - **Usage**: 
    ```bash
    sar -u 5
    ```
  - **Key Features**:
    - Can report CPU, memory, I/O, network, and other system activities.
    - Useful for historical performance analysis.

### `df` and `du`

- **`df`**: Reports file system disk space usage.
  - **Usage**: 
    ```bash
    df -h
    ```
  - **Key Features**:
    - Shows available and used disk space for all mounted filesystems.
    - Human-readable format with `-h` option.

- **`du`**: Estimates file space usage.
  - **Usage**: 
    ```bash
    du -sh /path/to/directory
    ```
  - **Key Features**:
    - Displays the total disk usage of a directory.
    - Useful for identifying large files and directories.

## System Logging with `syslog` and `journalctl`

### `syslog`

- **`syslog`**: A standard for system logging, providing a central location for logging messages from the kernel and various applications.
  - **Configuration**: The configuration file for `syslog` is typically located at `/etc/rsyslog.conf`.
  - **Log Files**:
    - `/var/log/syslog`: General system logs.
    - `/var/log/auth.log`: Authentication logs.
    - `/var/log/kern.log`: Kernel logs.
    - `/var/log/mail.log`: Mail server logs.
    - `/var/log/boot.log`: Boot process logs.

- **Logging Levels**:
  - **emerg**: System is unusable.
  - **alert**: Action must be taken immediately.
  - **crit**: Critical conditions.
  - **err**: Error conditions.
  - **warn**: Warning conditions.
  - **notice**: Normal but significant condition.
  - **info**: Informational messages.
  - **debug**: Debug-level messages.

- **Managing Logs**:
  - **View logs**:
    ```bash
    cat /var/log/syslog
    ```
  - **Filter logs by date**:
    ```bash
    grep "Sep  1" /var/log/syslog
    ```
