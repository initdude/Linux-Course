# Networking Basics

Understanding networking is crucial for administering Linux systems, especially in environments where multiple systems need to communicate. This page covers the foundational concepts of networking and essential commands in Linux.

## Basic Networking Concepts

### IP Addressing

- **IP Address**: A unique identifier assigned to each device on a network. IP addresses can be either IPv4 or IPv6.
  - **IPv4**: A 32-bit address represented as four decimal numbers separated by dots (e.g., `192.168.1.1`).
  - **IPv6**: A 128-bit address represented as eight groups of four hexadecimal digits (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`).

### Subnetting

- **Subnet**: A subdivision of an IP network. Subnetting allows for better network management and security.
  - **Subnet Mask**: A 32-bit number that separates the IP address into the network and host portions (e.g., `255.255.255.0`).
  - **CIDR Notation**: A shorthand for specifying an IP address and its associated network mask (e.g., `192.168.1.0/24`).

### DNS (Domain Name System)

- **DNS**: A system that translates human-readable domain names (e.g., `www.example.com`) into IP addresses.
  - **DNS Servers**: Servers that store DNS records and respond to queries from clients (e.g., `8.8.8.8` for Google DNS).

### DHCP (Dynamic Host Configuration Protocol)

- **DHCP**: A protocol used to automatically assign IP addresses and other network settings to devices on a network.
  - **DHCP Server**: A server that dynamically assigns IP addresses to devices.
  - **DHCP Lease**: The duration for which an IP address is assigned to a device.

### MAC Address

- **MAC Address**: A unique hardware identifier assigned to a network interface card (NIC). MAC addresses are 48 bits long and typically represented in hexadecimal (e.g., `00:1A:2B:3C:4D:5E`).

## Networking Commands

### `ifconfig` and `ip`

- **`ifconfig`**: A traditional command for configuring network interfaces.
  - **Usage**:
    ```bash
    ifconfig
    ```
  - **Key Features**:
    - Displays IP addresses, subnet masks, and other information for network interfaces.
    - Can be used to bring interfaces up or down.

- **`ip`**: A more modern and powerful command for network configuration.
  - **Usage**:
    ```bash
    ip addr
    ip link
    ip route
    ```
  - **Key Features**:
    - `ip addr`: Displays IP addresses and associated information.
    - `ip link`: Manages network interfaces.
    - `ip route`: Manages routing tables.

### `ping`

- **`ping`**: Tests connectivity between your system and another device by sending ICMP echo requests.
  - **Usage**:
    ```bash
    ping 8.8.8.8
    ```
  - **Key Features**:
    - Verifies whether a host is reachable.
    - Measures round-trip time and packet loss.

### `traceroute`

- **`traceroute`**: Traces the path packets take to reach a destination.
  - **Usage**:
    ```bash
    traceroute www.example.com
    ```
  - **Key Features**:
    - Identifies each hop between your system and the destination.
    - Useful for diagnosing network routing issues.

### `netstat` and `ss`

- **`netstat`**: Displays network connections, routing tables, and interface statistics.
  - **Usage**:
    ```bash
    netstat -tuln
    ```
  - **Key Features**:
    - Shows active listening ports.
    - Displays network statistics.

- **`ss`**: A modern alternative to `netstat` for displaying socket statistics.
  - **Usage**:
    ```bash
    ss -tuln
    ```
  - **Key Features**:
    - Faster and more detailed than `netstat`.
    - Displays TCP, UDP, and UNIX socket connections.

### `curl` and `wget`

- **`curl`**: A command-line tool for transferring data from or to a server using various protocols (HTTP, FTP, etc.).
  - **Usage**:
    ```bash
    curl http://www.example.com
    ```
  - **Key Features**:
    - Downloads or uploads data to/from servers.
    - Supports multiple protocols.

- **`wget`**: A command-line utility for downloading files from the web.
  - **Usage**:
    ```bash
    wget http://www.example.com/file.zip
    ```
  - **Key Features**:
    - Supports downloading files from HTTP, HTTPS, and FTP protocols.
    - Can download entire websites for offline viewing.

### `nslookup` and `dig`

- **`nslookup`**: Queries DNS to obtain domain name or IP address mapping.
  - **Usage**:
    ```bash
    nslookup www.example.com
    ```
  - **Key Features**:
    - Resolves domain names to IP addresses.
    - Can be used to troubleshoot DNS issues.

- **`dig`**: A more flexible and powerful DNS lookup utility.
  - **Usage**:
    ```bash
    dig www.example.com
    ```
  - **Key Features**:
    - Provides detailed information about DNS queries.
    - Supports various query types (A, AAAA, MX, etc.).

### `iptables` and `ufw`

- **`iptables`**: A command-line tool for configuring the Linux kernel’s packet filtering rules (firewall).
  - **Usage**:
    ```bash
    sudo iptables -L
    ```
  - **Key Features**:
    - Manages rules that control incoming and outgoing traffic.
    - Can filter packets based on IP address, port, protocol, etc.

- **`ufw`**: A user-friendly frontend for managing firewall rules, typically used on Ubuntu.
  - **Usage**:
    ```bash
    sudo ufw status
    sudo ufw allow 22/tcp
    ```
  - **Key Features**:
    - Simplifies firewall management.
    - Can quickly enable or disable firewall rules.
### `hostname`

- **`hostname`**: Displays or sets the system's hostname.
  - **Usage**:
    ```bash
    hostname
    sudo hostnamectl set-hostname new-hostname
    ```
  - **Key Features**:
    - Displays the current hostname.
    - Can be used to change the system’s hostname.

## Network Configuration Files

### `/etc/network/interfaces`

- **Location**: `/etc/network/interfaces`
- **Purpose**: Configuration file for network interfaces in Debian-based distributions.
- **Example**:
    ```bash
    auto eth0
    iface eth0 inet static
        address 192.168.1.100
        netmask 255.255.255.0
        gateway 192.168.1.1
    ```

### `/etc/resolv.conf`

- **Location**: `/etc/resolv.conf`
- **Purpose**: Configuration file for DNS resolution.
- **Example**:
    ```bash
    nameserver 8.8.8.8
    nameserver 8.8.4.4
    ```

### `/etc/hosts`

- **Location**: `/etc/hosts`
- **Purpose**: Maps hostnames to IP addresses.
- **Example**:
    ```bash
    127.0.0.1   localhost
    192.168.1.100   myserver.localdomain   myserver
    ```

## Network Troubleshooting Tips

### Check Network Interface Status

- Use `ip addr` or `ifconfig` to ensure network interfaces are up and configured correctly.

### Test Connectivity

- Use `ping` to check connectivity between devices.
- Use `traceroute` to diagnose network path issues.

### Check DNS Resolution

- Use `nslookup` or `dig` to ensure DNS is resolving domain names correctly.

### Monitor Network Traffic

- Use `netstat` or `ss` to monitor network connections and troubleshoot issues.
