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
