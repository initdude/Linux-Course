# System Maintenance

Maintaining a Linux system involves a set of routine tasks that ensure the system runs efficiently, securely, and reliably. This guide covers the essential maintenance tasks that every Linux administrator should perform regularly.

## 1. Introduction to System Maintenance

- **Purpose**: Regular maintenance helps prevent system failures, improves performance, and ensures security.
- **Frequency**: Some tasks should be done daily, while others may be weekly, monthly, or as needed.

## 2. Regular Updates and Upgrades

### 2.1 Keeping the System Up-to-Date

- **Update Package Lists**:
  ```bash
  sudo apt-get update
  ```
  - Synchronizes the package index files from their sources.

- **Upgrade Installed Packages**:
  ```bash
  sudo apt-get upgrade
  ```
  - Installs the latest versions of all installed packages.

- **Dist-Upgrade**:
  ```bash
  sudo apt-get dist-upgrade
  ```
  - Upgrades packages, intelligently handling dependencies and removing obsolete packages.

### 2.2 Kernel Updates

- **Install Kernel Updates**:
  ```bash
  sudo apt-get install linux-generic
  ```
  - Installs the latest kernel version available.

- **Check Current Kernel Version**:
  ```bash
  uname -r
  ```
  - Displays the current running kernel version.

## 3. Disk Space Management

### 3.1 Monitoring Disk Usage

- **Check Disk Usage**:
  ```bash
  df -h
  ```
  - Shows disk space usage in a human-readable format.

- **Find Large Files**:
  ```bash
  sudo du -ah / | sort -n -r | head -n 20
  ```
  - Lists the top 20 largest files and directories.

### 3.2 Cleaning Up Unnecessary Files

- **Remove Unused Packages**:
  ```bash
  sudo apt-get autoremove
  ```
  - Removes packages that were automatically installed to satisfy dependencies and are no longer needed.
- **Clean Up Package Cache**:
  ```bash
  sudo apt-get clean
  ```
  - Clears out the local repository of retrieved package files.

- **Empty Trash**:
  ```bash
  rm -rf ~/.local/share/Trash/*
  ```
  - Manually empties the trash to free up space.

## 4. Log Management

### 4.1 Monitoring Logs

- **View Logs with `journalctl`**:
  ```bash
  sudo journalctl -xe
  ```
  - Views system logs with extra details for troubleshooting.

- **Check Specific Service Logs**:
  ```bash
  sudo journalctl -u servicename
  ```
  - Views logs related to a specific service.

### 4.2 Log Rotation

- **Configure Log Rotation**:
  ```bash
  sudo nano /etc/logrotate.conf
  ```
  - Ensures logs are rotated, compressed, and deleted according to specified criteria.

- **Manual Log Rotation**:
  ```bash
  sudo logrotate -f /etc/logrotate.conf
  ```
  - Forces log rotation based on the current configuration.

## 5. Backup and Restore

### 5.1 Creating Backups

- **Using `rsync` for Backup**:
  ```bash
  rsync -av --delete /source/ /backup/
  ```
  - Synchronizes files between the source and backup directories, maintaining an exact copy.

- **Creating Compressed Backups**:
  ```bash
  tar -czvf backup.tar.gz /path/to/backup
  ```
  - Creates a compressed archive of the backup directory.

### 5.2 Automating Backups

- **Schedule Backups with Cron**:
  ```bash
  crontab -e
  ```
  - Example cron job to run backup every day at 2 AM:
  ```bash
  0 2 * * * rsync -av --delete /source/ /backup/
  ```

### 5.3 Restoring from Backup

- **Extract a Backup Archive**:
  ```bash
  tar -xzvf backup.tar.gz -C /restore/location
  ```
  - Extracts the contents of the backup to the specified location.

- **Restoring Files with `rsync`**:
  ```bash
  rsync -av /backup/ /restore/
  ```
  - Restores files from the backup directory to the restore location.

## 6. System Performance Monitoring

### 6.1 Real-Time Monitoring

- **Using `top`**:
  ```bash
  top
  ```
  - Displays real-time system resource usage, including CPU and memory.

- **Using `htop`**:
  ```bash
  sudo apt-get install htop
  htop
  ```
  - An enhanced version of `top` with a more user-friendly interface.

### 6.2 Analyzing System Performance

- **Check CPU and Memory Usage**:
  ```bash
  vmstat 1 5
  ```
  - Provides statistics on CPU and memory usage over time.

- **Disk I/O Monitoring**:
  ```bash
  iostat -xz 1 5
  ```
  - Monitors disk input/output statistics.

## 7. User and Group Maintenance

### 7.1 Managing User Accounts

- **List Users**:
  ```bash
  cut -d: -f1 /etc/passwd
  ```
  - Lists all user accounts on the system.

- **Remove Unnecessary Users**:
  ```bash
  sudo deluser username
  ```
  - Removes a user account.

### 7.2 Managing Group Membership

- **Add a User to a Group**:
  ```bash
  sudo usermod -aG groupname username
  ```
  - Adds a user to a specified group.

- **Remove a User from a Group**:
  ```bash
  sudo gpasswd -d username groupname
  ```
  - Removes a user from a specified group.

## 8. Hardware Maintenance

### 8.1 Checking Hardware Health

- **Monitor Disk Health with `smartctl`**:
  ```bash
  sudo apt-get install smartmontools
  sudo smartctl -a /dev/sdX
  ```
  - Checks the health status of a disk using SMART.

- **Monitor Battery Health (Laptops)**:
  ```bash
  upower -i /org/freedesktop/UPower/devices/battery_BAT0
  ```
  - Provides detailed information about the battery's health and status.

### 8.2 Checking for Hardware Failures

- **Check for Hardware Errors**:
  ```bash
  dmesg | grep -i error
  ```
  - Displays hardware-related errors from the system logs.

## 9. Automating Maintenance Tasks

- **Edit Crontab**:
  ```bash
  crontab -e
  ```
  - Opens the crontab file for editing scheduled tasks.

- **Common Maintenance Cron Jobs**:
  - Daily package updates:
    ```bash
    0 3 * * * sudo apt-get update && sudo apt-get upgrade -y
    ```
  - Weekly cleanup of temporary files:
    ```bash
    0 4 * * 7 sudo rm -rf /tmp/*
    ```
  
- Ensures that scheduled tasks are executed even if the system is off during the scheduled time.
