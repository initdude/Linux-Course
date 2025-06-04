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

