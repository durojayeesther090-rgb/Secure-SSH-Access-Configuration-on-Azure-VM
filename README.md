# Secure-SSH-Access-Configuration-on-Azure-VM
This project demonstrates how to configure secure, passwordless SSH authentication for a Linux virtual machine hosted on Microsoft Azure.  The goal was to eliminate password based login and enforce a more secure authentication mechanism using SSH keys.

Objectives
Enable SSH key-based authentication
Disable reliance on password login
Configure secure access for the root user
Ensure proper permission settings

Tools & Technologies
Microsoft Azure
Linux (Ubuntu)
SSH

Architecture

Client (Landing Host)
   |
   |  SSH Key Authentication (RSA Key Pair)
   ↓
Cloud VM (xfusion-vm)
   - authorized_keys stores public key
   - sshd enforces authentication rules
   - Implementation Steps

1. Generate SSH Key Pair (Client Host)
```bash
ssh-keygen -t rsa -f /root/.ssh/id_rsa -N

Troubleshooting Highlights
Fixed SSH permission denied errors
Resolved missing key file issues
Corrected mismatched authorized_keys entries
Debugged SSH authentication using verbose mode (-vvv)

Security Improvements Implemented
SSH key-based authentication enforced
File permission hardening (700/600)
Root login restricted to key-based access
Eliminated password-based authentication risks


Key Learnings
SSH authentication flow and debugging
Linux permission model for security
Cloud VM access control practices
Root vs non-root user privilege handling
SSH daemon configuration and troubleshooting

Outcome
Successfully established secure, passwordless SSH access between client and cloud VM while enforcing security best practices.

