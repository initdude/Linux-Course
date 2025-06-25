# Security Best Practices

Ensuring the security of a Linux system is a critical task for any system administrator. This guide outlines key security best practices that can help protect your system from unauthorized access, vulnerabilities, and other security threats.

## 1. Introduction to Linux Security

- **Security Philosophy**: The principle of least privilege, where users and processes are granted the minimum level of access necessary.
- **Security Layers**: Combining multiple security mechanisms to provide defense-in-depth.

## 2. User and Group Management

### 2.1 Use the Principle of Least Privilege

- **Regular Users**: Limit the use of the root account for administrative tasks. Use `sudo` for commands that require elevated privileges.
- **Command**:
  ```bash
  sudo adduser newuser
  sudo usermod -aG sudo newuser
  ```
  - Creates a new user and adds them to the `sudo` group.

### 2.2 Strong Password Policies

- **Enforce Strong Passwords**: Use tools like `passwd` to enforce strong password policies.
- **Command**:
  ```bash
  sudo passwd newuser
  ```
  - Sets or changes the password for a user.

- **Password Aging**: Enforce password expiration policies.
- **Command**:
  ```bash
  sudo chage -M 90 newuser
  ```
  - Requires the user to change their password every 90 days.

## 3. Securing SSH

### 3.1 Disable Root Login via SSH

- **Command**:
  ```bash
  sudo nano /etc/ssh/sshd_config
  ```
  - Set `PermitRootLogin` to `no`.

### 3.2 Use SSH Key Authentication

- **Generate SSH Keys**:
  ```bash
  ssh-keygen -t rsa -b 4096
  ```
  - Generates a pair of SSH keys for secure login.

- **Copy Public Key to Server**:
  ```bash
  ssh-copy-id username@server_ip
  ```
  - Copies the public key to the server for authentication.

### 3.3 Change the Default SSH Port

- **Command**:
  ```bash
  sudo nano /etc/ssh/sshd_config
  ```
  - Change the `Port` directive to a non-standard port (e.g., `Port 2222`).

### 3.4 Use Fail2ban to Protect SSH

- **Install Fail2ban**:
  ```bash
  sudo apt-get install fail2ban
  ```
  - Protects SSH by banning IP addresses with too many failed login attempts.

## 4. Firewall Configuration

### 4.1 Use `ufw` (Uncomplicated Firewall)

- **Enable UFW**:
  ```bash
  sudo ufw enable
  ```
  - Enables the UFW firewall.

- **Allow SSH**:
  ```bash
  sudo ufw allow ssh
  ```
  - Allows SSH traffic through the firewall.

### 4.2 Basic Firewall Rules

- **Allow Specific Ports**:
  ```bash
  sudo ufw allow 80/tcp
  sudo ufw allow 443/tcp
  ```
  - Allows HTTP and HTTPS traffic.

- **Deny All Incoming Traffic by Default**:
  ```bash
  sudo ufw default deny incoming
  ```
  - Denies all incoming traffic unless explicitly allowed.

## 5. Keeping the System Updated

### 5.1 Regularly Update Software

- **Update Package Lists**:
  ```bash
  sudo apt-get update
  ```
  - Updates the package list for upgrades.

- **Upgrade Installed Packages**:
  ```bash
  sudo apt-get upgrade
  ```
  - Installs the latest versions of all installed packages.

- **Enable Automatic Security Updates**:
  ```bash
  sudo apt-get install unattended-upgrades
  ```
  - Automatically installs security updates.

## 6. Monitoring and Auditing

### 6.1 Log Monitoring

- **Use `logwatch`**:
  ```bash
  sudo apt-get install logwatch
  ```
  - Monitors and summarizes log files for suspicious activity.

### 6.2 Auditing with `auditd`

- **Install `auditd`**:
  ```bash
  sudo apt-get install auditd
  ```
  - Tracks system calls and file accesses for auditing purposes.

- **Start the Audit Service**:
  ```bash
  sudo systemctl start auditd
  ```

### 6.3 File Integrity Monitoring with `AIDE`

- **Install AIDE**:
  ```bash
  sudo apt-get install aide
  ```
  - Monitors file integrity and alerts on unauthorized changes.

- **Initialize the AIDE Database**:
  ```bash
  sudo aideinit
  ```

## 7. Securing Network Services

### 7.1 Disable Unnecessary Services

- **List All Services**:
  ```bash
  systemctl list-units --type=service
  ```
  - Lists all active services.

- **Disable a Service**:
  ```bash
  sudo systemctl disable servicename
  sudo systemctl stop servicename
  ```
  - Disables and stops an unnecessary service.

### 7.2 Configure Network Time Protocol (NTP)

- **Install and Enable NTP**:
  ```bash
  sudo apt-get install ntp
  sudo systemctl enable ntp
  sudo systemctl start ntp
  ```
  - Ensures accurate timekeeping, which is crucial for logging and security.

## 8. Disk Encryption

### 8.1 Encrypting Partitions with LUKS

- **Install Cryptsetup**:
  ```bash
  sudo apt-get install cryptsetup
  ```
  - Tool for managing LUKS encryption.

- **Encrypt a Partition**:
  ```bash
  sudo cryptsetup luksFormat /dev/sdX
  ```
  - Encrypts the specified partition.

- **Open and Use the Encrypted Partition**:
  ```bash
  sudo cryptsetup luksOpen /dev/sdX crypted_partition
  sudo mount /dev/mapper/crypted_partition /mnt
  ```
