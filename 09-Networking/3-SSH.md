# SSH: Secure Shell

SSH (Secure Shell) is a protocol used to securely connect to remote systems over a network. It provides a secure channel over an unsecured network by encrypting the connection. SSH is commonly used for remote command-line login, file transfers, and secure tunneling.

## 1. Introduction to SSH

- **Purpose**: SSH enables secure remote access to servers and devices, allowing users to execute commands, transfer files, and manage systems over a network.
- **Components**:
  - **SSH Client**: The software that initiates the connection.
  - **SSH Server**: The software running on the remote machine that accepts and manages the connection.

## 2. Basic SSH Usage

### 2.1 Connecting to a Remote Server

- **Command**:
  ```bash
  ssh username@hostname_or_ip
  ```
  - `username`: The user account on the remote system.
  - `hostname_or_ip`: The remote system's hostname or IP address.

- **Example**:
  ```bash
  ssh user@example.com
  ```
  - Connects to the remote server `example.com` as the user `user`.

### 2.2 Specifying a Port

- **Command**:
  ```bash
  ssh -p port_number username@hostname_or_ip
  ```
  - `-p port_number`: Specifies a non-default SSH port (default is 22).

- **Example**:
  ```bash
  ssh -p 2222 user@example.com
  ```
  - Connects to `example.com` on port 2222.

### 2.3 Using SSH Keys for Authentication

- **Generate SSH Key Pair**:
  ```bash
  ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
  ```
  - `-t rsa`: Specifies the RSA key type.
  - `-b 4096`: Generates a 4096-bit key (more secure).
  - `-C "your_email@example.com"`: Adds a comment (usually your email) to the key.

- **Copy Public Key to Remote Server**:
  ```bash
  ssh-copy-id username@hostname_or_ip
  ```
  - Copies your public key to the remote server, allowing key-based authentication.

- **Example**:
  ```bash
  ssh-copy-id user@example.com
  ```
  - Copies your public key to `example.com` for the user `user`.

### 2.4 SSH Config File

- **Location**: `~/.ssh/config`
- **Purpose**: Simplifies SSH connections by storing configuration options.

- **Example Configuration**:
  ```plaintext
  Host example
      HostName example.com
      User user
      Port 2222
      IdentityFile ~/.ssh/id_rsa
  ```
  - Allows you to connect using `ssh example` instead of specifying the full command each time.
## 3. File Transfers with SSH

### 3.1 Using `scp` (Secure Copy)

- **Command**:
  ```bash
  scp source_file username@hostname_or_ip:/remote/directory
  ```
  - Copies a file from the local system to the remote system.

- **Example**:
  ```bash
  scp file.txt user@example.com:/home/user/
  ```
  - Copies `file.txt` to the `/home/user/` directory on `example.com`.

### 3.2 Using `rsync`

- **Command**:
  ```bash
  rsync -avz source_directory username@hostname_or_ip:/remote/directory
  ```
  - `-a`: Archive mode, preserves permissions, symlinks, etc.
  - `-v`: Verbose output.
  - `-z`: Compresses the data during transfer.

- **Example**:
  ```bash
  rsync -avz /local/dir/ user@example.com:/remote/dir/
  ```
  - Synchronizes the local directory `/local/dir/` with `/remote/dir/` on `example.com`.

## 4. SSH Tunneling

### 4.1 Local Port Forwarding

- **Purpose**: Forwards a local port to a remote network service.
- **Command**:
  ```bash
  ssh -L local_port:remote_host:remote_port username@hostname_or_ip
  ```
  - `-L local_port:remote_host:remote_port`: Specifies local port forwarding.

- **Example**:
  ```bash
  ssh -L 8080:localhost:80 user@example.com
  ```
  - Forwards local port 8080 to port 80 on `example.com`.

### 4.2 Remote Port Forwarding

- **Purpose**: Forwards a remote port to a local network service.
- **Command**:
  ```bash
  ssh -R remote_port:local_host:local_port username@hostname_or_ip
  ```
  - `-R remote_port:local_host:local_port`: Specifies remote port forwarding.

- **Example**:
  ```bash
  ssh -R 8080:localhost:80 user@example.com
  ```
  - Forwards port 8080 on `example.com` to port 80 on the local machine.

### 4.3 Dynamic Port Forwarding (SOCKS Proxy)

- **Purpose**: Creates a SOCKS proxy to tunnel traffic through SSH.
- **Command**:
  ```bash
  ssh -D local_port username@hostname_or_ip
  ```
  - `-D local_port`: Specifies dynamic port forwarding.

- **Example**:
  ```bash
  ssh -D 1080 user@example.com
  ```
  - Sets up a SOCKS proxy on local port 1080.

## 5. Securing SSH

### 5.1 Disabling Root Login

- **Edit SSH Configuration**:
  ```bash
  sudo nano /etc/ssh/sshd_config
  ```
  - Find and set `PermitRootLogin` to `no`.

### 5.2 Changing the Default Port

- **Edit SSH Configuration**:
  ```bash
  sudo nano /etc/ssh/sshd_config
  ```
  - Change `Port 22` to a non-standard port (e.g., `Port 2222`).

### 5.3 Enabling Firewall Rules

- **Example** (Using `ufw`):
  ```bash
  sudo ufw allow 2222/tcp
  sudo ufw enable
  ```
  - Allows traffic on the custom SSH port and enables the firewall.

### 5.4 Two-Factor Authentication

- **Install and Configure**:
  ```bash
  sudo apt-get install libpam-google-authenticator
  ```
  - Follow instructions to set up two-factor authentication (2FA) with Google Authenticator.
