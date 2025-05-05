# Managing Services

Services in Linux are background processes that start automatically when the system boots and provide various functions like web serving, database management, and network handling. Effective service management is crucial for system administrators to ensure that services run smoothly and securely.

This page will cover how to manage services using common tools like `systemctl` and `service`, along with some practical examples.

## Understanding Services and Daemons

- **Services**: These are programs that run in the background, typically without direct user interaction. Examples include web servers like Apache or Nginx, database servers like MySQL, and SSH servers.

- **Daemons**: These are special types of services that start at boot time and continue running as background processes, often named with a "d" at the end, such as `sshd` (SSH daemon) or `httpd` (HTTP daemon).

## Managing Services with `systemctl`

`systemctl` is the primary command used to control systemd-based services on modern Linux distributions like Ubuntu, CentOS, Fedora, and Debian.

### Starting a Service

- **Start a Service**:

    ```bash
    sudo systemctl start servicename
    ```

    Example:

    ```bash
    sudo systemctl start nginx
    ```

    This command starts the Nginx web server.

### Stopping a Service

- **Stop a Service**:

    ```bash
    sudo systemctl stop servicename
    ```

    Example:

    ```bash
    sudo systemctl stop nginx
    ```

    This command stops the Nginx web server.
