# Phase 3: Defence Implementation (SSH Hardening)

## Objective
The objective of this phase is to secure the SSH service on the Ubuntu server after identifying weaknesses during the attack simulation phase. The focus is on reducing the attack surface, preventing brute-force attacks, and enforcing secure authentication mechanisms.

---

## 1. Baseline Weakness Recap
From Phase 2 (Attack Simulation), the following weaknesses were identified:
- SSH password authentication was enabled
- SSH service was accessible on the default port
- No brute-force protection was active
- Weak user password was vulnerable to dictionary attacks

---

## 2. Password Hardening
The compromised user password was changed to a stronger password to immediately mitigate unauthorized access.

**Command used:**
```bash
passwd arjun
