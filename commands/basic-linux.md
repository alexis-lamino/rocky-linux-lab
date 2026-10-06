# Basic Linux Commands

This document contains fundamental Linux commands used during the Rocky Linux administration lab.

## System Information

Display the operating system information:

```bash
cat /etc/os-release
```

Display the current hostname:

```bash
hostname
```

Display the current user:

```bash
whoami
```

Display the current working directory:

```bash
pwd
```

## Files and Directories

List files and directories:

```bash
ls
```

List files with detailed information:

```bash
ls -la
```

Change directory:

```bash
cd <directory>
```

Create a directory:

```bash
mkdir <directory>
```

Create an empty file:

```bash
touch <file>
```

Copy a file:

```bash
cp <source> <destination>
```

Move or rename a file:

```bash
mv <source> <destination>
```

Remove a file:

```bash
rm <file>
```

## System Administration

Display running processes:

```bash
ps aux
```

Display systemd service status:

```bash
systemctl status <service>
```

Display system logs:

```bash
journalctl
```

Update Rocky Linux packages:

```bash
sudo dnf update
```

## Notes

Commands should be tested in the lab before being added to this document.

Sensitive information such as passwords, private keys, tokens, and real infrastructure credentials are not stored in this repository.
