# Rocky Linux 9 — Installation & Initial Configuration

## Objective

Set up a Rocky Linux 9 system as a headless Linux administration lab for practicing enterprise Linux administration, networking, security, troubleshooting, and automation.

## Environment

* **Operating System:** Rocky Linux 9
* **Administration:** SSH from Windows
* **Network management:** NetworkManager
* **Service management:** systemd
* **Version control:** Git / GitHub

## Initial Configuration

After installation, the system was configured for remote administration.

### Network connectivity

The Ethernet interface was initially disconnected after installation/reboot.

NetworkManager was used to reconnect the interface:

```bash
sudo nmcli device connect <ETHERNET_INTERFACE>
```

Autoconnect was then enabled:

```bash
sudo nmcli connection modify <CONNECTION_NAME> connection.autoconnect yes
```

The network configuration was verified with:

```bash
ip a
nmcli device status
```

### SSH

The SSH service was enabled to allow remote administration:

```bash
sudo systemctl enable sshd
sudo systemctl start sshd
```

The service status was verified with:

```bash
sudo systemctl status sshd
```

SSH connectivity was tested remotely from Windows using:

```text
ssh <ADMIN_USER>@<SERVER_IP>
```

The connection was successfully established.

### Headless operation

The system was configured to operate without requiring a graphical console or monitor for normal administration.

Sleep and hibernation targets were disabled to prevent the lab server from becoming unavailable during remote administration:

```bash
sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
```

The system was then rebooted and SSH connectivity was tested again.

## Verification

After a complete power cycle:

* The system booted successfully.
* Network connectivity was restored automatically.
* The SSH service was available.
* Remote administration from Windows was successful.
* No monitor or keyboard was required for normal administration.

## Security Notes

No passwords, private keys, API tokens, certificates, public IP addresses, or other secrets are stored in this repository.

Network addresses shown in public documentation should use placeholders or documentation/example addresses rather than the real home network configuration.

## Lessons Learned

This initial configuration provided practical experience with:

* NetworkManager
* `nmcli`
* IP configuration
* systemd
* SSH
* remote administration
* headless Linux servers
* service persistence after reboot
* basic operational security
* technical documentation

## Next Steps

The next stages of the lab will focus on:

* Linux users and groups
* sudo and least privilege
* SSH key authentication
* firewalld
* SELinux
* system updates
* system logs
* network troubleshooting
* service hardening
