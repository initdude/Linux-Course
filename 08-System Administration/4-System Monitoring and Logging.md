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
