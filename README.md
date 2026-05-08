# Linux Server Hardening

A collection of essential Linux server security and hardening practices for production environments.

## Topics Covered

- SSH hardening
- UFW firewall configuration
- Fail2Ban setup
- Docker security
- Automatic security updates
- Log monitoring
- Backup strategy
- NGINX security optimization
- Linux server monitoring
- Production environment security

---

## Update System Packages

```bash
sudo apt update && sudo apt upgrade -y
sudo apt autoremove -y
Create a New Sudo User
sudo adduser adminuser
sudo usermod -aG sudo adminuser
Disable Root SSH Login

Edit SSH config:

sudo nano /etc/ssh/sshd_config

Change:

PermitRootLogin no

Restart SSH:

sudo systemctl restart ssh
Configure UFW Firewall
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw enable

Check firewall status:

sudo ufw status
Install Fail2Ban
sudo apt install fail2ban -y
sudo systemctl enable fail2ban
sudo systemctl start fail2ban

Check status:

sudo fail2ban-client status
Enable Automatic Security Updates
sudo apt install unattended-upgrades -y
sudo dpkg-reconfigure unattended-upgrades
Monitor Authentication Logs
sudo tail -f /var/log/auth.log
Docker Security Tips
Avoid running containers as root
Use trusted images only
Limit exposed ports
Keep Docker updated
Scan images for vulnerabilities
Recommended Monitoring Tools
Prometheus
Grafana
Netdata
Uptime Kuma
Backup Strategy

Recommended tools:

rsync
BorgBackup
Restic
Rclone

Always maintain:

Daily backups
Offsite storage
Backup verification
Disaster recovery planning
Author

Sovrab Roy
Linux System Administrator & Server Engineer

🌐 Website: https://sovrabroy.online

💼 LinkedIn: https://linkedin.com/in/sovrabroy

🖥 GitHub: https://github.com/setu102

📘 DEV: https://dev.to/sovrab
