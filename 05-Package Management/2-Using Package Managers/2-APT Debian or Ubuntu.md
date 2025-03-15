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
### Holding Packages

If you want to prevent a package from being upgraded, you can place a hold on it:

```bash
sudo apt-mark hold package-name
```

To remove the hold and allow upgrades again:

```bash
sudo apt-mark unhold package-name
```

### Adding Repositories

In some cases, you might need to add additional repositories to install software that is not available in the default repositories. To do this, first, add the repository:

```bash
sudo add-apt-repository ppa:repository-name
```

Then, update the package lists:

```bash
sudo apt update
```

Finally, you can install the package from the newly added repository.

### Managing PPAs (Personal Package Archives)

PPAs are third-party repositories for software packages. They are commonly used to get newer versions of software that are not yet available in the official repositories.

To add a PPA:

```bash
sudo add-apt-repository ppa:repository-name
```

To remove a PPA:

```bash
sudo add-apt-repository --remove ppa:repository-name
```

### Managing Sources List

The list of repositories that APT uses is stored in the `/etc/apt/sources.list` file and the `/etc/apt/sources.list.d/` directory. You can manually edit these files to add or remove repositories.

Example entry in `sources.list`:

```plaintext
deb http://archive.ubuntu.com/ubuntu/ focal main restricted
```

## Troubleshooting APT

### Resolving Package Conflicts

If APT encounters conflicts between packages during installation or upgrade, it will usually provide options to resolve them. You can force the installation with:

```bash
sudo apt install -f
```

