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
