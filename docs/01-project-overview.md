# Secure SSH Defense Lab – Project Overview

## Objective
The goal of this project is to simulate SSH brute-force attacks on a Linux server and implement effective defensive mechanisms to secure the SSH service.

## Scope
- Simulate password-based SSH attacks
- Analyze authentication logs
- Harden SSH configuration
- Deploy automated defense using Fail2Ban
- Validate security improvements

## Lab Environment
- Attacker: Kali Linux
- Target: Ubuntu Server (VirtualBox)
- Network: Isolated virtual network

## Skills Demonstrated
- Linux system administration
- SSH security hardening
- Log analysis
- Intrusion prevention
- Blue team fundamentals




### Baseline SSH Configuration

The SSH server was deployed using the default OpenSSH configuration provided by Ubuntu Server.
Most security-related directives were left commented, resulting in default behavior.

Key baseline characteristics:
- SSH running on default port 22
- Password-based authentication enabled
- No brute-force protection
- No IP restrictions
- Default logging level

This configuration represents a common real-world deployment prior to security hardening.










## Disclaimer
This project is conducted in a controlled lab environment for educational purposes only.
