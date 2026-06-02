# Azure Day 01: Create SSH Key Pair

## Objective
Create a secure SSH key pair for Azure Virtual Machine authentication and establish a secure access foundation for future VM labs.

## Problem Statement
Before launching Azure Virtual Machines, secure SSH authentication must be prepared. The task is to generate a reusable SSH key pair that can be used for passwordless and secure VM access.

## Prerequisites
- Active Azure subscription
- Azure CLI installed and authenticated (`az login`)
- Local terminal with permission to create files in `~/.ssh`

## Azure CLI Commands Used
```bash
# Create RSA 4096 SSH key pair
ssh-keygen -t rsa -b 4096 -f ~/.ssh/nautilus-kp -C "azure-vm-access"

# Verify key files
ls -l ~/.ssh/nautilus-kp ~/.ssh/nautilus-kp.pub

# View public key content for VM provisioning
cat ~/.ssh/nautilus-kp.pub
```

## Validation Steps
1. Confirmed both private and public key files were generated.
2. Verified private key permissions are restricted.
3. Confirmed the public key is available for Azure VM authentication configuration.

## Screenshots Section
- Add screenshot of key generation command output.
- Add screenshot showing `~/.ssh/nautilus-kp` and `~/.ssh/nautilus-kp.pub`.
- Add screenshot of public key content used during VM setup.

## Key Learnings
- Created an RSA SSH key pair named "nautilus-kp" using Azure services and validated secure authentication setup for Azure Virtual Machines.
- Understood how SSH key-based access improves security compared to password-based login.
- Practiced foundational secure access setup needed before VM provisioning.

## Real-World Use Cases
- Secure administrator access to Azure Linux VMs in production.
- Automated VM provisioning pipelines that inject SSH public keys during deployment.
- Standardized secure remote access for DevOps and platform engineering teams.

## Summary
Successfully created and validated the `nautilus-kp` RSA SSH key pair for Azure VM access. This lab established the baseline for secure, passwordless authentication in upcoming Azure infrastructure tasks.
