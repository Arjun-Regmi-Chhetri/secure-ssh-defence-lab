# 🔒 Secure SSH Defense Lab

A hands-on cybersecurity project demonstrating SSH brute-force attack simulation and defense implementation in a controlled lab environment.

## 📋 Project Overview

This project simulates real-world SSH brute-force attacks against a Linux server and implements effective defensive mechanisms to secure the SSH service. It serves as a practical demonstration of blue team fundamentals, system hardening, and intrusion prevention techniques.

### Objective

Simulate SSH brute-force attacks on a Linux server and implement effective defensive mechanisms to secure the SSH service.

### Skills Demonstrated

- 🖥️ Linux system administration
- 🔐 SSH security hardening
- 📊 Log analysis and monitoring
- 🛡️ Intrusion prevention
- 🔵 Blue team fundamentals

---

## 🏗️ Lab Environment

### Infrastructure

- **Attacker Machine**: Kali Linux
- **Target Server**: Ubuntu Server (VirtualBox)
- **Network**: Isolated virtual network
- **Attack Tool**: THC-Hydra
- **Defense Tool**: Fail2Ban

### Network Configuration

The lab uses an isolated virtual network to ensure safe testing without affecting production systems or external networks.

---

## 🎯 Project Phases

### Phase 1: Baseline Configuration

Initial SSH server deployment with default OpenSSH configuration:
- SSH running on default port 22
- Password-based authentication enabled
- No brute-force protection
- No IP restrictions
- Default logging level

**Configuration files**: See [`configs/sshd_config_before`](configs/sshd_config_before)

### Phase 2: Attack Simulation

Simulated SSH brute-force attack using THC-Hydra:

```bash
hydra -l arjun -P password.txt ssh://192.168.56.102 -t 4 -vV
```

**Attack Environment**:
- OS: Kali Linux
- Tool: THC-Hydra
- Attack Type: Password-based SSH brute force
- Target Port: 22

**Password List**: See [`attack/password.txt`](attack/password.txt)

📖 **Details**: [Attack Simulation Documentation](docs/04-attack-simulation.md)

### Phase 3: Defense Implementation

Implemented comprehensive SSH hardening measures:

#### Security Improvements

1. **SSH Port Change**
   - Changed from default port 22 to port 2222
   - Reduces automated attack surface

2. **Disabled Root Login**
   - Set `PermitRootLogin no`
   - Prevents direct root access attempts

3. **Disabled Password Authentication**
   - Set `PasswordAuthentication no`
   - Enforces key-based authentication only

4. **Enhanced Password Security**
   - Changed weak passwords to strong ones
   - Implemented password complexity requirements

5. **Fail2Ban Integration** (Planned)
   - Automated intrusion prevention
   - IP blocking after failed attempts
   - Configurable ban policies

**Hardened Configuration**: See [`configs/sshd_config_after`](configs/sshd_config_after)

📖 **Details**: [Defense Implementation Documentation](docs/06-defense-implementation.md)

---

## 📁 Repository Structure

```
secure-ssh-defence-lab/
├── attack/               # Attack simulation files
│   └── password.txt     # Password list used in brute-force
├── configs/             # SSH configuration files
│   ├── sshd_config_before   # Default baseline configuration
│   └── sshd_config_after    # Hardened configuration
├── diagrams/            # Network and architecture diagrams
├── docs/                # Detailed documentation
│   ├── 01-project-overview.md
│   ├── 04-attack-simulation.md
│   └── 06-defense-implementation.md
├── screenshots/         # Lab evidence and screenshots
└── README.md           # This file
```

---

## 🚀 Getting Started

### Prerequisites

- VirtualBox (or similar virtualization platform)
- Kali Linux ISO
- Ubuntu Server ISO
- Basic knowledge of Linux and networking

### Setup Instructions

1. **Set up Virtual Network**
   - Create an isolated virtual network in VirtualBox
   - Configure network adapters for both VMs

2. **Deploy Target Server**
   - Install Ubuntu Server
   - Configure SSH service
   - Create user accounts

3. **Configure Attacker Machine**
   - Install Kali Linux
   - Install Hydra: `sudo apt install hydra`
   - Verify network connectivity to target

4. **Run Attack Simulation**
   - Use the password list from `attack/password.txt`
   - Execute Hydra with appropriate parameters
   - Monitor authentication logs on target

5. **Implement Defenses**
   - Apply SSH hardening configurations
   - Set up Fail2Ban
   - Test and validate security improvements

---

## 🔍 Key Security Changes

| Security Measure | Before | After |
|-----------------|--------|-------|
| SSH Port | 22 (default) | 2222 (custom) |
| Root Login | Allowed | Disabled |
| Password Auth | Enabled | Disabled |
| Key Auth | Optional | Required |
| Brute-force Protection | None | Fail2Ban |

---

## 📊 Results and Findings

### Attack Phase Results
- Successfully demonstrated vulnerability of default SSH configuration
- Weak passwords were cracked within seconds
- No automated defense mechanisms triggered

### Defense Phase Results
- SSH service hardened against common attacks
- Key-based authentication enforced
- Reduced attack surface through port changes
- Automated defense ready for deployment

---

## 📚 Documentation

Detailed documentation is available in the [`docs/`](docs/) directory:

- [Project Overview](docs/01-project-overview.md) - Comprehensive project background
- [Attack Simulation](docs/04-attack-simulation.md) - Attack methodology and execution
- [Defense Implementation](docs/06-defense-implementation.md) - Security hardening steps

---

## ⚠️ Disclaimer

**This project is conducted in a controlled lab environment for educational purposes only.**

- Do not perform these attacks on systems you do not own or have explicit permission to test
- Unauthorized access to computer systems is illegal
- This lab demonstrates defensive security concepts and ethical penetration testing
- Always follow responsible disclosure and ethical hacking guidelines

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page or submit a pull request.

---

## 📄 License

This project is open source and available for educational purposes.

---

## 👤 Author

**Arjun Regmi Chhetri**

- GitHub: [@Arjun-Regmi-Chhetri](https://github.com/Arjun-Regmi-Chhetri)

---

## 🙏 Acknowledgments

- Ubuntu and OpenSSH communities for excellent documentation
- Kali Linux and Offensive Security for security tools
- The cybersecurity community for best practices and guidance

---

*Built with 🔐 for learning and demonstrating SSH security fundamentals*
