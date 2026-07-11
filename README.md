# AWS DevOps Internship: Static Web Deployment with Nginx

[![AWS](https://shields.io)](https://amazon.com)
[![Ubuntu](https://shields.io)](https://ubuntu.com)
[![Nginx](https://shields.io)](https://nginx.org)

A professional hand-on guide demonstrating how to provision cloud infrastructure on Amazon Web Services (AWS), manage a Linux environment, and deploy a public-facing web server.

---

## 🎯 Objective
Deploy a custom HTML profile website on an AWS EC2 Ubuntu instance using the Nginx web server to establish foundational cloud infrastructure and Linux administration skills.

## 🛠️ Tech Stack & Tools
* **Cloud Platform:** Amazon Web Services (AWS)
* **Compute Instance:** Amazon EC2 (Ubuntu Server 22.04 LTS, `t2.micro`)
* **Web Server:** Nginx
* **Terminal Client:** Git Bash / SSH

---

## 🔒 Security Group Configuration

The instance is secured via an AWS Security Group acting as a virtual firewall with the following inbound rules:

| Protocol | Port | Source | Purpose |
| :--- | :--- | :--- | :--- |
| **SSH** | 22 | My IP | Secure remote server management |
| **HTTP** | 80 | 0.0.0.0/0 (Anywhere) | Public web traffic delivery |

---

## 💻 Linux Commands Reference

### 1. Package Management & Installation
```bash
# Update local package indexes
sudo apt update

# Install Nginx web server (auto-approve prompts)
sudo apt install nginx -y
```

### 2. Service Operations
```bash
# Verify if the Nginx service is running
sudo systemctl status nginx

# Restart the server to apply configuration changes
sudo systemctl restart nginx
```

### 3. Resource Monitoring & Troubleshooting
```bash
# Check available and used disk space (human-readable)
df -h

# Check RAM utilization status
free -h

# List all actively running system processes
ps -ef
```

---

## 🚀 Step-by-Step Deployment Guide

### Phase 1: AWS Infrastructure Provisioning
1. Launch an **Ubuntu Server** EC2 instance under the AWS Free Tier.
2. Create and assign a **Security Group** with the inbound rules detailed in the table above.
3. Download the generated private key pair (`.pem` file) securely.

### Phase 2: Server Connection & Setup
1. Launch **Git Bash** on your local machine.
2. Connect to the instance using the downloaded key file:
   ```bash
   ssh -i "your-key.pem" ubuntu@your-ec2-public-ip
   ```
3. Update system repositories and execute the Nginx installation commands.

### Phase 3: Web Page Deployment
1. Navigate to the default web root directory:
   ```bash
   cd /var/www/html/
   ```
2. Replace the default placeholder file with your custom profile file:
   ```bash
   sudo nano index.html
   ```
3. Open your browser and paste your **EC2 Public IP address** to view the live website.

---

## 🌐 Deployed Website Overview
The hosted landing page contains the following profile parameters:
* 👤 **Name:** [Your Name]
* 🎓 **College:** [Your College Name]
* 🌿 **Branch:** [Your Engineering/Academic Branch]
* 📧 **Email:** [Your Professional Email Address]
* 📅 **Deployment Date:** [Date]

---

## 🧠 Learning Outcomes
* **Cloud Infrastructure:** Gained hands-on experience provisioning and securing cloud compute networks.
* **Linux Administration:** Mastered core bash commands for system monitoring, package installation, and process management.
* **Web Serving:** Learned how to install, configure, and maintain Nginx to serve live production web traffic.
* **Version Control:** Utilized Git and GitHub for documentation management and project version tracking.
