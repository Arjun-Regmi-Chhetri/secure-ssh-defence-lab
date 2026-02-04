# Attack Simulation – SSH Brute Force

## Objective
The objective of this phase was to simulate a real-world SSH brute-force
attack against an Ubuntu Server running a default OpenSSH configuration,
in order to validate the security posture of the baseline system.

---

## Attacker Environment
- OS: Kali Linux
- Tool: THC-Hydra
- Attack Type: Password-based SSH brute force

## Target Environment
- OS: Ubuntu Server
- Service: OpenSSH
- Port: 22
- Authentication Method: Password-based

---

## Attack Methodology
A controlled password list was used to perform a brute-force attack
against a known valid user account on the SSH service.

The password list content used during the attack is documented in:
attack/password.txt

The attack was executed remotely from the attacker machine without any
prior access to the target system.

---

## Attack Execution
The following command was executed from the Kali Linux attacker host:

```bash
hydra -l arjun -P password.txt ssh://192.168.56.102 -t 4 -vV
```
