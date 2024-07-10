# Home Lab Setup on Kali Linux and Ubuntu

This repository documents the setup and configuration of a home lab using Kali Linux and Ubuntu virtual machines on VirtualBox. The lab environment is designed for network security testing, privacy enhancement, and general Linux administration practice.

## Table of Contents
- [Introduction](#introduction)
- [Virtual Machines](#virtual-machines)
  - [Kali Linux](#kali-linux)
  - [Ubuntu](#ubuntu)
- [Tools and Utilities](#tools-and-utilities)
- [Setup Instructions](#setup-instructions)
- [Contributing](#contributing)
- [License](#license)

## Introduction
The home lab consists of two virtual machines running on VirtualBox:
- **Kali Linux**: A penetration testing distribution.
- **Ubuntu**: A versatile Linux distribution for general use.

Both virtual machines are configured with essential updates and tools for network security and privacy.

## Virtual Machines

### Kali Linux
The Kali Linux VM is configured for network security testing. Key steps in the setup include:
1. **Update System**:
    ```sh
    sudo apt-get update && sudo apt-get upgrade -y
    ```
2. **Install Airodump-ng**:
    ```sh
    sudo apt-get install aircrack-ng
    ```
3. **Setup Airodump-ng**: Used for network monitoring and cracking.
4. **Install Mullvad VPN**: To enhance privacy and security.
5. **Other Privacy Tools**: Additional tools to ensure privacy and security.

Detailed setup instructions can be found [here](kali-linux/setup.md).

### Ubuntu
The Ubuntu VM is configured for general Linux administration and additional security tools. Key steps in the setup include:
1. **Update System**:
    ```sh
    sudo apt-get update && sudo apt-get upgrade -y
    ```
2. **Install Airodump-ng**:
    ```sh
    sudo apt-get install aircrack-ng
    ```
3. **Setup Airodump-ng**: Used for network monitoring and cracking.
4. **Install Mullvad VPN**: To enhance privacy and security.
5. **Other Privacy Tools**: Additional tools to ensure privacy and security.

Detailed setup instructions can be found [here](ubuntu/setup.md).

## Tools and Utilities
- **VirtualBox**: For running the virtual machines.
- **Airodump-ng**: For network monitoring and cracking.
- **Mullvad VPN**: For enhancing privacy and security.
- **Other Privacy Tools**: Various tools to ensure privacy and security.

## Setup Instructions

### Update Systems
Run the following script to update both systems:
```sh
./scripts/update-systems.sh
