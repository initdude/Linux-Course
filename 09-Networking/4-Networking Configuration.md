# Networking Configuration

Networking is a critical aspect of any Linux system, as it allows the system to communicate with other devices over a network. This page will cover the basics of configuring network settings, managing interfaces, and using key networking tools in Linux.

## 1. Introduction to Networking Configuration

- **Networking Components**:
  - **IP Address**: Identifies a device on a network.
  - **Subnet Mask**: Defines the network segment.
  - **Gateway**: The device that routes traffic from a local network to other networks.
  - **DNS (Domain Name System)**: Resolves domain names to IP addresses.

## 2. Viewing Network Interfaces

### 2.1 Using `ifconfig`

- **Command**:
  ```bash
  ifconfig
  ```
  - Displays the current network interfaces and their configurations.
- **Example Output**:
  ```plaintext
  eth0      Link encap:Ethernet  HWaddr 00:1a:2b:3c:4d:5e  
            inet addr:192.168.1.10  Bcast:192.168.1.255  Mask:255.255.255.0
            ...
  ```
  - Shows the configuration of the `eth0` interface.

### 2.2 Using `ip` Command

- **Command**:
  ```bash
  ip addr show
  ```
  - Displays detailed information about all network interfaces.
- **Example**:
  ```plaintext
  2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
      inet 192.168.1.10/24 brd 192.168.1.255 scope global dynamic eth0
      ...
  ```

## 3. Configuring Network Interfaces

### 3.1 Using `ifconfig`

- **Assign an IP Address**:
  ```bash
  sudo ifconfig eth0 192.168.1.20 netmask 255.255.255.0
  ```
  - Assigns the IP address `192.168.1.20` with a subnet mask of `255.255.255.0` to `eth0`.

### 3.2 Using `ip` Command

- **Assign an IP Address**:
  ```bash
  sudo ip addr add 192.168.1.20/24 dev eth0
  ```
  - Assigns the IP address `192.168.1.20/24` to `eth0`.

### 3.3 Making Changes Persistent

- **Debian/Ubuntu**: Edit the `/etc/network/interfaces` file.
  ```plaintext
  auto eth0
  iface eth0 inet static
      address 192.168.1.20
      netmask 255.255.255.0
      gateway 192.168.1.1
  ```
- **RHEL/CentOS**: Edit the appropriate file in `/etc/sysconfig/network-scripts/`.
  ```plaintext
  DEVICE=eth0
  BOOTPROTO=static
  IPADDR=192.168.1.20
  NETMASK=255.255.255.0
  GATEWAY=192.168.1.1
  ONBOOT=yes
  ```
