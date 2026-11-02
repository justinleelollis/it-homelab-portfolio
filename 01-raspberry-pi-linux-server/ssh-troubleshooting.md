# Troubleshooting SSH Service Configuration on Raspberry Pi OS

## Project Overview
While configuring SSH on my Raspberry Pi Linux server, I encountered an issue when attempting to enable the SSH service through systemd.

## Problem
Systemd refused to enable `sshd.service`, displaying an error indicating that it was a linked unit file.

## Troubleshooting Steps

1. **Checked the service status**

   Investigated the SSH service and identified `ssh.service` as the actual systemd unit.

2. **Inspected the systemd unit file**

   Examined the `[Install]` section and discovered `Alias=sshd.service`.

3. **Attempted to enable the actual service**

   Ran:

   ```bash
   sudo systemctl enable ssh.service
   ```

   The command completed without displaying an error.

4. **Investigated the alias error**

   Ran:

   ```bash
   sudo systemctl enable sshd
   ```

   Systemd rejected the command because `sshd.service` was a linked alias rather than the actual service unit.

## Root Cause

The issue was caused by a systemd service-name mismatch. `sshd.service` was an alias for the actual `ssh.service` unit. Systemd would not enable the linked alias directly.

## Resolution

Used the actual service name:

```bash
sudo systemctl enable ssh.service
```

## Verification

The next step is to verify that SSH is enabled at startup and actively running:

```bash
systemctl is-enabled ssh
systemctl is-active ssh
```

Expected results:

- `enabled`
- `active`

## Skills Practiced

- Linux command-line administration
- systemd service management
- SSH configuration
- Reading and inspecting systemd unit files
- Troubleshooting service aliases
- Identifying root causes and verifying resolutions
