
# Ubuntu Lab Setup Guide

This document is a personal guide on how I set up an Ubuntu virtual machine for my home lab. My setup focuses on both general Linux administration and specific security enhancements using VirtualBox.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Initial Setup](#initial-setup)
- [Tool Installation](#tool-installation)
- [Security Enhancements](#security-enhancements)
- [Maintenance and Updates](#maintenance-and-updates)

## Prerequisites
To start, I make sure to have:
- **VirtualBox** installed on my host machine.
- The **Ubuntu ISO** file downloaded from the official Ubuntu website.

## Initial Setup
1. **Creating a New Virtual Machine**:
   - I open VirtualBox and click "New".
   - I name the VM "UbuntuLab", selecting "Linux" and "Ubuntu (64-bit)".
   - I allocate at least 2048 MB of memory and create a virtual hard disk.

2. **Installing Ubuntu**:
   - I start the VM and select the Ubuntu ISO file when prompted.
   - I follow the installation instructions carefully, setting my timezone, keyboard layout, and user credentials.

3. **Inserting Guest Additions CD Image**:
   - After Ubuntu installs, I go to the VirtualBox menu, select "Devices", and then "Insert Guest Additions CD Image" to improve performance and enable shared folders.

## Tool Installation
1. **Updating the System**:
   ```
   sudo apt update && sudo apt upgrade -y
   ```
2. **Installing Network Tools**:
   ```
   sudo apt install net-tools nmap wireshark
   ```
   - For Wireshark, I grant non-root user permission to capture packets:
     ```
     sudo dpkg-reconfigure wireshark-common
     sudo usermod -a -G wireshark $USER
     ```

3. **Installing Security Tools**:
   ```
   sudo apt install clamav clamtk
   ```
   - I run a system scan with ClamAV:
     ```
     sudo clamscan -r /
     ```

## Security Enhancements
1. **Configuring the Firewall**:
   - I enable UFW (Uncomplicated Firewall):
     ```
     sudo ufw enable
     ```
   - I set default policies and allow SSH:
     ```
     sudo ufw default deny incoming
     sudo ufw default allow outgoing
     sudo ufw allow ssh
     ```

2. **Enhancing SSH Security**:
   - I edit the SSH configuration to disable root login and password authentication:
     ```
     sudo nano /etc/ssh/sshd_config
     ```
     - I change `PermitRootLogin` to `no`.
     - I change `PasswordAuthentication` to `no`.
   - I restart the SSH service:
     ```
     sudo systemctl restart sshd
     ```

## Maintenance and Updates
I regularly update my system to ensure it has the latest security patches and software updates:
```
sudo apt update && sudo apt upgrade -y
```

This guide outlines how I set up my Ubuntu VM in the home lab, customized to my specific needs for security and administration.
