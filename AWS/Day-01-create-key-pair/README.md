# AWS Day 01: Create Key Pair

## Objective
Create an EC2 Key Pair to enable secure SSH authentication for Amazon EC2 instances.

## Problem Statement
To access Linux EC2 instances securely, a key-based SSH authentication mechanism is required. The task is to create and manage an EC2 Key Pair for safe remote access.

## Prerequisites
- Active AWS account with EC2 access permissions
- Region selected in AWS Console
- AWS CLI configured (optional for CLI-based creation)

## AWS Console/CLI Steps
### AWS Console
1. Open **EC2 Dashboard**.
2. Navigate to **Network & Security > Key Pairs**.
3. Click **Create key pair**.
4. Enter name: `nautilus-kp`.
5. Select key pair type: **RSA** and private key format: **.pem**.
6. Download and securely store the key file.

### AWS CLI (Optional)
```bash
aws ec2 create-key-pair \
  --key-name nautilus-kp \
  --query 'KeyMaterial' \
  --output text > nautilus-kp.pem

chmod 400 nautilus-kp.pem
```

## Validation Steps
1. Verified `nautilus-kp` appears in the EC2 Key Pairs list.
2. Confirmed key fingerprint is generated in AWS.
3. Verified downloaded `.pem` file has secure local permissions.

## Screenshots Section
- Add screenshot of EC2 Key Pairs page with `nautilus-kp`.
- Add screenshot of key pair creation confirmation.
- Add screenshot of terminal showing secure `.pem` file permissions.

## Key Learnings
- Created and managed an EC2 Key Pair to enable secure SSH authentication for Amazon EC2 instances.
- Learned to protect private key files and apply least-privilege file permissions.
- Understood the role of key pairs in secure EC2 access workflows.

## Real-World Use Cases
- Secure SSH access for cloud-hosted Linux workloads.
- Controlled operational access for production EC2 instances.
- Standard key-based authentication setup for DevOps and infrastructure teams.

## Summary
Successfully created the `nautilus-kp` EC2 Key Pair and validated secure SSH access prerequisites for AWS compute services. This lab establishes a strong access-security baseline for upcoming EC2 tasks.
