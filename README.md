# Linux File Permissions Audit & Hardening

Practical lab documenting the detection and remediation of insecure file and directory permissions on a Linux server environment.

---

## Objective
Identify vulnerabilities caused by overly permissive files (such as global write permissions `-o+w` or `777`) and enforce secure standard permissions (`644` for files, `755` for directories).

## Configuration & Audit Steps

### 1. Simulated Vulnerable Environment
Created a test web directory structure and intentionally introduced insecure permissions (`777`):
```bash
mkdir -p /tmp/web_project/uploads
touch /tmp/web_project/config.php
chmod 777 /tmp/web_project/config.php
chmod 777 /tmp/web_project/uploads
