# Troubleshooting Ubuntu Web Server

Common issues and solutions for the Apache web server setup on Ubuntu 24.04 LTS

## Issue 1: Apache2 Not Starting
- Checked: 'sudo systemctl status apache2' and 'sudo tail /var/log/apache2/error.log'.
- Fixed syntax errors: 'sudo apache2ctl configtest'.

## Issue 2: Page Not starting
- Verified firewall: 'sudo ufw status'.

## Issue 3: Monitor Logs
- Viewed logs: 'sudo tail -n 20 /var/log/apache2/access.log'


