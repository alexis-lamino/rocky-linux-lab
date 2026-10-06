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



## Users and Groups

Display the current user identity:

```bash
id
```

Display the groups of the current user:

```bash
groups
```

Display the user's sudo privileges:

```bash
sudo -l
```

## File Permissions

Display detailed file permissions:

```bash
ls -l <file>
```

Display directory permissions:

```bash
ls -ld <directory>
```

A typical permission string can be interpreted as:

```text
-rwxr-xr--
```

The permissions are divided into:

* Owner
* Group
* Others

For directories, the first character is `d`:

```text
drwx------
```

## File Metadata

Display detailed metadata about a file:

```bash
stat <file>
```

This can show:

* File size
* Owner
* Group
* Permissions
* Inode
* Access time
* Modification time
* SELinux security context

## SELinux Contexts

Display SELinux contexts:

```bash
ls -Z
```

Display SELinux contexts for a directory:

```bash
ls -laZ <directory>
```

SELinux adds an additional security layer beyond traditional Linux file permissions.

Common file contexts in a user's home directory include:

```text
user_home_t
```

Directory contexts may include:

```text
user_home_dir_t
```

## Security Principles

The lab follows the principle of least privilege:

* Users should receive only the permissions they require.
* Administrative privileges should be granted through controlled mechanisms such as `sudo`.
* File permissions should be reviewed before modifying access.
* SELinux should remain enabled unless there is a documented operational reason to change it.
* Security configurations should be tested before being deployed.
* Secrets and credentials must never be committed to the repository.

