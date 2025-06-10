# Networking Commands

Networking is a critical aspect of Linux system administration, and knowing how to use networking commands effectively can help you manage, troubleshoot, and optimize your network connections. This page covers the most commonly used networking commands in Linux, providing practical examples and explanations.

## Checking Network Interfaces: `ip` and `ifconfig`

### `ip` Command

The `ip` command is a modern replacement for the older `ifconfig` command and provides more comprehensive network management capabilities.

- **Display Network Interfaces**:

    ```bash
    ip addr show
    ```

    This command shows all network interfaces and their IP addresses.

- **Bring an Interface Up/Down**:

    ```bash
    sudo ip link set dev eth0 up
    sudo ip link set dev eth0 down
    ```

    These commands bring the `eth0` interface up or down.

- **Assign an IP Address to an Interface**:

    ```bash
    sudo ip addr add 192.168.1.100/24 dev eth0
    ```

    This assigns the IP address `192.168.1.100` with a subnet mask of `24` to the `eth0` interface.

### `ifconfig` Command

Although `ifconfig` is deprecated, it is still used on many systems.

- **Display Network Interfaces**:

    ```bash
    ifconfig
    ```
This command lists all network interfaces along with their IP addresses.

- **Bring an Interface Up/Down**:

    ```bash
    sudo ifconfig eth0 up
    sudo ifconfig eth0 down
    ```

    These commands bring the `eth0` interface up or down.

- **Assign an IP Address to an Interface**:

    ```bash
    sudo ifconfig eth0 192.168.1.100 netmask 255.255.255.0
    ```

    This assigns the IP address `192.168.1.100` with a subnet mask of `255.255.255.0` to the `eth0` interface.

## Checking Network Configuration: `nmcli` and `nmtui`

### `nmcli` Command

`nmcli` is a command-line tool for managing NetworkManager and can be used to control network connections.

- **Show All Connections**:

    ```bash
    nmcli con show
    ```

    This lists all network connections and their statuses.

- **Connect to a Network**:

    ```bash
    nmcli con up id "connection_name"
    ```

    This brings up the specified network connection.

- **Disconnect from a Network**:

    ```bash
    nmcli con down id "connection_name"
    ```

    This disconnects the specified network connection.

### `nmtui` Command

`nmtui` provides a text-based user interface for managing NetworkManager connections.

- **Launch `nmtui`**:

    ```bash
    sudo nmtui
    ```

    This launches the `nmtui` interface, where you can easily manage network connections.

## Monitoring Network Traffic: `netstat`, `ss`, and `tcpdump`

### `netstat` Command

`netstat` is a classic command used to monitor network connections, routing tables, interface statistics, masquerade connections, and multicast memberships.

- **Display All Connections**:

    ```bash
    netstat -a
    ```

    This command lists all active connections, including TCP and UDP.

- **Display Listening Ports**:

    ```bash
    netstat -tuln
    ```

    This shows all listening ports with numeric IP addresses and port numbers.

### `ss` Command

`ss` is a modern alternative to `netstat`, offering faster performance and more detailed information.

- **Display All Connections**:

    ```bash
    ss -a
    ```
 This shows all listening ports with numeric IP addresses and port numbers.

### `tcpdump` Command

`tcpdump` is a powerful command-line packet analyzer used for network troubleshooting and security analysis.

- **Capture Packets on an Interface**:

    ```bash
    sudo tcpdump -i eth0
    ```

    This command captures packets on the `eth0` interface.

- **Save Captured Packets to a File**:

    ```bash
    sudo tcpdump -i eth0 -w capture.pcap
    ```

    This saves the captured packets to a file named `capture.pcap`.

## Testing Network Connectivity: `ping`, `traceroute`, and `mtr`

### `ping` Command

`ping` is used to test the reachability of a host on a network and measure the round-trip time for messages sent from the originating host.

- **Ping a Host**:

    ```bash
    ping google.com
    ```

    This sends ICMP echo requests to `google.com` and reports the results.

### `traceroute` Command

`traceroute` is used to track the path that packets take from your system to a destination.

- **Trace the Route to a Host**:

    ```bash
    traceroute google.com
    ```

    This shows the path taken by packets to reach `google.com`.

### `mtr` Command

`mtr` combines the functionality of `ping` and `traceroute` in a single network diagnostic tool.

- **Run `mtr` on a Host**:

    ```bash
    mtr google.com
    ```

    This command provides a real-time view of the network path to `google.com`.

## Network Configuration Files

Understanding the key network configuration files in Linux is essential for manual network setup and troubleshooting.

### `/etc/network/interfaces`

This file is used to configure network interfaces on Debian-based systems.

Example configuration:

```bash
auto eth0
iface eth0 inet static
    address 192.168.1.100
    netmask 255.255.255.0
    gateway 192.168.1.1
```

### `/etc/sysconfig/network-scripts/`

This directory contains configuration files for network interfaces on Red Hat-based systems.

Example configuration for `eth0`:

```bash
DEVICE=eth0
BOOTPROTO=static
ONBOOT=yes
IPADDR=192.168.1.100
NETMASK=255.255.255.0
GATEWAY=192.168.1.1
```
