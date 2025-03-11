# APT (Debian/Ubuntu)

APT (Advanced Package Tool) is the package management system used by Debian, Ubuntu, and their derivatives. It simplifies the process of installing, updating, and removing software by handling dependencies and providing user-friendly commands.

## Understanding APT

APT is a front-end for the `dpkg` package management system, which handles `.deb` packages. APT automates the retrieval, configuration, and installation of software packages, making it easier for users to manage their systems.

### Key Components

- **apt-get**: A lower-level tool for managing packages.
- **apt**: A higher-level tool that combines functionalities of `apt-get` and `apt-cache` for a more streamlined experience.
- **dpkg**: The backend tool for handling `.deb` packages directly.

## Basic APT Commands

### Installing Packages

To install a package, use the following command:

```bash
sudo apt install package-name
```

Example:

```bash
sudo apt install git
```
### Updating Package Lists

Before installing or upgrading packages, update the package lists from the repositories:

```bash
sudo apt update
```

This command fetches the latest information about available packages, ensuring that you install the most recent versions.

### Upgrading Packages

To upgrade all installed packages to their latest versions:

```bash
sudo apt upgrade
```

If you want to perform a full system upgrade, which might include removing obsolete packages or installing new dependencies, use:

```bash
sudo apt full-upgrade
```

### Removing Packages

To remove a package while keeping its configuration files:

```bash
sudo apt remove package-name
```

Example:

```bash
sudo apt remove vlc
```

To remove a package along with its configuration files:

```bash
sudo apt purge package-name
```

### Searching for Packages

To search for a package by name or description:

```bash
apt search package-name
```

Example:

```bash
apt search apache
```
### Viewing Package Information

To view detailed information about a package, including its description, dependencies, and installation size:

```bash
apt show package-name
```

Example:

```bash
apt show nginx
```

### Cleaning Up

After installing or upgrading packages, you might want to clean up the local package cache to free up disk space:

```bash
sudo apt clean
```

To remove packages that were automatically installed to satisfy dependencies but are no longer needed:

```bash
sudo apt autoremove
```

### Fixing Broken Dependencies

Sometimes, package installations or removals can leave your system in an inconsistent state. To fix broken dependencies:

```bash
sudo apt --fix-broken install
```

This command will attempt to correct any dependency issues.

## Advanced APT Usage

### Pinning Packages

Pinning allows you to prioritize or prevent certain packages from being upgraded. This is useful if you want to stick with a specific version of a package.

To pin a package, you need to create or edit the `/etc/apt/preferences` file:

```plaintext
Package: package-name
Pin: version version-number
Pin-Priority: priority
```

For example, to pin the `nginx` package to version `1.18.0`:

```plaintext
Package: nginx
Pin: version 1.18.0
Pin-Priority: 1001
```
This command will display a list of packages matching the search term.
### Viewing Package Information

To view detailed information about a package, including its description, dependencies, and installation size:

```bash
apt show package-name
```

Example:

```bash
apt show nginx
```

### Cleaning Up

After installing or upgrading packages, you might want to clean up the local package cache to free up disk space:

```bash
sudo apt clean
```

To remove packages that were automatically installed to satisfy dependencies but are no longer needed:

```bash
sudo apt autoremove
```

### Fixing Broken Dependencies

Sometimes, package installations or removals can leave your system in an inconsistent state. To fix broken dependencies:

```bash
sudo apt --fix-broken install
```

This command will attempt to correct any dependency issues.

## Advanced APT Usage

### Pinning Packages

Pinning allows you to prioritize or prevent certain packages from being upgraded. This is useful if you want to stick with a specific version of a package.

To pin a package, you need to create or edit the `/etc/apt/preferences` file:

```plaintext
Package: package-name
Pin: version version-number
Pin-Priority: priority
```

For example, to pin the `nginx` package to version `1.18.0`:

```plaintext
Package: nginx
Pin: version 1.18.0
Pin-Priority: 1001
```

