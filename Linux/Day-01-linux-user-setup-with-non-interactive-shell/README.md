# Linux Day 01: Linux User Setup with Non-Interactive Shell

## Objective
Create a user named `kirsty` with a non-interactive shell on App Server 2 to enforce secure service-account behavior.

## Problem Statement
As part of the KodeKloud 100 Days of DevOps Challenge, create a Linux user account that cannot be used for interactive logins. Service accounts are commonly used by applications, backup agents, monitoring tools, and system services, and should be restricted from shell access.

## Prerequisites
- Access to App Server 2 with sudo privileges
- Basic Linux command-line access
- Existing `useradd`, `grep`, and `id` utilities

## Implementation
### Create the User
```bash
sudo useradd -s /sbin/nologin kirsty
```

### Verify User Creation
```bash
grep '^kirsty:' /etc/passwd
```

### Check User Information
```bash
id kirsty
```

### Alternative Verification
```bash
cat /etc/passwd | grep kirsty
```

## Expected Output
```text
kirsty:x:1001:1001::/home/kirsty:/sbin/nologin
```

## Command Breakdown
### `useradd`
Creates a new Linux user account.

### `-s`
Specifies the login shell assigned to the user.

### `/sbin/nologin`
Prevents interactive logins by displaying a message and terminating the login attempt.

### `kirsty`
The username being created.

## Why Use a Non-Interactive Shell?
Not every account on a Linux server is intended for human users.

Examples include:
- Backup Agents
- Monitoring Tools
- Database Services
- Web Servers
- Automation Services

Using a non-interactive shell improves security by preventing unnecessary access.

## Difference Between `/sbin/nologin` and `/bin/false`
| Feature | `/sbin/nologin` | `/bin/false` |
| --- | --- | --- |
| Prevent Login | ✅ | ✅ |
| Displays Message | ✅ | ❌ |
| Exits Immediately | ✅ | ✅ |
| Preferred for Service Accounts | ✅ | ⚠️ |

Example:
```bash
useradd -s /sbin/nologin backupuser
```

This provides better feedback when a login attempt is made.

## Key Learnings
- Linux user management
- Service accounts
- Login shell configuration
- Linux security best practices
- Understanding `/etc/passwd`
- Difference between `/sbin/nologin` and `/bin/false`

## Real-World Use Cases
- Backup agent accounts
- Monitoring services
- Application service accounts
- Database service users
- CI/CD automation users

## Screenshots Section
Add screenshots of:
- User creation command
- Verification output
- `/etc/passwd` entry
- Successful task completion

Store screenshots in:
```text
screenshots/
```

## References
- Linux User Management
- `man useradd`
- `man passwd`
- Linux Security Best Practices

## Challenge Status
**Completed Successfully**

Day 01 of the KodeKloud 100 Days of DevOps Challenge completed successfully.
