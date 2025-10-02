# Ubuntu 24.04 LTS Web Server Setup Guide

This guide documents the setup of a secure Apache2 web server, including firewall config, SSH hardening and additional security measures.

## Prerequisites
- Ubuntu 24.04 LTS
- Sudo privileges
- Internet connection

## Steps performed
1. **Updated the system**:
- Ran 'sudo apt update && sudo apt upgrade -y' to ensure all packages were up to date.

2. **Installed Apache2**:
- Installed with 'sudo apt install apache2 -y'
- Started and enabled: 'sudo systemctl start apache2 && sudo systemctl enable apache2'
- Verified status: 'sudo systemctl status apache2'

3. **Configured Firewall**:
- Allowed HTTP/HTTPS: 'sudo ufw allow 80/tcp && sudo ufw allow 443/tcp'
- Blocked telnet: 'sudo ufw deny 23/tcp'
- Enabled firewall: 'sudo ufw enable'
- Verified: 'sudo ufw status'

4. **Tested the web server**:
- Accessed via 'http://localhost' or http://serverip
- Created a custom 'index.html'

5. **Hardened SSH**
- Edited '/etc/ssh/sshd_config' to set 'Port 2222' and 'PermitRootLogin no'
- Restarted SSH: 'sudo systemctl restart ssh'

6. **Enabled Automatic Security Updates**
- Installed: 'sudo apt install unattended-upgrades -y'
- Configured: 'sudo dpkg-reconfigure --priority=low unattended-upgrades'.
- Restarted Apache2: 'sudo systemctl restart apache2'.

7. **Backed Up Web Files**:
- Created backup: 'sudo mkdir /backups && sudo tar -czf /backups/www-backup-$(date +%F).tar.gz /var/www/html'.





